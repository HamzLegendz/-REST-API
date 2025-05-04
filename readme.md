
<h1 align="center" style="font-weight: bold; font-size: 2rem;">
  🚀 Simple Base REST API
</h1>
<p align="center">Modular Express.js REST API boilerplate built for scalability, performance, and ease of use.</p>

<p align="center">
  <svg xmlns="http://www.w3.org/2000/svg" width="140" height="28" role="img" aria-label="Express.js: 4.x">
    <linearGradient id="b" x2="0" y2="100%">
      <stop offset="0" stop-color="#bbb" stop-opacity=".1"/>
      <stop offset="1" stop-opacity=".1"/>
    </linearGradient>
    <rect rx="4" width="140" height="28" fill="#555"/>
    <rect rx="4" x="75" width="65" height="28" fill="#007acc"/>
    <path fill="#007acc" d="M75 0h4v28h-4z"/>
    <rect rx="4" width="140" height="28" fill="url(#b)"/>
    <g fill="#fff" text-anchor="middle" font-family="Verdana" font-size="11">
      <text x="38" y="19">Express.js</text>
      <text x="105" y="19">4.x</text>
    </g>
  </svg>

  <svg xmlns="http://www.w3.org/2000/svg" width="120" height="28" role="img" aria-label="Node.js: 18+">
    <rect rx="4" width="120" height="28" fill="#555"/>
    <rect rx="4" x="60" width="60" height="28" fill="#3c873a"/>
    <g fill="#fff" text-anchor="middle" font-family="Verdana" font-size="11">
      <text x="30" y="19">Node.js</text>
      <text x="90" y="19">18+</text>
    </g>
  </svg>

  <svg xmlns="http://www.w3.org/2000/svg" width="110" height="28" role="img" aria-label="API: Ready">
    <rect rx="4" width="110" height="28" fill="#555"/>
    <rect rx="4" x="50" width="60" height="28" fill="#facc15"/>
    <g fill="#000" text-anchor="middle" font-family="Verdana" font-size="11">
      <text x="25" y="19" fill="#fff">API</text>
      <text x="80" y="19">Ready</text>
    </g>
  </svg>

  <svg xmlns="http://www.w3.org/2000/svg" width="180" height="28" role="img" aria-label="Made by: HamzLegendz">
    <rect rx="4" width="180" height="28" fill="#555"/>
    <rect rx="4" x="80" width="100" height="28" fill="#d946ef"/>
    <g fill="#fff" text-anchor="middle" font-family="Verdana" font-size="11">
      <text x="40" y="19">Made by</text>
      <text x="130" y="19">HamzLegendz</text>
    </g>
  </svg>
</p>

---

## ⚙️ Getting Started

```bash
git clone https://github.com/ArixOffc/base-restapi.git
cd base-restapi
npm install
node index.js
```

Server starts on: [http://localhost:3000](http://localhost:3000)

---

## 🗂️ Project Structure

```txt
base-restapi/
├── api/
│   └── ai/
│       └── hydromind.js       # AI endpoint
├── views/
│   └── api.json               # API route docs
├── apiMonitor.js              # Logs API usage
├── index.js                   # Main server file
```

---

## ✨ Features

- Modern REST API base
- Plug-and-play routing system
- Request logging and analytics
- Dynamic API documentation (via `views/api.json`)

---

## 🧪 Example Endpoint

```http
GET /api/ai/hydromind?text=hello&model=default
```

Response:

```json
{
  "result": "Hello, how can I help you today?"
}
```

---

## ➕ Adding a New Endpoint

1. Tambahkan folder baru di `api/`
2. Buat file JS route baru
3. Tambahkan entry baru di `views/api.json`

Contoh:

```js
// api/tools/example.js
router.get('/tools/example', (req, res) => {
  res.json({ message: 'Example endpoint' })
})
```

---

## 📖 Live Documentation

API endpoint list tersedia di:

```
GET /api
```

Menampilkan daftar semua endpoint dalam format JSON.

---

## 🛠️ Dev Tools

| Tool       | Kegunaan                       |
|------------|--------------------------------|
| Postman    | API testing GUI                |
| Hoppscotch | Lightweight online API tester |
| Insomnia   | Cross-platform API debugging  |

---

## 💡 Tips

- Gunakan `.env` untuk variabel rahasia
- Gunakan `nodemon` untuk auto-reload:

```bash
npx nodemon index.js
```

---

## 🤝 Contribution

Pull request sangat diterima. Silakan fork dan kembangkan fitur baru atau perbaiki bug.

---

## ⚖️ License

MIT License.

---

<p align="center" style="font-style: italic; color: #888;">
  Built with Express.js • Clean, Modular, and Modern
</p>

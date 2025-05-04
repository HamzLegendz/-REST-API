
<h1 align="center">🚀 Simple Base REST API</h1>
<p align="center">
  Modular Express.js REST API boilerplate built for scalability, performance, and ease of use.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Express.js-4.x-blue.svg" />
  <img src="https://img.shields.io/badge/Node.js-18+-green.svg" />
  <img src="https://img.shields.io/badge/API-ready-yellow.svg" />
  <img src="https://img.shields.io/badge/Made%20by-HamzLegendz-red.svg" />
</p>

---

## 📂 Project Structure

```
simple-api/
├── api/
│   └── ai/
│       └── hydromind.js       # Example API endpoint
├── views/
│   └── api.json               # Endpoint listing for documentation
├── apiMonitor.js              # Logs request success & failure
├── index.js                   # Main server entry point
```

---

## ⚙️ Getting Started

To get started, clone this repository to your local machine and install dependencies:

```bash
git clone https://github.com/yourusername/simple-api.git
cd simple-api
npm install
node index.js
```

Your API server will be running at [http://localhost:3000](http://localhost:3000) by default.

---

## ➕ Menambahkan Endpoint Baru

Adding a new endpoint is super easy. Here’s how you can do it:

1. **Create a new category folder** inside `/api` (e.g., `ai`, `tools`, `media`, etc.):

```bash
mkdir api/ai
```

2. **Add a new file** inside that folder, such as `hydromind.js`, and structure the endpoint like this:

```js
const express = require('express');
const router = express.Router();
const axios = require('axios');
const FormData = require('form-data');
const apiMonitor = require('../../apiMonitor');

router.get('/hydromind', async (req, res) => {
    const { text, model } = req.query;
    if (!text || !model) {
        return res.status(400).json({
            error: 'text and model parameter is required. See supported models: https://mind.hydrooo.web.id'
        });
    }

    try {
        const response = await hydromind(text, model);
        apiMonitor.recordSuccess('/api/ai/hydromind');
        res.json(response);
    } catch (error) {
        apiMonitor.recordFailure('/api/ai/hydromind');
        const statusCode = error.response?.status || 500;
        const errorMessage = error.response?.data?.message || 'Error processing request to HydroMind.';
        res.status(statusCode).json({
            error: errorMessage,
            details: process.env.NODE_ENV === 'development' ? error.message : undefined
        });
    }
});

async function hydromind(content, model) {
    const form = new FormData();
    form.append('content', content);
    form.append('model', model);
    const { data } = await axios.post('https://mind.hydrooo.web.id/v1/chat/', form, {
        headers: {
            ...form.getHeaders(),
        }
    });
    return data;
}

module.exports = router;
```

3. **Update the `/views/api.json` file** with your new endpoint so that it appears in the API documentation:

```json
{
  "status": true,
  "api": [
    {
      "endpoint": "/api/ai/hydromind",
      "method": "GET",
      "description": "AI chatbot using HydroMind API (requires text and model query)"
    }
  ]
}
```

---

## 🔍 Recommended API Testing Tools

These tools make it easier to test and interact with your API endpoints:

- [Postman](https://www.postman.com/) - The most popular tool for API testing and development.
- [Hoppscotch](https://hoppscotch.io/) - A lightweight alternative that runs in the browser.
- [Insomnia](https://insomnia.rest/) - A powerful API client with robust support for environments.

All of these tools let you easily make requests to your API, check responses, and automate tests.

---

## 🧠 Tips Development

- Use **`.env`** files to keep sensitive information like API keys safe.
- Use **`nodemon`** for automatic restarts while developing:

```bash
npx nodemon index.js
```

---

## 🤝 Contributing

We welcome contributions! If you find a bug or want to add a feature, fork the repository, create a new branch, and submit a pull request.

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

> Built with ❤️ using Node.js & Express  
> Style by developer taste + documentation clarity

# Ollama Key Proxy (Rotato) - Render Deploy

## One-click Deploy

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy)

## Manual Deploy

1. Fork/push this repo to GitHub
2. In Render Dashboard → New → Web Service
3. Connect repo, set:
   - **Runtime**: Node
   - **Build Command**: (leave empty)
   - **Start Command**: `node index.js`
4. Add environment variables:
   - `PORT` = `10000`
   - `ADMIN_PASSWORD` = `your-secure-password`
   - `OPENAI_OLLAMA_API_KEYS` = `key1,key2,key3` (comma-separated)
   - `OPENAI_OLLAMA_BASE_URL` = `https://ollama.com/v1`

## Usage

Send requests to `https://your-app.onrender.com/ollama/v1/chat/completions`

```bash
curl https://your-app.onrender.com/ollama/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer anything" \
  -d '{"model": "gpt-oss:120b", "messages": [{"role": "user", "content": "Hello"}]}'
```

Admin panel: `https://your-app.onrender.com/admin`

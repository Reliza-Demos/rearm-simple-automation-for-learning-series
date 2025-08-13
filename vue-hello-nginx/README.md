# Vue 3 Hello World (Vite) + Nginx

Simple Vue 3 app built with Vite and served as static files via Nginx in Docker.

## Local dev

1. Install Node 18+ (or 20+ recommended).
2. Install deps:
   ```bash
   npm install
   ```
3. Run dev server:
   ```bash
   npm run dev
   ```
   Visit http://localhost:5173

## Build

```bash
npm run build
```
Outputs to `dist/`.

## Docker

Build the image:
```bash
docker build -t vue-hello-nginx .
```
Run the container:
```bash
docker run --rm -p 8080:80 vue-hello-nginx
```
Visit http://localhost:8080

## Notes
- Multi-stage Dockerfile builds the app and serves the static `dist/` via `nginx:alpine`.
- `nginx.conf` includes SPA fallback to `index.html` (client-side routing ready).

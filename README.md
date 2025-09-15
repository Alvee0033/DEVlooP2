AmbuGo HackTheAI API (Q1–Q20)

Run locally

- Install Node 20+.
- Install deps and start:

```bash
npm install
npm run start
```

API: http://localhost:3000
Tester UI: open file:///home/alvee/Desktop/New%20Folder%20(1)/tester.html

Docker

- Build:

```bash
docker build -t hacktheai-api .
```

- Run (bind port 3000):

```bash
docker run --name hacktheai-api --rm -p 3000:3000 hacktheai-api
```

Use from another device on the same network

1) Find your host machine IP:

```bash
ip addr show | grep "inet "
```

2) On the other device, open the tester file locally or host it, and set base URL to:

```
http://<HOST_IP>:3000
```

3) If opening the provided tester.html directly on another device, edit the `run()` function base URL or serve the folder and access via HTTP. Example quick static server on host:

```bash
npx serve 
```

Then visit `http://<HOST_IP>:3000` for API and `http://<HOST_IP>:3000` for API calls from the tester (served from its own port, e.g., `http://<HOST_IP>:3001`). Ensure CORS is enabled (already configured).

Health

```bash
curl http://localhost:3000/health
```


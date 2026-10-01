
# WAVE AI 2.0 — Compliance Intelligence Ecosystem Platform        <img width="250" height="250" alt="WAVE AI Fintech logo" img align="right" src="https://github.com/user-attachments/assets/ede0eebb-cfa9-4fb2-bfc2-badd0c2de365" />

> AI-powered financial crime compliance dashboard for the **WIC × Microsoft AI Innovator Apprenticeship (2026)**

## Deliverable 1 — AI Innovation Map Dashboard

Visualizes an AI innovation strategy for banking and financial crime compliance — mapping autonomous AI, human-AI collaboration, human authority, and governance zones across an interactive four-zone dashboard with an ROI opportunities tab.

### Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 19, TypeScript 6, Vite 8 |
| Backend | Node.js (ESM), Express 4 |
| Dev tooling | ESLint 10, Vite proxy, dotenv |

### Project Structure

```
Deliverable1/
├── server/                  # Express.js REST API
│   ├── index.js             # Server entry point
│   └── package.json
└── wave-ai-dashboard/       # React + Vite frontend
    ├── src/
    │   ├── components/
    │   │   └── aiinnovationmap.tsx   # Main dashboard component
    │   └── App.tsx
    └── vite.config.ts       # Dev proxy config
```

### Architecture

- **Backend** (`Deliverable1/server/`): Node.js ESM module, Express 4, CORS locked to `http://localhost:5173`, dotenv for config. Runs on port `3001`.
- **Frontend** (`Deliverable1/wave-ai-dashboard/`): React 19, TypeScript, Vite 8. API calls use Vite's dev proxy — requests to `/api/*` are forwarded to `http://localhost:3001`. No API base URL needed in frontend code.
- **Key component**: `Deliverable1/wave-ai-dashboard/src/components/aiinnovationmap.tsx` — AI Innovation Map with four interactive zones and ROI opportunities tab.

### Getting Started

#### Prerequisites

Ensure Node.js is installed. On corporate/proxy networks, you may need to configure a CA certificate before running `npm install`.

**Option A — CA certificate file:**
```bash
npm config set cafile "C:\path\to\your-ca-bundle.crt"
```

**Option B — Disable strict SSL (trusted networks only):**
```bash
npm config set strict-ssl false
```

**Option C — Per-session environment variable:**
```bash
export NODE_EXTRA_CA_CERTS="C:\path\to\your-ca-bundle.crt"
```

#### Installation & Dev Start

Start the **backend first**, then the frontend in a second terminal.

**Terminal 1 — Backend:**
```bash
cd "Deliverable1/server"
npm install
npm run dev
```

**Terminal 2 — Frontend:**
```bash
cd "Deliverable1/wave-ai-dashboard"
npm install
npm run dev
```

Open `http://localhost:5173` in your browser.

### Environment Variables

`Deliverable1/server/.env` (gitignored):
```
PORT=3001
```

### Scripts

**Backend (`Deliverable1/server/`):**

| Script | Command | Description |
|---|---|---|
| `dev` | `node --watch index.js` | Dev server with auto-restart |
| `start` | `node index.js` | Production start |

**Frontend (`Deliverable1/wave-ai-dashboard/`):**

| Script | Command | Description |
|---|---|---|
| `dev` | `vite` | Dev server with HMR |
| `build` | `tsc -b && vite build` | Type-check + production build |
| `lint` | `eslint .` | Lint all source files |
| `preview` | `vite preview` | Preview production build locally |

### Key Files

| File | Description |
|---|---|
| `Deliverable1/server/index.js` | Express entry point, CORS config, `/api/health` route |
| `Deliverable1/wave-ai-dashboard/vite.config.ts` | Vite config with `/api` proxy to backend |
| `Deliverable1/wave-ai-dashboard/src/components/aiinnovationmap.tsx` | Main dashboard: AI Innovation Map + ROI Opportunities |
| `Deliverable1/wave-ai-dashboard/src/App.tsx` | Root React component |

### License

See [LICENSE](LICENSE).

🚍 TDX Bus ETA: Modern Transit TrackerA high-performance, asynchronous proxy service and reactive frontend for Taiwan's TDX Transport Data.這是為了拯救那些受夠了官方 App 臃腫緩慢的人類而生的。透過 FastAPI 的非同步架構與 Vue 3 的響應式介面，提供極速、無廣告的公車動態查詢體驗。⚡ Key Features (核心功能)🚀 Asynchronous Core: 後端採用 FastAPI + HTTPX，完全非同步處理 TDX API 請求，高併發下依然穩如泰山。🛡️ Type-Safe Architecture: 嚴格的資料流控制，後端資料清洗後直出前端，拒絕 undefined 災難。⚡ Lightning Fast UI: 基於 Vite 建構的 Vue 3 前端，HMR (Hot Module Replacement) 快到讓你忘記什麼是編譯時間。🔄 Smart Proxying: 內建 CORS 處理與資料聚合 (Aggregation)，解決前端直接呼叫 TDX 的跨域與 Token 驗證痛點。📊 Slidev Integration: 內建開發者簡報模式，Code Review 或技術分享隨開隨講。🛠️ Tech Stack (技術堆疊)Backend (The Brain)Framework: FastAPI (ASGI)Runtime: Python 3.10+Dependency Management: pip / venvUtilities: python-dotenv, httpxFrontend (The Face)Framework: Vue 3 (Composition API)Build Tool: ViteNode Version: Node.js 18+🚀 Quick Start (極速啟動)別浪費時間，照著做。1. Environmental Setup你需要先搞定 TDX 的鑰匙。Bash# Backend Config
cp .env.example backend/.env
# 填入你的 TDX_APP_ID 與 TDX_APP_KEY (不要把這個 push 到 git 上，拜託)

# Frontend Config
cp .env.example frontend/.env
2. Ignite the Backend啟動高效能 API 服務。PowerShell# 在專案根目錄
python -m venv .venv
.\.venv\Scripts\activate
pip install -r backend/requirements.txt

cd backend
python app/main.py
# Server is now listening on http://localhost:8000 🚀
3. Launch the Frontend啟動現代化 UI。PowerShell# 開一個新的 terminal
cd frontend
npm install
npm run dev -- --host
# UI is live at http://localhost:5173 ✨
🔌 API Endpoints後端不只是轉發，還幫你做了髒活（資料正規化）。MethodEndpointDescriptionGET/api/routes/{route}/eta取得原始 ETA 資料 (Proxy /v2/Bus/EstimatedTimeOfArrival)GET/api/routes/{route}/stops取得原始站序資料 (Proxy /v2/Bus/StopOfRoute)GET/api/routes/{route}/stop-etas🔥 Killer Feature: 自動合併「站序」與「預估時間」，前端直接渲染即可Query Param: ?city=Taipei (Default)Supported Cities: Taipei, NewTaipei, Taoyuan, Taichung, Tainan, Kaohsiung ...📂 Project Structure乾淨的架構是工程師的尊嚴。Plaintexttdx-bus-demo/
├── backend/            # Python FastAPI Service
│   ├── app/
│   │   ├── main.py     # Application Entry Point
│   │   └── ...
│   └── requirements.txt
├── frontend/           # Vue 3 + Vite Application
│   ├── src/
│   └── ...
├── slidev/             # Developer Presentation (Markdown based)
└── .github/            # CI/CD & Templates
⚠️ Disclaimer本專案使用交通部 TDX 運輸資料流通服務平臺 API。請勿濫用 API 額度，若因頻繁請求導致 IP 被 Ban，請自行負責。This tool is provided "as is" without warranty of any kind.
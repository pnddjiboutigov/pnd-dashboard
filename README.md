# PND Command Center

Police Nationale de Djibouti - Command Center Dashboard

## Files

| File | Description |
|------|-------------|
| `server.js` | Hono backend server with REST API + static file serving |
| `package.json` | Dependencies: hono + @hono/node-server only |
| `public/index.html` | Complete dashboard (React + Chart.js) |
| `public/logo.jpg` | PND emblem |
| `logo.jpg` | PND emblem (root copy) |

## Dashboard Pages

1. **Dashboard** - KPI cards, recent reports, accident hotspots
2. **Accident Reports** - Full report list with filters, view/approve/delete
3. **Daily Reports** - Day-specific report analysis with charts
4. **Weekly Reports** - Week view with daily distribution chart
5. **Monthly Reports** - Month view with daily bar chart
6. **Officers** - CRUD management with auth codes
7. **Analytics** - Time series, by type, weather, road condition charts
8. **Audit Log** - Complete action history
9. **Settings** - System configuration

## Deploy to Render

1. Upload all files to your GitHub repo `pnddjibouti/pnddjibouti`
2. In Render dashboard, create new Web Service
3. Connect to your GitHub repo
4. Settings:
   - **Runtime**: Node
   - **Build Command**: `npm install`
   - **Start Command**: `node server.js`
5. Click Deploy

## Login

- Password: `admin2025`

## API Endpoints

- `GET /api/officers` - List active officers (for mobile app)
- `POST /api/auth/login` - Officer login with badge + auth code
- `POST /api/reports` - Submit report (from mobile app)
- `GET /api/trpc/*` - Dashboard data endpoints

## Mobile App Connection

The mobile app should connect to:
- `https://your-render-url.onrender.com/api/auth/login`
- `https://your-render-url.onrender.com/api/reports`

Replace `your-render-url` with your actual Render service URL.

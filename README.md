# 🤖 Moltbot Monitor Dashboard

> Real-time monitoring dashboard for Clawdbot/Moltbot Discord bot. Track system resources, bot status, GPU usage, and logs with a beautiful Next.js interface.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Node.js](https://img.shields.io/badge/node-%3E%3D18.0.0-green.svg)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue.svg)

## ✨ Features

- 📊 **Real-time Monitoring**: CPU, RAM, GPU usage updated every 5 seconds
- 🤖 **Bot Status**: Track Clawdbot online/offline status and uptime
- 📝 **Live Logs**: View latest bot logs with color-coded error highlighting
- 🔄 **Remote Control**: Restart bot directly from dashboard
- 📱 **Responsive Design**: Works on desktop and mobile devices
- 🎨 **Modern UI**: Built with Next.js 15, TypeScript, and Tailwind CSS

## 🏗️ Project Structure

```
moltbot-monitor/
├── api/                    # Backend Express API
│   ├── monitor-server.js   # Main monitoring server
│   └── package.json        # API dependencies
├── dashboard/              # Frontend Next.js app
│   ├── app/                # Next.js App Router pages
│   ├── components/         # React components
│   ├── lib/                # API client utilities
│   └── types/              # TypeScript type definitions
└── README.md               # This file
```

## 🚀 Quick Start

### Prerequisites

- Node.js 18+ and npm
- Clawdbot/Moltbot installed and running
- WSL2 (for Linux environment on Windows)

### Installation

#### 1. Clone the repository

```bash
git clone https://github.com/Tim2840/moltbot-monitor.git
cd moltbot-monitor
```

#### 2. Setup Backend API (WSL2/Linux)

```bash
cd api
npm install

# Start the monitoring server
node monitor-server.js

# OR use PM2 for production
npm install -g pm2
pm2 start monitor-server.js --name moltbot-monitor
pm2 save
```

The API will run on `http://localhost:3001`

#### 3. Setup Frontend Dashboard (Windows/Linux)

```bash
cd dashboard
npm install

# Start development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser 🎉

## 📡 API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/health` | GET | System health and bot status |
| `/api/gpu` | GET | GPU information (AMD/NVIDIA) |
| `/api/logs` | GET | Latest 50 bot logs |
| `/api/status` | GET | Clawdbot detailed status |
| `/api/models` | GET | Model configuration status |
| `/api/restart` | POST | Restart the bot |

## 🛠️ Tech Stack

### Backend
- **Express.js** - Fast, minimalist web framework
- **systeminformation** - Hardware and OS information library
- **PM2** - Production process manager

### Frontend
- **Next.js 15** - React framework with App Router
- **TypeScript** - Type-safe development
- **Tailwind CSS** - Utility-first CSS framework
- **Recharts** - Charting library for data visualization
- **Lucide React** - Beautiful icon library

## 📸 Screenshots

### Dashboard Overview
![Dashboard](https://via.placeholder.com/800x450?text=Dashboard+Preview)

*Real-time monitoring of system resources and bot status*

### Live Logs Viewer
![Logs](https://via.placeholder.com/800x450?text=Logs+Viewer)

*Color-coded log viewer with auto-refresh*

## 🔧 Configuration

### API Port

Edit `api/monitor-server.js`:

```javascript
const PORT = 3001; // Change to your preferred port
```

### Dashboard API URL

Edit `dashboard/lib/api.ts`:

```typescript
const API_BASE_URL = 'http://localhost:3001/api';
```

### Auto-refresh Interval

Edit `dashboard/app/page.tsx`:

```typescript
const interval = setInterval(fetchData, 5000); // 5 seconds
```

## 📋 Todo List

- [ ] Add historical data charts (CPU/Memory trends)
- [ ] Discord webhook notifications for errors
- [ ] Model switching interface
- [ ] Authentication system
- [ ] Docker deployment support
- [ ] Mobile app version

## 🐛 Troubleshooting

### API Connection Failed

```bash
# Check if monitor server is running
pm2 status

# View logs
pm2 logs moltbot-monitor
```

### CORS Error

Make sure `cors` is installed and configured in `monitor-server.js`:

```javascript
const cors = require('cors');
app.use(cors());
```

### Clawdbot Commands Not Found

```bash
# Verify clawdbot installation
which clawdbot

# Check status manually
clawdbot status
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**郭宣廷 (Guo Xuan-Ting)**
- GitHub: [@Tim2840](https://github.com/Tim2840)
- Learning: Frontend Development (React, Next.js, TypeScript)

## 🙏 Acknowledgments

- [Clawdbot](https://github.com/clawdbot/clawdbot) - The amazing AI bot framework
- [Next.js](https://nextjs.org/) - The React framework for production
- [Tailwind CSS](https://tailwindcss.com/) - For the beautiful UI

---

⭐ If you find this project helpful, please give it a star!

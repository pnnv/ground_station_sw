# CanSat Groundstation Visualizer

A modern web-based groundstation for visualizing and monitoring telemetry data from a CanSat or similar aerospace payload. This project features a real-time dashboard built with React, TypeScript, and Vite, and a Python Flask backend for serving telemetry data.

## Features

- 📡 **Live Telemetry Table:** View the latest received data including altitude, pressure, temperature, voltage, GPS, and more.
- 📈 **Real-Time Charts:** Visualize key metrics (altitude, temperature, voltage, pressure, tilt, rotation) as they update.
- 🛰️ **Status Header:** See connection status and last update time.
- 🗂️ **Modern UI:** Responsive, clean interface using shadcn/ui and Radix UI components.
- 🔌 **Backend API:** Python Flask server reads the latest telemetry from `telemetry.csv` and serves it via a REST API.

## Project Structure

```
.
├── server.py           # Flask backend serving telemetry API
├── simulation.py       # (Optional) Simulates telemetry data
├── telemetry.csv       # Telemetry data file (CSV)
├── src/                # React frontend (TypeScript, Vite)
│   ├── components/     # UI components (Sidebar, TelemetryTable, Charts, etc.)
│   ├── pages/          # Main dashboard page
│   └── ...             # Hooks, utils, styles
├── public/             # Static assets
├── package.json        # Frontend dependencies & scripts
├── requirements.txt    # Backend dependencies
└── README.md           # Project documentation
```

## Getting Started

### Prerequisites

- **Node.js** (v18+ recommended)
- **Python** (3.8+ recommended)
- **pip** (for Python dependencies)

### 1. Install Frontend Dependencies

```sh
npm install
```

### 2. Install Backend Dependencies

```sh
pip install -r requirements.txt
```

### 3. Run the Backend Server

```sh
python server.py
```

- The Flask server will serve the API at `http://localhost:5000/api/telemetry`.

### 4. Run the Frontend (Development)

```sh
npm run dev
```

- The React app will be available at `http://localhost:8080`.

### 5. Open the Dashboard

Visit [http://localhost:8080](http://localhost:8080) in your browser.

## Telemetry Data Format

The backend expects a `telemetry.csv` file with the following columns (in order):

- Team_Id, TimeStamp, PacketCount, Altitude, Pressure, Temperature, Voltage, GpsTime, GpsLatitude, GpsLongitude, GpsAltitude, GpsSats, a_x, a_y, a_z, gyro_x, gyro_y, gyro_z, FSW_State, AngleX, AngleY, AngleZ

## Customization

- **UI Components:** Located in `src/components/` and `src/components/ui/`.
- **API Endpoint:** Configured in `src/pages/Index.tsx` (`/api/telemetry`).
- **Telemetry Fields:** Update `TelemetryData` interface in `src/pages/Index.tsx` as needed.

## Scripts

- `npm run dev` – Start frontend in development mode
- `npm run build` – Build frontend for production
- `npm run preview` – Preview production build
- `python server.py` – Start backend server

## License

MIT

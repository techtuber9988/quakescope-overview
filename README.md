# Quakescope 🌍

> An interactive earthquake monitoring dashboard that transforms global seismic data into an understandable visual experience.

[![Live Demo](https://img.shields.io/badge/Live-Demo-0ea5e9?style=for-the-badge)](https://quakescope-overview.vercel.app)
[![React](https://img.shields.io/badge/React-19-61dafb?style=for-the-badge&logo=react)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-Build%20Tool-646cff?style=for-the-badge&logo=vite)](https://vite.dev/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

## 🔗 Project Links

- **Live Application:** https://quakescope.vercel.app/
- **GitHub Repository:** https://github.com/techtuber9988/quakescope

---

## 📌 Overview

Quakescope is a web-based earthquake monitoring application built with React and Vite.

It integrates the USGS Earthquake Catalog API to retrieve earthquake data and presents that information through an interactive map, filtering controls, and event-detail views.

The goal of the project is to make seismic information easier to discover, explore, and understand without requiring users to interpret raw API responses manually.

Quakescope is a monitoring and visualization tool. It does **not** predict earthquakes or replace official emergency information.

---

## 🎯 Problem Statement

Earthquake data is publicly available through APIs, but raw seismic datasets can be difficult for non-technical users to interpret.

Users may struggle to:

- Identify where earthquakes have occurred
- Compare events by magnitude
- Filter events by time
- Understand individual event information
- Interpret geographic data without visual context

Quakescope addresses these challenges through an interactive dashboard that combines data retrieval, map visualization, filtering, and event details.

---

## ✨ Features

### 🌍 Interactive Earthquake Map

- Displays earthquake locations on an interactive map
- Uses Leaflet and React-Leaflet for geographic visualization
- Allows users to explore the spatial distribution of earthquake events

### 🎚️ Dynamic Filtering

- Filter earthquake events by magnitude
- Filter results using a time window
- Refresh displayed data according to selected criteria

### 📊 Earthquake Information

- View individual earthquake details
- Display magnitude and geographic coordinates
- Present available significance and alert information
- Inspect the location and metadata of selected events

### ⚠️ Error and Loading States

- Handles API loading states
- Provides feedback for network failures
- Handles empty result sets
- Uses request timeout and retry behavior where implemented

### ♿ Accessibility and Responsive Design

- Responsive interface for different screen sizes
- Keyboard-navigable interactive controls
- Visible focus states
- Clear interface structure and readable visual hierarchy

---

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| React 19 | Component-based frontend development |
| Vite | Development server and production build tool |
| JavaScript | Application logic and data handling |
| Tailwind CSS v4 | Styling and responsive UI |
| Leaflet | Interactive maps |
| React-Leaflet | React integration for Leaflet |
| USGS Earthquake Catalog API | Earthquake data source |
| Vercel | Deployment and hosting |

---

## 🧩 How the Application Works

The application follows this general workflow:

```text
User opens Quakescope
        ↓
Frontend requests earthquake data
        ↓
USGS Earthquake Catalog API returns GeoJSON
        ↓
React processes and stores the response
        ↓
Earthquake events are displayed on the map
        ↓
User applies magnitude/time filters
        ↓
Filtered results and event details are displayed
```

### Data Flow

1. The application sends a request to the USGS Earthquake Catalog API.
2. The API returns earthquake information in GeoJSON format.
3. React receives and stores the earthquake data in the application state.
4. The data is processed and displayed on the interactive Leaflet map.
5. Users can filter earthquakes according to magnitude and time range.
6. The filtered results update the map, statistics, and earthquake list.
7. Selecting an earthquake displays detailed information such as magnitude, location, coordinates, depth, and event time.

---

## Project Structure

```text
quakescope/
├── public/
│   └── assets/
├── src/
│   ├── components/
│   │   ├── Map/
│   │   ├── Navbar/
│   │   ├── Filters/
│   │   ├── EarthquakeList/
│   │   └── EarthquakeDetails/
│   ├── pages/
│   ├── hooks/
│   ├── utils/
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
├── package.json
├── package-lock.json
├── vite.config.js
├── index.html
└── README.md
```

> The exact folder structure may vary depending on the latest implementation.

---

## Prerequisites

Before running Quakescope locally, make sure the following software is installed:

- Node.js version 18 or higher
- npm, which is included with Node.js
- Git
- A modern web browser such as Google Chrome, Microsoft Edge, Firefox, or Safari
- An active internet connection because earthquake data is fetched from the USGS API

Node.js 20 LTS is recommended for the best compatibility.

You can verify the installed versions using:

```bash
node -v
npm -v
git --version
```

---

## Installation

Follow these steps to run the project locally.

### 1. Clone the Repository

```bash
git clone https://github.com/techtuber9988/quakescope.git
```

### 2. Navigate to the Project Directory

```bash
cd quakescope
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Start the Development Server

```bash
npm run dev
```

After starting the development server, Vite will provide a local URL similar to:

```text
http://localhost:5173
```

Open this URL in your browser to access the application.

---

## Quick Start

Run the following commands in your terminal:

```bash
git clone https://github.com/techtuber9988/quakescope.git
cd quakescope
npm install
npm run dev
```

The application will be available at the local development URL shown in the terminal.

---

## Environment Variables

Quakescope currently uses the public USGS Earthquake Catalog API.

No API key is required for the current implementation.

### Environment Variable Status

| Variable | Required | Description |
|----------|----------|-------------|
| None | No | The application directly uses the public USGS Earthquake Catalog API. |

Therefore, creating a `.env` file is not required for the current version of the project.

### API Source

The application obtains earthquake data from:

```text
https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/all_day.geojson
```

The API provides publicly available earthquake information in GeoJSON format.

> If the API URL is moved into an environment variable in a future version, the variable should be documented here. For example, a Vite environment variable would normally use the `VITE_` prefix.

---

## Using the Application

### 1. View Earthquake Activity

When the application loads, it fetches recent earthquake data from the USGS API and displays the events on the dashboard.

### 2. Explore the Interactive Map

The map displays earthquake locations using map markers.

Users can:

- Zoom in and out
- Move around the map
- View earthquake locations
- Select individual earthquake markers
- Inspect event information

### 3. Apply Filters

Users can filter earthquake events based on:

- Magnitude
- Time range
- Other available filtering controls

The map and earthquake list update according to the selected filters.

### 4. View Earthquake Details

Selecting an earthquake displays information such as:

- Magnitude
- Location
- Latitude
- Longitude
- Depth
- Event time
- Significance
- USGS event link

### 5. Handle Loading and Errors

The application displays appropriate states while:

- Data is loading
- No earthquakes match the selected filters
- The API request fails
- The external service is unavailable

---

## Testing and Verification

After starting the project, verify the following functionality:

- The application loads without errors.
- Earthquake data is displayed.
- The interactive map renders correctly.
- Earthquake markers appear on the map.
- Magnitude filters work correctly.
- Time filters update the displayed results.
- Selecting an earthquake displays its details.
- Loading states appear while data is being fetched.
- Error messages appear if the API request fails.
- Empty states appear when no events match the filters.
- The layout works on desktop, tablet, and mobile screens.
- Navigation and interactive controls are usable with a keyboard.

### Create a Production Build

To create an optimized production build, run:

```bash
npm run build
```

### Preview the Production Build

To preview the production build locally, run:

```bash
npm run preview
```

### Run Linting

If ESLint is configured in the project, run:

```bash
npm run lint
```

> The available commands depend on the scripts defined in `package.json`.

You can view all available scripts using:

```bash
npm run
```

---

## Available Commands

| Command | Description |
|---------|-------------|
| `npm install` | Installs project dependencies |
| `npm run dev` | Starts the Vite development server |
| `npm run build` | Creates a production build |
| `npm run preview` | Previews the production build locally |
| `npm run lint` | Checks the code using ESLint, if configured |

---

## Deployment

Quakescope can be deployed using platforms that support Vite applications, such as Vercel, Netlify, or GitHub Pages with suitable configuration.

### Deployment Using Vercel

1. Open the Vercel dashboard.
2. Import the GitHub repository.
3. Select the `quakescope` repository.
4. Configure the project using the following settings:

| Setting | Value |
|---------|-------|
| Framework Preset | Vite |
| Install Command | `npm install` |
| Build Command | `npm run build` |
| Output Directory | `dist` |

5. Click **Deploy**.
6. Wait for the build to complete.
7. Open the generated deployment URL.

### Live Demo

The deployed application is available at:

https://quakescope.vercel.app/

---

## Data Limitations and Reliability

Quakescope depends on data provided by the USGS Earthquake Catalog API. Therefore, the application is affected by the availability, response time, and accuracy of the external API.

Important limitations include:

- Earthquake data depends on the USGS API.
- The application cannot display data when the API is unavailable.
- Earthquake information may be revised by the data provider.
- Some events may have incomplete location or depth information.
- API response time depends on network conditions.
- The number of displayed events depends on the selected API feed and response.
- Data is not guaranteed to represent every seismic event worldwide in real time.
- Earthquake information may be delayed or updated after the initial report.
- The application does not predict future earthquakes.

The application is intended for educational and informational purposes. It should not be used as a replacement for official emergency alerts, scientific monitoring systems, or public safety services.

---

## Out of Scope

The following features are not included in the current version:

- User authentication
- User profiles
- Saved earthquake searches
- Personalized dashboards
- Email notifications
- Push notifications
- SMS alerts
- Real-time WebSocket streaming
- Earthquake prediction
- Earthquake forecasting
- Advanced seismic trend analysis
- Historical data analytics over unlimited time periods
- Emergency warning functionality
- Offline earthquake data access
- Administrative controls
- User-generated earthquake reports

These features may be considered for future versions.

---

## Known Limitations

The current version has the following known limitations:

1. The application requires an internet connection to fetch earthquake data.
2. The application depends on the availability of the USGS API.
3. Data updates depend on the selected USGS feed and its refresh frequency.
4. Some earthquake events may contain incomplete information.
5. The application does not provide earthquake predictions.
6. The map requires an external map tile provider to load map tiles.
7. Large datasets may affect browser performance.
8. The application is designed for monitoring and visualization rather than professional seismic analysis.
9. The current version does not provide user accounts or saved preferences.
10. The application does not send emergency notifications.

---

## Technical Decisions

### React

React was selected because it supports component-based development and makes it easier to manage dynamic earthquake data, filters, map interactions, and UI updates.

### Vite

Vite was selected because it provides:

- Fast development startup
- Fast hot module replacement
- Efficient production builds
- Simple configuration
- Good compatibility with modern React applications

### Tailwind CSS

Tailwind CSS was used to create a responsive and consistent interface using utility classes. It also helps maintain spacing, typography, colors, and responsive layouts efficiently.

### Leaflet and React-Leaflet

Leaflet was selected because it is lightweight, open-source, and suitable for interactive maps.

React-Leaflet provides React components for integrating Leaflet maps into a React application.

### USGS Earthquake Catalog API

The USGS API was selected because it provides publicly available earthquake data from a trusted geological organization.

Advantages include:

- Public accessibility
- No API key requirement for the selected feed
- GeoJSON support
- Regularly updated earthquake information
- Useful event metadata

### Client-Side Filtering

Client-side filtering was selected because the application works with the earthquake data already fetched from the API. This allows filters to update the interface quickly without making a new API request for every interaction.

### Trade-Offs

The selected architecture provides a simple and responsive user experience, but it also has limitations:

- Client-side filtering may become less efficient with very large datasets.
- The application depends on external API availability.
- Public API data may have rate limits or usage restrictions.
- Advanced backend processing is not included.
- The current application is not designed for large-scale production monitoring.

---

## Security and Privacy

Quakescope does not require user registration or authentication.

The application does not intentionally collect:

- User passwords
- Personal profiles
- Payment information
- Private user data
- User-generated personal records

The application primarily requests publicly available earthquake data from the USGS API.

Users should still review the privacy policies of the hosting provider, map tile provider, and external API provider when deploying or using the application.

---

## Future Improvements

Possible future improvements include:

- Real-time earthquake updates
- WebSocket-based data streaming
- Advanced filtering options
- Historical earthquake analysis
- Data visualization charts
- Magnitude and depth statistics
- Earthquake clustering
- User-selected geographic regions
- Saved filters and preferences
- Email or push notifications
- PWA support
- Offline support
- Improved accessibility
- Dark and light theme customization
- Backend caching
- Automated testing
- Performance optimization for large datasets

---

## License

This project is created for educational and demonstration purposes.

If a specific open-source license is added to the repository, update this section accordingly.

---

## Author

**Ayush Tripathi**

- GitHub: https://github.com/techtuber9988
- Project Repository: https://github.com/techtuber9988/quakescope
- Live Demo: https://quakescope.vercel.app/

---

## Project Summary

Quakescope is a real-time earthquake monitoring dashboard built with React, Vite, Tailwind CSS, Leaflet, and the USGS Earthquake Catalog API.

The project focuses on transforming earthquake data into an interactive and understandable interface. Users can explore earthquake locations on a map, filter events based on magnitude and time, and inspect detailed information about individual earthquakes.

The project demonstrates the use of:

- React component architecture
- API integration
- GeoJSON data handling
- Interactive maps
- Client-side filtering
- Responsive UI development
- Loading and error-state handling
- Modern frontend development tools
- Deployment using Vercel
````

# ♿ Wheelchair Accessibility Map

A real-time, interactive mapping application designed to help users identify and contribute wheelchair-accessible locations. This project leverages the **Overpass API (OpenStreetMap)** to fetch accessibility data and **Leaflet.js** for a smooth, responsive map interface. 

Currently, the core logic is implemented in vanilla JavaScript (`app.js`), but the project is configured as a **Next.js** application with **Tailwind CSS**, **Radix UI**, and **Supabase** dependencies ready for modern full-stack development.

## 🌟 Features

* **Real-time Geolocation:** Automatically centers the map on the user's current position to show nearby accessible spots.
* **Overpass API Integration:** Fetches "live" accessibility data directly from OpenStreetMap, including ramps, elevators, and accessible toilets.
* **Custom Map Markers:** Uses Font Awesome icons to clearly designate accessible points on the map.
* **Interactive Info Panel:** Displays a summary of results and detailed information when a marker is clicked.
* **Crowdsourced Contributions:** Allows users to manually "Add Missing Points" through a custom modal form (currently simulated for frontend demonstration).
* **Mobile Responsive:** A clean UI that adapts to both desktop and mobile screens.

## 🛠️ Tech Stack

* **Frontend:** HTML5, CSS3, JavaScript (ES6+)
* **Framework Framework/Environment:** Next.js 15, React 19
* **Mapping:** Leaflet.js & React-Google-Maps (configured)
* **Data Source:** OpenStreetMap via Overpass API
* **Styling:** Tailwind CSS
* **UI Components:** Radix UI, Tabler Icons, Lucide React
* **Backend Ready:** Supabase configured in dependencies

## 🚀 Getting Started

### Prerequisites

* [Node.js](https://nodejs.org/) (v18 or higher recommended)
* npm, yarn, or pnpm

### Installation

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/asl-accessibility-map.git](https://github.com/your-username/asl-accessibility-map.git)
   cd asl-accessibility-map

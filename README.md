# ♿ EYE-LINK: Wheelchair Accessibility Map

<div align="center">

**Making the world more accessible—one location at a time.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Next.js](https://img.shields.io/badge/Next.js-15.1-000?logo=next.js)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19.0-61DAFB?logo=react)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6?logo=typescript)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-3.4-06B6D4?logo=tailwindcss)](https://tailwindcss.com/)
[![Open Source](https://img.shields.io/badge/Open%20Source-Yes-brightgreen)](#contributing)
[![Platform](https://img.shields.io/badge/Platform-JavaScript%20%2F%20TypeScript-F7DF1E?logo=javascript)](#tech-stack)

</div>

---

## 🎯 Overview

**EYE-LINK** is a cutting-edge, real-time interactive mapping application designed to empower wheelchair users and accessibility advocates by identifying and contributing wheelchair-accessible locations in their communities. 

Leveraging the power of **OpenStreetMap** via the **Overpass API**, EYE-LINK provides live accessibility data including accessible ramps, elevators, wheelchair-friendly entrances, and accessible restrooms. The platform combines geolocation services with crowdsourced contributions, creating a dynamic, community-driven accessibility database that grows stronger with every user.

### 🤔 The Problem

Navigating the world as a wheelchair user remains challenging. Existing maps lack comprehensive, real-time accessibility information. Finding accessible routes, entrances, and facilities requires extensive research, often leaving users stranded or frustrated.

### ✨ The Solution

EYE-LINK democratizes accessibility information by:
- **Aggregating** real-time data from OpenStreetMap
- **Visualizing** accessible locations with intuitive markers and popups
- **Enabling** community contributions through crowdsourced point submissions
- **Providing** mobile-responsive access from any device
- **Reducing** time spent searching for accessible routes and facilities

---

## 🌟 Key Features

✅ **Real-Time Geolocation Detection**
   - Automatically centers the map on your current location
   - Seamless GPS integration for instant context

✅ **Live Accessibility Data Integration**
   - Direct connection to OpenStreetMap's Overpass API
   - Queries for wheelchair-accessible facilities (ramps, elevators, toilets, etc.)
   - Configurable search radius (1–2 km and beyond)

✅ **Intelligent Marker System**
   - Custom wheelchair icons for clear visual identification
   - Color-coded accessibility levels (Full Access / Limited Access)
   - Categorized amenities (entrances, parking, restrooms)

✅ **Interactive Information Panels**
   - Click markers to view detailed facility information
   - Displays amenity type, accessibility level, and user notes
   - Real-time result summaries and count statistics

✅ **Crowdsourced Contributions**
   - "Add Missing Accessibility Point" feature
   - Modal form for detailed point submission
   - Support for multiple accessibility categories
   - User-friendly annotation system for facility details

✅ **Mobile-First Responsive Design**
   - Optimized for desktop, tablet, and mobile devices
   - Touch-friendly interactions
   - Adaptive layout for smaller screens

✅ **Modern Web Technology Stack**
   - Next.js 15 for server-side rendering
   - React 19 for component-based UI
   - TypeScript for type safety and developer experience
   - Tailwind CSS for rapid, consistent styling

---

## 🛠️ Tech Stack

### **Frontend Architecture**

| Category | Technology | Version | Purpose |
|----------|-----------|---------|---------|
| **Framework** | Next.js | 15.1.7 | Server-side rendering, routing, optimization |
| **UI Library** | React | 19.0.0 | Component-based UI development |
| **Language** | TypeScript / JavaScript | 5.0 / ES6+ | Type-safe, modern code |
| **Styling** | Tailwind CSS | 3.4.1 | Utility-first CSS framework |
| **Styling** | PostCSS | 8.0 | CSS transformation and plugins |

### **UI Component Libraries**

| Library | Version | Components |
|---------|---------|-----------|
| Radix UI | 1.2.x | Accordion, Avatar, Checkbox, Dropdown, Label, Navigation, Popover, Select, Slot, Switch, Tabs, Tooltip |
| Tabler Icons | 3.30.0 | Icon library for accessibility and UI |
| Lucide React | 0.475.0 | Modern, customizable icon set |
| React Icons | 5.4.0 | Comprehensive icon collection |

### **Mapping & Geolocation**

| Library | Version | Purpose |
|---------|---------|---------|
| Leaflet.js | 1.9.4 | Interactive mapping library |
| React-Google-Maps | 2.20.6 | Google Maps integration |
| Leaflet Routing Machine | 3.2.12 | Route calculation and visualization |
| @googlemaps/js-api-loader | 1.16.8 | Google Maps API loader |

### **Data & Backend**

| Service | Version | Purpose |
|---------|---------|---------|
| Supabase Auth | 0.10.0 | Authentication and user management |
| Supabase SSR | 0.5.2 | Server-side rendering support |
| Supabase JS Client | 2.48.1 | Database and real-time API |
| **External API** | Overpass API | Live accessibility data from OpenStreetMap |

### **Utilities & Enhancement**

| Package | Version | Purpose |
|---------|---------|---------|
| Framer Motion | 12.4.3 | Smooth animations and transitions |
| Canvas Confetti | 1.9.3 | Celebration animations |
| Date-fns | 4.1.0 | Date manipulation and formatting |
| clsx | 2.1.1 | Conditional class name merging |
| Tailwind Merge | 3.0.1 | Tailwind CSS class merging |
| Sonner | 1.7.4 | Toast notifications |
| Geist Font | 1.3.1 | Premium typography |

### **Development Tools**

| Tool | Version |
|------|---------|
| Node.js | 18+ (recommended) |
| Package Manager | npm, yarn, or pnpm |
| Type Checking | TypeScript 5.0 |

---

## 🏗️ System Architecture

### **High-Level Data Flow**

```
User Browser (Client-Side)
    ↓
[Geolocation API] → Determine user's latitude/longitude
    ↓
[Leaflet.js] → Initialize map with OpenStreetMap tiles
    ↓
[Overpass API Query] → POST accessibility query with coordinates
    ↓
[OpenStreetMap Database] → Returns wheelchair-accessible nodes/ways/relations
    ↓
[Data Processing] → Parse elements, extract tags, format data
    ↓
[Marker Rendering] → Create custom icons and add to map layer
    ↓
[Interactive Popups] → Display facility details on marker click
    ↓
[User Interaction] → Add new points or explore existing locations
```

### **Component Breakdown**

1. **Map Initialization Module** (`app.js` - Core Logic)
   - Initializes Leaflet map with OpenStreetMap base layer
   - Implements geolocation detection fallback
   - Manages layer groups for accessibility markers

2. **Accessibility Data Fetcher**
   - Constructs Overpass API queries with dynamic coordinates and radius
   - Handles POST requests to Overpass interpreter
   - Error handling with user-friendly messages

3. **Data Processor**
   - Parses API responses for relevant elements
   - Extracts tags (name, amenity, accessibility level, entrance type)
   - Formats data for marker creation

4. **Marker System**
   - Custom Leaflet `divIcon` with Font Awesome wheelchair icons
   - Color-coded based on accessibility level
   - Configurable icon anchors and popup positioning

5. **User Contribution Form**
   - Modal-based UI for adding new accessibility points
   - Form validation (name, type, accessibility level, notes)
   - Client-side storage (ready for backend integration)

6. **Next.js Application Structure**
   - TypeScript configuration for type safety
   - Tailwind CSS configuration with custom themes
   - Middleware for potential authentication flows (Supabase integration)

### **API Integration Points**

- **Overpass API**: `https://overpass-api.de/api/interpreter`
  - Query Format: OpenStreetMap Query Language (OQL)
  - Response Format: JSON with elements array
  - Search Parameters: Wheelchair tags, geospatial radius, element types

- **Geolocation API**: Browser native
  - High accuracy GPS data
  - Fallback to default location on permission denial

---

## 🚀 Getting Started

### **Prerequisites**

Before you begin, ensure you have the following installed:

- **Node.js** (v18 or higher) – [Download](https://nodejs.org/)
- **npm**, **yarn**, or **pnpm** – Comes with Node.js or install separately
- **Git** – [Download](https://git-scm.com/)
- **A modern web browser** – Chrome, Firefox, Safari, or Edge (recommended)
- **Code Editor** – VS Code, WebStorm, or your favorite editor

### **Installation & Setup**

#### **Step 1: Clone the Repository**

```bash
git clone https://github.com/RITESH2127/EYE-LINK-PROJECT.git
cd EYE-LINK-PROJECT
```

#### **Step 2: Install Dependencies**

Using **npm**:
```bash
npm install
```

Or using **yarn**:
```bash
yarn install
```

Or using **pnpm** (fastest):
```bash
pnpm install
```

#### **Step 3: Configure Environment Variables** (if needed)

Create a `.env.local` file in the root directory for any external service credentials:

```env
# Example: If using Supabase
# NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
# NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anon-key

# Example: If using Google Maps
# NEXT_PUBLIC_GOOGLE_MAPS_API_KEY=your-google-maps-api-key
```

#### **Step 4: Run the Development Server**

```bash
npm run dev
```

The application will be available at `http://localhost:3000` (default Next.js port).

#### **Step 5: Open in Browser**

Navigate to `http://localhost:3000` and grant location permissions when prompted.

### **Alternative: Build for Production**

To create an optimized production build:

```bash
npm run build
npm run start
```

---

## 📖 Usage

### **Basic Usage**

1. **Allow Location Access**
   - Grant browser permission to access your geolocation
   - The map automatically centers on your location

2. **Explore Accessible Locations**
   - The map displays wheelchair-accessible facilities with wheelchair icons
   - Zoom in/out using your mouse wheel or touch gestures
   - Pan the map by clicking and dragging

3. **View Facility Details**
   - Click any wheelchair marker to open a popup
   - View facility name, accessibility level, type, and additional notes
   - Close the popup by clicking the X button

4. **Add a New Accessibility Point**
   - Click the **"Add Missing Accessibility Point"** button
   - The map cursor changes to a crosshair
   - Click on the map to place a new marker
   - Fill out the form with:
     - **Name/Description** of the facility
     - **Type** (Entrance, Ramp, Elevator, Toilet, Parking, Other)
     - **Accessibility Level** (Full Access / Limited Access)
     - **Additional Notes** (optional)
   - Click **"Save Point"** to add it to the map
   - Click **"Cancel"** to exit add mode

### **Code Examples**

#### **Accessing the Map**

```javascript
// The map object is globally available
let currentZoom = map.getZoom();
map.setView([lat, lon], 15); // Center on coordinates at zoom level 15
```

#### **Querying Accessibility Data**

```javascript
// Fetch accessibility data for a specific radius
fetchAccessibilityData(51.505, -0.09, 2); // Latitude, Longitude, Radius in km
```

#### **Creating Custom Markers**

```javascript
const customIcon = L.divIcon({
  className: "accessibility-icon",
  html: '<i class="fas fa-wheelchair" style="font-size: 24px; color: #1e88e5;"></i>',
  iconSize: [30, 30],
  iconAnchor: [15, 15],
  popupAnchor: [0, -15],
});

const marker = L.marker([lat, lon], { icon: customIcon }).addTo(map);
```

### **Expected Output**

**On successful data fetch:**
```
Found 15 wheelchair accessible location(s).
Click on markers to view details.
```

**On marker click:**
```
Wheelchair Accessible Entrance
Accessibility: Full Access
Type: Entrance
Location ID: 12345678
```

**On add point submission:**
```
[New marker appears on map with popup]
"Library Ramp - User-added point (not yet in OpenStreetMap)"
```

### **Screenshots / Visual Placeholders**

```
┌─────────────────────────────────────────────────┐
│  🗺️  Wheelchair Accessibility Map               │
├─────────────────────────────────────────────────┤
│                                                 │
│        [Interactive Map with Markers]           │
│                                                 │
│                ♿ ♿         ♿                   │
│           ♿          ♿                         │
│                                                 │
│  Info Panel (Top Right):                        │
│  ─────────────────────────                      │
│  Wheelchair Accessibility Map                   │
│  Found 12 locations                             │
│  [Add Missing Point] [Button]                   │
│                                                 │
└─────────────────────────────────────────────────┘
```

---

## 🗺️ Roadmap & Future Enhancements

### **Phase 1: Core Features** ✅ (Current)
- [x] Real-time geolocation detection
- [x] Overpass API integration
- [x] Interactive marker system
- [x] Crowdsourced contribution form
- [x] Mobile-responsive design
- [x] Next.js and React setup

### **Phase 2: Data Persistence** 🚧 (In Progress)
- [ ] Supabase database integration for user submissions
- [ ] Authentication system (Google, GitHub OAuth)
- [ ] User profiles and contribution tracking
- [ ] Backend validation and moderation

### **Phase 3: Advanced Features** 📅 (Planned)
- [ ] Route planning with accessibility filters
- [ ] Advanced search filters (facility type, accessibility level)
- [ ] User reviews and ratings for locations
- [ ] Photo uploads for facilities
- [ ] Accessibility challenges and solutions reporting
- [ ] Integration with OpenStreetMap editing tools
- [ ] Multi-language support (i18n)
- [ ] Dark mode / light mode theme toggle

### **Phase 4: Community & Analytics** 🎯 (Long-term)
- [ ] Community forums and discussions
- [ ] Contribution leaderboards and gamification
- [ ] Analytics dashboard for accessibility trends
- [ ] Heat maps of underserved areas
- [ ] Partnership with accessibility organizations
- [ ] Offline map support (PWA)
- [ ] Native mobile apps (React Native)

### **Phase 5: Enterprise & Integration** 🌟 (Vision)
- [ ] API for third-party integrations
- [ ] City and municipality partnerships
- [ ] Real-time accessibility event notifications
- [ ] AI-powered accessibility predictions
- [ ] Integration with public transportation systems

---

## 🤝 Contributing

We believe in the power of community. Your contributions—whether code, ideas, or feedback—help make the world more accessible.

### **Getting Started with Contributing**

1. **Fork the Repository**
   ```bash
   Click the "Fork" button on GitHub
   ```

2. **Clone Your Fork**
   ```bash
   git clone https://github.com/YOUR-USERNAME/EYE-LINK-PROJECT.git
   cd EYE-LINK-PROJECT
   ```

3. **Create a Feature Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```
   
   **Branch Naming Conventions:**
   - `feature/add-new-feature`
   - `fix/bug-description`
   - `docs/update-readme`
   - `refactor/improve-performance`

4. **Make Your Changes**
   - Write clean, well-documented code
   - Follow the existing code style
   - Add comments for complex logic
   - Test your changes thoroughly

5. **Commit Your Changes**
   ```bash
   git add .
   git commit -m "feat: add feature description"
   ```
   
   **Commit Message Format:**
   - `feat:` for new features
   - `fix:` for bug fixes
   - `docs:` for documentation
   - `style:` for code style changes
   - `refactor:` for code refactoring
   - `test:` for tests

6. **Push to Your Fork**
   ```bash
   git push origin feature/your-feature-name
   ```

7. **Open a Pull Request**
   - Navigate to the original repository
   - Click "New Pull Request"
   - Select your branch and provide a detailed description
   - Reference any related issues (e.g., "Closes #42")

### **Pull Request Guidelines**

- ✅ Provide a clear, descriptive title
- ✅ Include a detailed description of changes
- ✅ Reference related issues
- ✅ Add screenshots or GIFs for UI changes
- ✅ Ensure all tests pass
- ✅ Follow the code style guide
- ✅ Request review from maintainers

### **Code Style Guide**

- **JavaScript/TypeScript**: Use ESLint and Prettier for consistency
  ```bash
  npm run lint
  ```

- **Naming Conventions**:
  - Variables and functions: `camelCase`
  - Classes and components: `PascalCase`
  - Constants: `UPPER_SNAKE_CASE`

- **Component Structure**:
  ```typescript
  import React from 'react';
  
  interface ComponentProps {
    // props interface
  }
  
  const MyComponent: React.FC<ComponentProps> = ({ prop }) => {
    // component logic
    return <div>Component</div>;
  };
  
  export default MyComponent;
  ```

### **Issues & Feature Requests**

- Check existing issues before creating a new one
- Use issue templates (if available)
- Provide clear, reproducible examples
- Include screenshots or error logs
- Tag issues appropriately (bug, feature, documentation)

### **Getting Help**

- 💬 **Discussion Forums**: [GitHub Discussions](#)
- 📧 **Email**: [Contact Maintainer](#)
- 🐛 **Bug Reports**: Use GitHub Issues
- 💡 **Feature Suggestions**: Create an issue with `[FEATURE REQUEST]` tag

---

## 📄 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

### **MIT License Summary**

You are free to:
- ✅ Use this software for any purpose
- ✅ Copy, modify, and distribute it
- ✅ Include it in proprietary applications

You must:
- ✓ Include the original copyright notice
- ✓ Include a copy of the MIT License

---

## 👥 Contact & Community

### **Project Maintainer**

**Ritesh** ([GitHub Profile](https://github.com/RITESH2127))

### **Get Involved**

- 🌟 **Star this repository** if you find it helpful!
- 🔔 **Watch for updates** to stay informed
- 🐛 **Report bugs** through GitHub Issues
- 💡 **Suggest features** in Discussions
- 🤝 **Contribute code** via Pull Requests

### **Follow for Updates**

- 📱 GitHub: [@RITESH2127](https://github.com/RITESH2127)
- 💌 Subscribe to updates on the [repository](https://github.com/RITESH2127/EYE-LINK-PROJECT)

---

## 🙏 Acknowledgments

- **OpenStreetMap** – For the comprehensive, free geographic data
- **Overpass API** – For the powerful query interface
- **Leaflet.js** – For the excellent mapping library
- **Next.js & React Teams** – For amazing frameworks
- **Tailwind CSS** – For utility-first CSS excellence
- **Radix UI** – For accessible component primitives
- **Our Contributors** – For believing in accessibility

---

## ⚖️ Disclaimer

This project is a community-driven effort to improve accessibility. While we strive for accuracy, **data from OpenStreetMap and user contributions may not be complete or current**. Always verify accessibility features directly with venues before visiting. For critical accessibility needs, contact facilities directly.

---

## 📞 Support

If you encounter any issues or need assistance:

1. **Check the [Troubleshooting](#troubleshooting) section** below
2. **Search existing [GitHub Issues](https://github.com/RITESH2127/EYE-LINK-PROJECT/issues)**
3. **Create a new issue** with detailed information
4. **Join our community** discussions for peer support

### **Troubleshooting**

| Issue | Solution |
|-------|----------|
| Map not loading | Check internet connection, ensure browser allows geolocation |
| No markers showing | Verify coordinates are correct, check Overpass API status |
| Form won't submit | Ensure all required fields are filled, check console for errors |
| Styling looks broken | Clear cache and hard-refresh (Ctrl+Shift+R or Cmd+Shift+R) |
| Geolocation denied | Enable location access in browser settings, reload page |

---

<div align="center">

### **Made with ♥️ to make the world more accessible**

**[⬆ back to top](#eye-link-wheelchair-accessibility-map)**

[![GitHub Stars](https://img.shields.io/github/stars/RITESH2127/EYE-LINK-PROJECT?style=social)](https://github.com/RITESH2127/EYE-LINK-PROJECT)
[![GitHub Forks](https://img.shields.io/github/forks/RITESH2127/EYE-LINK-PROJECT?style=social)](https://github.com/RITESH2127/EYE-LINK-PROJECT)
[![GitHub Contributors](https://img.shields.io/github/contributors/RITESH2127/EYE-LINK-PROJECT)](https://github.com/RITESH2127/EYE-LINK-PROJECT/graphs/contributors)

</div>
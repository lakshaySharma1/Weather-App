🌦️ 3D Live Nature Weather App
An immersive, 3D interactive weather dashboard that brings forecasts to life.

📖 Overview
This project is a modern, front-end web application that fetches real-time weather data and visualizes it through a glassmorphism interface set against a live, parallax nature background.

Unlike standard weather dashboards, this application focuses on User Experience (UX) by implementing 3D tilt effects that respond to mouse movement, dynamic animations that reflect actual weather conditions (rain, wind speed), and a "living" background system.

✨ Key Features
🎨 Visual & Interactive
3D Parallax Tilt Effect: The main glass card rotates in 3D space based on the user's cursor position, creating a depth-of-field effect.

Live Nature Background: Features a static mountain layer and a continuously flowing cloud layer to simulate a living environment.

Glassmorphism UI: Modern, translucent card design with backdrop blurring and dynamic shadows.

⚡ Dynamic Weather Visualization
Real-Time Rain Simulation: If the API reports rain, a CSS-based rain overlay is dynamically generated over the scenery.

Smart Wind Animation: A custom CSS "Wind Fan" spins at different speeds depending on the actual wind speed (kph) fetched from the API.

Breeze: Slow rotation.

Storm: Fast rotation.

Floating Elements: Weather icons and text float on different Z-axis layers to enhance the 3D depth.

🛠️ Technical
API Integration: Powered by WeatherAPI.com using asynchronous JavaScript (async/await).

Robust Error Handling: Manages invalid cities, network errors, and API limits with user-friendly feedback.

Responsive Data Grid: Displays Temperature, Humidity, UV Index, Visibility, Pressure, and "Feels Like" temperature.

💻 Tech Stack
HTML5: Semantic structure.

CSS3: Advanced animations (@keyframes), 3D transforms (perspective, rotate3d), CSS Variables, and Flexbox/Grid layouts.

JavaScript (ES6+): DOM manipulation, Fetch API, Event Listeners, and logic for dynamic styling.

🚀 Installation & Setup
Since this is a client-side application, no backend server setup is required.

Clone the Repository

Bash

git clone https://github.com/YOUR_USERNAME/weather-app-lakshay.git
Navigate to the Folder

Bash

cd weather-app-lakshay
Run the Project Simply open the index.html file in your preferred web browser.

Recommended: Use the "Live Server" extension in VS Code for the best experience.

API Key Configuration

Open index.html.

Locate the const API_KEY variable in the script section.

(Optional) Replace the existing key with your own free API key from WeatherAPI.com.

🧠 Code Highlights
1. The 3D Tilt Logic
We calculate the mouse position relative to the center of the screen and apply a rotation to the card container.

JavaScript

document.addEventListener('mousemove', (e) => {
    // Calculate distance from center, divided by sensitivity factor (20)
    const x = (window.innerWidth / 2 - e.pageX) / 20; 
    const y = (window.innerHeight / 2 - e.pageY) / 20;

    // Apply rotation: Y-axis rotation is based on X mouse movement
    card.style.transform = `rotateY(${-x}deg) rotateX(${y}deg)`;
});
2. Dynamic Wind Fan Speed
We map the wind speed (km/h) to a CSS animation duration variable (--spin-speed).

JavaScript

const kph = current.wind_kph;
let spinDuration;

if (kph < 5) spinDuration = '4s';       // Slow
else if (kph < 15) spinDuration = '2s'; // Medium
else if (kph < 30) spinDuration = '1s'; // Fast
else spinDuration = '0.3s';             // Storm mode

// Inject the variable into the CSS
windFan.style.setProperty('--spin-speed', spinDuration);
📂 Project Structure
/
├── index.html       # The core application (HTML/CSS/JS bundled)
├── assets/          # (Optional) Folder for local images/icons
└── README.md        # Project documentation
🔮 Future Improvements
Dark/Light Mode Toggle: Based on the local time of the searched city (Day vs. Night).

5-Day Forecast: Expanding the card to show upcoming weather trends.

Geolocation: Automatically fetch weather for the user's current location on load.

📄 License
This project is open source and available under the MIT License.

Crafted with 💙 by Lakshay

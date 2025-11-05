⚽ React Player Cards – Interactive Football Showcase

This project is a React application built with Create React App that displays interactive football player cards using React Bootstrap.
Each player card includes an image, a GIF animation on hover, and a unique sound effect that plays when you click the sound button.

🚀 Features

🎴 Display player information (name, team, nationality, jersey number, age)

🖼️ Smooth GIF transition on hover

🔊 Play custom sounds for each player (e.g., “Siuuu” for Ronaldo)

🧩 Modular React components (Player, PlayerList, Header, Footer)

💅 Styled using React Bootstrap with inline effects and transitions

🎧 Prevents overlapping sounds (stops the previous one before playing another)

🧱 Project Structure
public/
 ├── img/
 │    ├── sound.jpg
 │    ├── kylian-mbappe.webp
 │    ├── ...
 ├── sounds/
 │    ├── kylian-mbappe.mp3
 │    ├── lionel-messi.mp3
 │    ├── christiano-ronaldo.mp3
 │    └── lamine-yamal.mp3
src/
 ├── components/
 │    ├── Player.js
 │    ├── PlayerList.js
 │    ├── Header.js
 │    ├── Footer.js
 ├── models/
 │    └── player.js
 ├── App.js
 ├── App.css
 └── index.js

🛠️ Installation & Setup

Clone the repository

git clone https://github.com/your-username/react-player-cards.git
cd react-player-cards


Install dependencies

npm install


Run the app

npm start


The app will open on http://localhost:3000

🧩 Components Overview
🧠 Player.js

Displays an individual player card:

Shows image and switches to a GIF on hover

Includes a clickable sound button (sound.jpg)

Uses Card and Image from React Bootstrap

🏆 PlayerList.js

Maps through all players from players.js and renders a list of Player components.

🧾 players.js

Contains an array of JSON objects defining player data:

{
  name: "Kylian Mbappé",
  team: "Paris Saint-Germain",
  nationality: "France",
  jerseyNumber: 7,
  age: 26,
  imageURL: "/img/kylian-mbappe.webp",
  gifURL: "/img/kylian-mbappe.gif",
  soundURL: "/sounds/kylian-mbappe.mp3"
}

🧱 App.js

The root component that imports Header, PlayerList, and Footer to display the complete layout.

🎨 Styling

Cards styled with React Bootstrap and inline styles

Smooth transitions (transition: 1s ease-in-out)

Interactive hover effects (scale, shadow-sm)

Icons/images used for sound buttons

🧠 Key Code Highlights
<Image
  src="/img/sound.jpg"
  onClick={() => playSound(soundURL)}
  width="20"
  height="20"
  style={{ cursor: "pointer" }}
/>

const playSound = (soundURL) => {
  if (currentAudio) {
    currentAudio.pause();
    currentAudio.currentTime = 0;
  }
  const audio = new Audio(soundURL);
  audio.volume = 0.8;
  audio.play();
  currentAudio = audio;
  audio.onended = () => (currentAudio = null);
};

🧩 Dependencies

React – UI framework

React Bootstrap – For responsive cards and layout

Bootstrap – CSS styling

(Optional) React Icons – For adding sound or action icons

Install React Bootstrap if not already:

npm install react-bootstrap bootstrap


And import Bootstrap in index.js:

import 'bootstrap/dist/css/bootstrap.min.css';

💡 Future Improvements

Add animation or icon change during sound playback

Display player stats or achievements dynamically

Integrate a search or filter bar

Use context or Redux for global sound control

👨‍💻 Author

Sylvestre Ibombo Gakosso
Full Stack Developer — Java, Spring Boot, Angular, React, Laravel
📍 Based in Senegal
🔗 GitHub: Sylviedistribution
# Chain Reaction 3D (Mobile Friendly)

This project is a 3D version of the classic chain reaction game built using Three.js. The game is designed to be mobile friendly, featuring responsive layouts and a touch-friendly interface.

## Project Structure

- **index.html**  
  The main HTML file that contains all the game logic within inline scripts.  
  It handles:
  - Game setup and UI (setup screen, game over panel, mute button)
  - Three.js scene setup (camera, renderer, lighting, grid visuals)
  - Game logic (placing orbs, checking for critical mass, chain reactions, explosions)
  - Animation of projectiles using `requestAnimationFrame`
  - Sound control with the Web Audio API
  - Game clean-up and resource disposal

- **README.md**  
  This file describes the project setup, game rules, and instructions.

## How to Run

1. **Open the Game Directly:**
   - You can open the `index.html` file directly in your web browser by double-clicking it or dragging it into a browser window.

2. **Using a Local Development Server:**

   ### With Python:
   ```sh
   python -m http.server
   ```
   Open `http://localhost:8000` in your browser.

   ### With Node.js:
   Install a simple HTTP server:
   ```sh
   npm install -g http-server
   ```
   Run the server:
   ```sh
   http-server
   ```
   Then open the provided URL (e.g., `http://localhost:8080`) in your browser.

## Game Play and Mechanics

- **Setup:**  
  On launch, a setup panel appears letting you select the number of players and grid size. Once configured, click the **Start Game** button.

- **Gameplay:**  
  - Players take turns placing orbs on cells by tapping or clicking on the grid.
  - Each cell has a critical mass that depends on its position (corners, edges, or center). Once that mass is reached, the cell "explodes," sending orbs to adjacent cells.
  - Orbs take on the color of the player who placed them. When a chain reaction occurs, explosions spread to nearby cells.
  - A timer has been added within the explosion chain to automatically exit the game after 5 seconds of continuous explosions.

- **Game Over:**  
  The game will display a win message on the UI panel if a player wins or if the explosion chain exceeds 5 seconds. The winning player's color is highlighted, and a "Play Again" button is presented to restart the game.

## Code Highlights

- **Explosion Timer:**  
  The explosion loop in `explodeCell` monitors the duration of ongoing explosions. If the chain reaction continues for more than 5 seconds after a move, the game is ended automatically.

- **Resource Management:**  
  The `disposeObject` and `cleanup` methods ensure that Three.js resources (materials, geometries, textures) are properly disposed of when the game is reset or exited.

- **Responsive Design:**  
  The game scales dynamically to fit the browser window. UI elements such as the grid, mute button, and setup panel are designed to be accessible on mobile devices.

## Dependencies

- [Three.js](https://threejs.org/)  
  The game utilizes Three.js for 3D rendering.

- [Tailwind CSS](https://tailwindcss.com/)  
  Used for some basic styling of the UI panels.

## License

Feel free to modify and use this code as needed. If you redistribute it, please include proper attribution where necessary.

---

Enjoy the game and have fun with Chain Reaction 3D!
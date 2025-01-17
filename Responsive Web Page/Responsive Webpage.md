# Responsive Webpage Project

This project demonstrates the creation of a responsive webpage using HTML, CSS, JavaScript, and Node.js. The webpage consists of a navigation bar, a main content area, and two side panels. The layout dynamically adjusts based on the screen size.

---

## File Structure
![Alt Text](https://github.com/AniketP117/Frontend-Work-With-js/blob/8ef2f78b6704a3cea6ac39dd2bd18bd97fd0cae7/Responsive%20Web%20Page/codes%20all%20in%20one%20place.png)

### HTML
The `index.html` file provides the structure of the webpage.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Webpage</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <nav class="navbar">Navbar</nav>
  <div class="container">
    <aside class="left-menu">
        <p>Left Menu Content</p>
        <select>
            <option value="Menu Item 1">Menu Item 1</option>
            <option value="Menu Item 2">Menu Item 2</option>
            <option value="Menu Item 3">Menu Item 3</option>
        </select>
    </aside>
    <main class="main-content">
      Main Content Area
    </main>
    <aside class="right-panel">
      Right Side Panel
    </aside>
  </div>
  <footer>Footer</footer>
  <script src="script.js"></script>
</body>
</html>
```

### CSS
The `styles.css` file defines the styling and responsiveness of the webpage.

```css
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}

.navbar {
    background-color: #333;
    color: white;
    padding: 10px;
    position: fixed;
    width: 100%;
    top: 0;
    z-index: 1000;
    display: flex;
    justify-content: center;
}

.container {
    display: flex;
    margin-top: 50px;
    min-height: 90vh;
}

.left-menu, .right-panel {
    width: 20%;
    background-color: #f4f4f4;
    padding: 10px;
}

.main-content {
    flex: 1;
    padding: 10px;
}

footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 10px 0;
    position: fixed;
    bottom: 0;
    width: 100%;
}
```

### JavaScript
The `script.js` file adds interactivity and responsiveness to the webpage.

```javascript
document.getElementById("collapse-btn")?.addEventListener("click", () => {
    const leftMenu = document.querySelector(".left-menu");
    leftMenu.style.display = leftMenu.style.display === "none" ? "block" : "none";
});

function adjustWidth() {
    const screenWidth = window.innerWidth;
    const container = document.querySelector(".container");

    if (screenWidth <= 600) {
        container.style.transform = "scale(0.5)";
    } else if (screenWidth <= 700) {
        container.style.transform = "scale(0.75)";
    } else if (screenWidth <= 767) {
        container.style.transform = "scale(0.8)";
    } else if (screenWidth <= 1600) {
        container.style.transform = "scale(0.9)";
    } else {
        container.style.transform = "scale(1)";
    }
}

window.addEventListener("resize", adjustWidth);
adjustWidth();
```

### Node.js Server
The `server.js` file sets up a Node.js server to serve the webpage.

```javascript
const express = require('express');
const app = express();
const path = require('path');

// Serve static files
app.use(express.static(path.join(__dirname, 'public')));

// Serve the homepage
app.get('/', (req, res) => {
  res.sendFile(path.join(__dirname, 'public/index.html'));
});

// Start the server
const PORT = 3000;
app.listen(PORT, () => {
  console.log(`Server running on http://localhost:${PORT}`);
});
```

---

## How to Run the Project

1. Clone the repository:

```bash
git clone <repository-url>
```

2. Navigate to the project directory:

```bash
cd <project-directory>
```

3. Install the required dependencies:

```bash
npm install
```

4. Start the server:

```bash
node server.js
```

5. Open your browser and navigate to:

```text
http://localhost:3000
```

---

## Features

- **Result**: Main Containt Page.
![Alt Text](https://github.com/AniketP117/Frontend-Work-With-js/blob/3964c47d49ecd7dae57c75239bf0d73de5b313d2/Responsive%20Web%20Page/Result%20of%20the%20execution.png)

- **Result-Oriented Design**: Features a dropdown menu and collapsible left menu.
![Alt Text](https://github.com/AniketP117/Frontend-Work-With-js/blob/125181d7765ae6aeadfad4fb9856f53950f5ed44/Responsive%20Web%20Page/collapsable%20left%20panel.png)
- **Responsive Design**: The layout adjusts to different screen sizes.
![Alt Text](https://github.com/AniketP117/Frontend-Work-With-js/blob/8ef2f78b6704a3cea6ac39dd2bd18bd97fd0cae7/Responsive%20Web%20Page/When%20Webpage%20is%20at%20600px.png)
---

## Terminal Result

Here is a preview of the terminal output when the server is successfully started:

![Terminal Result](https://github.com/AniketP117/Frontend-Work-With-js/blob/83ade66c41e9743815dcbf3695bdca9a47526bfa/Responsive%20Web%20Page/Terminal%20after%20code%20execution.png)

---

## Future Enhancements

- Add more interactivity to the side panels.
- Implement additional responsive breakpoints.
- Integrate backend APIs for dynamic content loading.

---

## License

This project is open-source.

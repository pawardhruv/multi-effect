# multi-effect
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Easy UI Showcase</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Easy Multi-Effect UI Showcase</h1>
        <p>A simple demonstration of CSS concepts</p>
    </header>

    <div class="container">
        <section class="profile-cards">
            <h2>Layered Profile Cards (Simplified)</h2>
            <div class="card-grid">
                <div class="card">
                    <img src="https://via.placeholder.com/100" alt="Profile 1">
                    <h3>User One</h3>
                    <p>Web Developer</p>
                </div>
                <div class="card">
                    <img src="https://via.placeholder.com/100" alt="Profile 2">
                    <h3>User Two</h3>
                    <p>UI/UX Designer</p>
                </div>
            </div>
        </section>

        <section class="buttons">
            <h2>Creative Buttons (Simplified)</h2>
            <button class="simple-button">Hover Me</button>
            <button class="glow-button">Glow</button>
        </section>
    </div>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    background-color: #f4f4f4;
    color: #333;
}

header {
    background-color: #333;
    color: #fff;
    padding: 20px 0;
    text-align: center;
    margin-bottom: 20px;
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

section {
    background-color: #fff;
    padding: 20px;
    margin-bottom: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

h2 {
    text-align: center;
    margin-bottom: 25px;
    color: #555;
}

/* Card Grid Layout */
.card-grid {
    display: grid; /* Organizes multiple responsive sections using display: grid  */
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); /* responsive columns  */
    gap: 20px;
    justify-content: center;
}

.card {
    background-color: #fff;
    border: 1px solid #ddd;
    border-radius: 8px;
    padding: 20px;
    text-align: center;
    transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out; /* Apply hover with transform and transition to animate cards  */
    position: relative;
    overflow: hidden; /* Needed for ::before pseudo-element */
}

.card img {
    border-radius: 50%;
    width: 100px;
    height: 100px;
    object-fit: cover;
    margin-bottom: 10px;
    border: 3px solid #eee;
}

.card h3 {
    margin: 10px 0 5px;
    color: #007bff;
}

.card p {
    color: #666;
    font-size: 0.9em;
}

/* Card Hover Effect */
.card:hover {
    transform: translateY(-10px) scale(1.02); /* Animate cards  */
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

/* ::before for layered visual effects (simplified)  */
.card::before {
    content: '';
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: radial-gradient(circle at center, rgba(0, 123, 255, 0.1) 0%, transparent 70%);
    opacity: 0;
    transition: opacity 0.4s ease-in-out;
    z-index: 0;
}

.card:hover::before {
    opacity: 1;
}

/* Simple Button */
.simple-button, .glow-button {
    background-color: #007bff;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
    transition: background-color 0.3s ease;
    margin: 5px;
}

.simple-button:hover {
    background-color: #0056b3;
}

/* Glow Button (simplified) */
.glow-button {
    background-color: #ffc107;
    color: #333;
    position: relative;
    overflow: hidden;
}

.glow-button::before {
    content: '';
    position: absolute;
    top: -100%;
    left: -100%;
    width: 300%;
    height: 300%;
    background: radial-gradient(circle at center, rgba(255, 255, 255, 0.5) 0%, transparent 70%);
    transition: transform 0.5s ease-in-out;
    transform: rotate(45deg);
    opacity: 0;
}

.glow-button:hover::before {
    transform: rotate(45deg) translate(50%, 50%);
    opacity: 1;
}

.glow-button:hover {
    box-shadow: 0 0 15px rgba(255, 193, 7, 0.7);
}


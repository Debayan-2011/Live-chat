<html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gaming Coaching & Training Hub</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #ff5e00;
            color: rgb(0, 0, 0);
            text-align: center;
           }
        .container {
            max-width: 1000px;
            margin: 50px auto;
        }
        .chat-box {
            border: 1px solid #ff5e00;
            height: 300px;
            overflow-y: scroll;
            padding: 10px;
            background: #006866;
        }
        .message {
            background: #006866;
            padding: 5px;
            margin: 5px;
            border-radius: 5px;
        }
        input, button {
            padding: 10px;
            margin-top: 10px;
        }a
            flex-wrap: wrap;
            justify-content: center;
            gap: 10px;
        }
        .coach-card {
            background: #006866;
            padding: 15px;
            border-radius: 8px;
            width: 250px;
            text-align: left;
        }
        .contact-form {
            background: #006866;
            padding: 20px;
            border-radius: 10px;
            width: 50%;
            margin: auto;
        }
    </style>
</head>
<body>
    <div class="container">
        <marquee><h1>Welcome to Gaming Coaching & Training Hub</h1></marquee>
        <p>Find professional gaming coaches, training programs, and game testing services.</p>
        
        <marquee><h2>Available Coaches & Training Programs</h2></marquee>
        <div class="coaching-list" id="coaching-list"></div>
        
        <h2>Live Chat</h2>
        <div class="chat-box" id="chat-box"></div>
        
        <form id="chat-form">
            <input type="text" id="message" placeholder="Type a message...">
            <button type="submit">Send</button>
        </form>

        <h2>Book a Coaching Session</h2>
        <form class="contact-form" method="post" action="https://formspree.io/f/mdkenrba">
            <input type="text" name="name" placeholder="Your Name" required><br><br>
            <input type="email" name="email" placeholder="Your Email" required><br><br>
            <select name="game" required>
                <option value="FAU-G">FAU-G</option>
                <option value="Free Fire">Free Fire</option>
                <option value="Call of Duty">Call of Duty</option>
                <option value="Minecraft">Minecraft</option>
            </select><br><br>
            <textarea name="message" placeholder="Tell us your goals" required></textarea><br><br>
            <button type="submit">Book Now</button>
        </form>
    </div>

    <script>
        document.getElementById("chat-form").addEventListener("submit", function(event) {
            event.preventDefault();
            const message = document.getElementById("message").value;
            if (message.trim() !== "") {
                const chatBox = document.getElementById("chat-box");
                const msgDiv = document.createElement("div");
                msgDiv.className = "message";
                msgDiv.innerText = `${new Date().toLocaleTimeString()} - ${message}`;
                chatBox.appendChild(msgDiv);
                chatBox.scrollTop = chatBox.scrollHeight;
                document.getElementById("message").value = "";
            }
        });

        function addCoach(name, expertise) {
            const coachingList = document.getElementById("coaching-list"); 
            const coachCard = document.createElement("div");
            coachCard.className = "coach-card";
            coachCard.innerHTML = `<strong>${name}</strong><br>Expertise: ${expertise}`;
            coachingList.appendChild(coachCard);
        }

        addCoach("Alex Gaming", "FPS Games - Call of Duty, Valorant");
        addCoach("ProBuilder", "Building & Strategy - Fortnite");
        addCoach("CreativeCraft", "Sandbox & Survival - Minecraft");
        addCoach("RPGMaster", "Open-world RPGs - Elden Ring");
    </script>
</body>
</html>

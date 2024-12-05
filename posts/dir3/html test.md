---
title: This post has HTML
order: 1
---

<script src="https://resources.sienci.com/wp-content/react/wizard.js"></script>
<style>@import url('https://resources.sienci.com/wp-content/react/wizard.css')</style>

Test2

<!-- Header Section -->
<header>
    <h1>Sample HTML Page</h1>
</header>

<!-- Navigation Section -->
<nav>
    <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
</nav>

✨ ✨ ✨ ✨ ✨ ✨ ✨

<!-- Main Content Section -->
<main>
    <section id="home">
        <h2>Welcome to Our Website!</h2>
        <p>This is a sample HTML page with JavaScript and CSS styling.</p>
    </section>

    <section id="about">
        <h2>About Us</h2>
        <p>We are here to demonstrate the use of HTML tags, CSS styling, and JavaScript in a web page.</p>
        <img src="https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png" alt="Google logo"/>
    </section>

    <!-- JavaScript Interaction -->
    <section id="contact">
        <h2>Contact Us</h2>
        <p>Feel free to reach out to us!</p>
        <img src="/resources/images/icons/git-it-write.png" alt="Git it Write"/>

        <!-- Sample JavaScript -->
        <script>
            function showMessage() {
                alert('Thank you for contacting us!');
            }
            
            const emailRegex = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/;

            const email = "example@email.com";
            if (emailRegex.test(email)) {
                console.log("Valid email address");
            } else {
                console.log("Invalid email address");
            }
            
        </script>

        <!-- Sample Form -->
        <form>
            <label for="name">Name:</label>
            <input type="text" id="name" name="name" placeholder="Your name">

            <label for="email">Email:</label>
            <input type="email" id="email" name="email" placeholder="Your email">

            <label for="message">Message:</label>
            <textarea id="message" name="message" placeholder="Your message"></textarea>

            <button type="button" onclick="showMessage()">Submit</button>
        </form>
    </section>
</main>

<!-- Footer Section -->
<footer>
    <p>&copy; 2023 Sample HTML Page</p>
</footer>

<!-- Sample CSS Style -->
<style>
    body {
        font-family: 'Arial', sans-serif;
        background-color: red;
        margin: 0;
    }

    h1 {
        color: #333;
    }

    p {
        color: #666;
    }

    form {
        margin-top: 20px;
    }

    label {
        display: block;
        margin-bottom: 5px;
    }

    input {
        padding: 8px;
        margin-bottom: 10px;
        width: 100%;
        box-sizing: border-box;
    }

    button {
        background-color: #4caf50;
        color: white;
        padding: 10px 15px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
</style>

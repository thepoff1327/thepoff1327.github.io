<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Site Content</title>
</head>
<body>
    <!-- Menu -->
    <div id="menu">
        <ul>
            <li><a href="#" onclick="loadContent('home')">Home</a></li>
            <!-- Add more menu items as needed -->
            <li style="float: right;"><a href="#" onclick="loadContent('login')">Log In</a></li>
        </ul>
    </div>

    <!-- Site content will be dynamically loaded here -->
    <div id="site-content">
        <!-- Content will be dynamically loaded here -->
    </div>

    <script>
        // Function to load content based on menu selection
        function loadContent(page) {
            if (page === 'login') {
                // Login page content
                document.getElementById("site-content").innerHTML = `
                    <h1>Login</h1>
                    <form id="loginForm">
                        <label for="username">Username:</label>
                        <input type="text" id="username" name="username" required><br><br>
                        <label for="password">Password:</label>
                        <input type="password" id="password" name="password" required><br><br>
                        <button type="submit">Log In</button>
                    </form>
                `;
            } else {
                // Fetch the HTML content for other pages
                var rawContentUrl = "https://raw.githubusercontent.com/thepoff1327/thepoff1327.github.io/main/" + page;
                fetch(rawContentUrl)
                    .then(response => response.text())
                    .then(html => {
                        document.getElementById("site-content").innerHTML = html;
                    })
                    .catch(error => {
                        console.error("Error fetching site content:", error);
                    });
            }
        }

        // Load the home page by default
        loadContent('home');
    </script>
</body>
</html>

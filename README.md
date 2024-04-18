<!DOCTYPE html>
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
            <li><a href="#" onclick="loadContent('videos')">Videos</a></li>
            <li><a href="#" onclick="loadContent('about me')">About Me</a></li>
            <!-- Add more menu items as needed -->
        </ul>
    </div>

    <!-- Site content will be dynamically loaded here -->
    <div id="site-content">
        <!-- Content will be dynamically loaded here -->
    </div>

    <script>
        // Function to load content based on menu selection
        function loadContent(page) {
            var rawContentUrl = "https://raw.githubusercontent.com/thepoff1327/thepoff1327.github.io/main/" + page.replace(/ /g, '%20');

            // Fetch the HTML content
            fetch(rawContentUrl)
                .then(response => response.text())
                .then(html => {
                    // Insert the fetched HTML content into the site
                    document.getElementById("site-content").innerHTML = html;
                })
                .catch(error => {
                    console.error("Error fetching site content:", error);
                });
        }

        // Load the home page by default
        loadContent('home');
    </script>
</body>
</html>

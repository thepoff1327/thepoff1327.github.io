# thepoff1327.github.io
se ci est pour mon école  project
//
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Site Content</title>
</head>
<body>
    <div id="site-content">
        <!-- Content will be dynamically loaded here -->
    </div>

    <script>
        // URL of the raw content on GitHub
        var rawContentUrl = "https://raw.githubusercontent.com/thepoff1327/thepoff1327.github.io/main/home";

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
    </script>
</body>
</html>
//

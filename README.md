# Festive.github.io
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Generator</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>My Image Generator</h1>
        <p>Enter a word or phrase to generate an image</p>
    </header>
    <main>
        <input type="text" id="query" placeholder="Enter words...">
        <button onclick="generateImage()">Generate Image</button>
        <div id="image-container"></div>
    </main>
    <footer>
        <p>© 2024 MyImageGenerator.com</p>
    </footer>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    text-align: center;
}

header, footer {
    background-color: #f4f4f4;
    padding: 10px;
}

input {
    padding: 10px;
    margin: 10px;
}

button {
    padding: 10px;
    background-color: #007bff;
    color: white;
    border: none;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}
async function generateImage() {
    const query = document.getElementById('query').value;
    const response = await fetch(`https://api.example.com/search?query=${encodeURIComponent(query)}`);
    const data = await response.json();
    
    const imageUrl = data.results[0].imageUrl;
    const imageContainer = document.getElementById('image-container');
    imageContainer.innerHTML = `<img src="${imageUrl}" alt="Generated Image">`;
}


#image-container img {
    max-width: 100%;
    height: auto;
}

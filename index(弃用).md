<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Random Image API</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            min-height: 100vh;
            margin: 0;
        }
        main {
            flex: 1;
        }
        footer {
            text-align: center;
            padding: 1em;
            background: #f1f1f1;
        }
        img {
            display: block;
            margin: 0 auto;
            max-width: 100%;
            height: auto;
        }
        a {
            color: inherit;
            text-decoration: none;
        }
    </style>
</head>
<body>
    <main>
        <h1>Random Image API</h1>
        <img id="random-image" alt="Random Image" />
    </main>
    <footer>
        &copy; 2024 <a href="https://github.com/lidxs/random-image-api" target="_blank">lidxs</a>. All rights reserved.
    </footer>
    <script>
        // 动态加载 images.json 并随机选择图片
        fetch('images.json')
            .then(response => response.json())
            .then(images => {
                if (images.length > 0) {
                    const randomIndex = Math.floor(Math.random() * images.length);
                    const imgElement = document.getElementById('random-image');
                    imgElement.src = images[randomIndex];
                }
            })
            .catch(error => console.error('Error loading images:', error));
    </script>
</body>
</html>

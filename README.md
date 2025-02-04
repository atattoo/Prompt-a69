<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI Image Prompt Generator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #f8f8f8;
        }
        input, button, select {
            padding: 10px;
            margin: 10px;
            font-size: 16px;
        }
        #output {
            margin-top: 20px;
            font-size: 18px;
            color: #333;
            max-width: 80%;
            text-align: center;
        }
    </style>
</head>
<body>
    <h2>AI Image Prompt Generator</h2>
    <input type="text" id="keywords" placeholder="Enter keywords...">
    <select id="style">
        <option value="watercolor">Watercolor</option>
        <option value="oil painting">Oil Painting</option>
        <option value="ink sketch">Ink Sketch</option>
        <option value="charcoal drawing">Charcoal Drawing</option>
        <option value="digital painting">Digital Painting</option>
        <option value="pastel drawing">Pastel Drawing</option>
        <option value="acrylic painting">Acrylic Painting</option>
        <option value="pencil sketch">Pencil Sketch</option>
        <option value="collage art">Collage Art</option>
        <option value="pointillism">Pointillism</option>
        <!-- เพิ่ม style ใหม่ -->
        <option value="graffiti">Graffiti</option>
        <option value="surrealism">Surrealism</option>
        <option value="cubism">Cubism</option>
        <option value="abstract expressionism">Abstract Expressionism</option>
        <option value="pop art">Pop Art</option>
        <option value="low poly">Low Poly</option>
        <option value="stained glass">Stained Glass</option>
        <option value="vaporwave">Vaporwave</option>
        <option value="retro 80s">Retro 80s</option>
        <option value="steampunk">Steampunk</option>
    </select>
    <input type="number" id="quantity" placeholder="Enter number of prompts" min="1" max="10">
    <button onclick="generatePrompts()">Generate Prompts</button>
    <div id="output"></div>

    <script>
        function generatePrompts() {
            let keywords = document.getElementById('keywords').value.trim();
            let style = document.getElementById('style').value;
            let quantity = parseInt(document.getElementById('quantity').value);

            if (!keywords || isNaN(quantity) || quantity < 1) {
                document.getElementById('output').innerText = "Please enter valid keywords and quantity.";
                return;
            }

            let details = [
                "intricate patterns and textures", 
                "dynamic lighting and shadows", 
                "a surreal composition with unexpected elements", 
                "a harmonious blend of colors and depth", 
                "a cinematic perspective with striking contrast", 
                "an ethereal atmosphere with soft diffusion", 
                "a bold, expressive brushstroke technique", 
                "high detail in every aspect of the subject", 
                "a dreamlike quality with flowing motion", 
                "a timeless, classic aesthetic",
                // เพิ่มรายละเอียดใหม่อีก 50 แบบ
                "geometric abstraction with bold lines", 
                "a soft, atmospheric haze", 
                "a neon-lit ambiance with glowing edges", 
                "a retro-futuristic sci-fi aesthetic", 
                "organic shapes with flowing curves", 
                "symmetrical composition with precise angles", 
                "a textured surface with visible strokes", 
                "a muted, vintage color palette", 
                "a cold, industrial vibe with metallic tones", 
                "a bright, pop-inspired color scheme", 
                "gritty realism with high contrast", 
                "a hand-drawn illustration style", 
                "a highly saturated, vibrant look", 
                "a monochrome palette with dramatic lighting", 
                "a bold, graffiti-inspired design", 
                "a delicate, pastel-toned aesthetic", 
                "sharp, angular lines with high precision", 
                "a calming, zen-like simplicity", 
                "a chaotic, energetic burst of colors", 
                "a photorealistic, high-detail rendering", 
                "an abstract, experimental concept", 
                "a glowing, luminescent quality", 
                "rustic textures with natural imperfections", 
                "an exaggerated, cartoonish style", 
                "a smooth, polished finish", 
                "a grunge, distressed texture", 
                "a sleek, modern design with minimalism", 
                "a soft, impressionistic blur", 
                "a fantasy landscape with mystical elements", 
                "a futuristic, cyberpunk environment", 
                "a peaceful, idyllic countryside", 
                "a dense, urban cityscape", 
                "a whimsical, childlike quality", 
                "sharp contrasts with bold highlights", 
                "a minimalist black-and-white design", 
                "colorful, chaotic energy with motion blur", 
                "a serene underwater scene", 
                "otherworldly, alien landscapes", 
                "a fragmented, pixelated look", 
                "an abstract fusion of natural and digital elements", 
                "a bold, retro color scheme with neon accents", 
                "a sense of vast emptiness and space", 
                "a high-energy, dynamic composition", 
                "a vintage-inspired collage with mixed media", 
                "a fluid, organic motion with liquid forms", 
                "a high-contrast chiaroscuro lighting", 
                "a playful, quirky atmosphere", 
                "a subtle gradient blend of colors", 
                "a bold, flat design with vibrant colors", 
                "a polished, metallic surface with reflections"
            ];

            let output = "";
            for (let i = 0; i < quantity; i++) {
                let randomDetail = details[Math.floor(Math.random() * details.length)];
                let prompt = `A ${style} of ${keywords}, featuring ${randomDetail} --v 6.1 --style raw`;
                output += `<p>${prompt}</p>`;
            }
            document.getElementById('output').innerHTML = output;
        }
    </script>
</body>
</html>

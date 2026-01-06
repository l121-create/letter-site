# letter-site
A heartfelt interactive letter
letter-site/
├── index.html
├── style.css
├── script.js
└── piano.mp3
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>A Letter With Love</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<link href="https://fonts.googleapis.com/css2?family=Playfair+Display&family=Great+Vibes&display=swap" rel="stylesheet">

<link rel="stylesheet" href="style.css">
</head>

<body>

<audio id="music" loop>
    <source src="piano.mp3" type="audio/mpeg">
</audio>

<div class="container">
    <div class="envelope" onclick="openLetter()">
        <div class="flap"></div>
        <div class="letter">
            <h1>Dearest Yogeshbhai,</h1>

            <p>
                Thank you so much for the invitation. It was truly moving to read it
                and realize just how quickly the next generation has grown.
            </p>

            <p>
                It is with a heavy heart that I share we won’t be able to make it to
                the celebration, but Mummy and Papa will surely be there. Please feel
                our presence through them as they join you.
            </p>

            <p>
                Even though we are miles apart, please know that our love and blessings
                will be showering over Jay as he embarks on this significant new chapter
                of his life.
            </p>

            <p>
                We miss you all dearly and look forward to the day when our entire family
                (all three generations) can finally be reunited under one roof.
            </p>

            <p>
                I am genuinely sorry to miss the chance to see Jay enter Yuvavastha in
                person. As he steps into this new phase starting from his Yagnopavit,
                I am certain he is following his father’s lead.
            </p>

            <div class="signature">
                With all our love and blessings,<br>
                <span>Dushyant, Sonika, Kian & Aadhya</span> ❤️
            </div>
        </div>
    </div>

    <div class="hint">Click the envelope 💌</div>
</div>

<script src="script.js"></script>
</body>
</html>
body {
    margin: 0;
    height: 100vh;
    background: linear-gradient(135deg, #f6d365, #fda085);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Playfair Display', serif;
}

.container {
    text-align: center;
}

.envelope {
    width: 380px;
    height: 260px;
    background: #c0392b;
    position: relative;
    cursor: pointer;
    border-radius: 8px;
    box-shadow: 0 25px 50px rgba(0,0,0,0.3);
    overflow: hidden;
}

.flap {
    position: absolute;
    width: 100%;
    height: 100%;
    background: #a93226;
    clip-path: polygon(0 0, 100% 0, 50% 50%);
    transform-origin: top;
    transition: transform 1.2s ease;
    z-index: 3;
}

.letter {
    position: absolute;
    background: #fff6e5;
    width: 100%;
    height: 500px;
    top: 40px;
    left: 0;
    padding: 30px;
    box-sizing: border-box;
    transform: translateY(200px);
    transition: transform 1.5s ease;
    overflow-y: auto;
    z-index: 2;
}

.letter h1 {
    font-family: 'Great Vibes', cursive;
    font-size: 36px;
    margin-top: 0;
}

.signature span {
    font-family: 'Great Vibes', cursive;
    font-size: 26px;
}

.envelope.open .flap {
    transform: rotateX(180deg);
}

.envelope.open .letter {
    transform: translateY(-260px);
}

.hint {
    margin-top: 15px;
    color: #5a2d0c;
    font-style: italic;
}
let opened = false;

function openLetter() {
    if (!opened) {
        document.querySelector('.envelope').classList.add('open');
        document.getElementById('music').play();
        opened = true;
    }
}

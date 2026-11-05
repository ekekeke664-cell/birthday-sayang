
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Love ❤️</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    min-height: 100vh;
    overflow: hidden;
    font-family: Georgia, serif;
    background: radial-gradient(ellipse at bottom, #53264f, #190e2c 75%);
    color: white;
}

.scene {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: relative;
    padding: 15px;
    overflow: hidden;
}

.stars {
    position: absolute;
    inset: 0;
    pointer-events: none;
}

.star {
    position: absolute;
    color: white;
    animation: twinkle 2s infinite alternate;
}

h1 {
    font-size: clamp(28px, 7vw, 48px);
    text-align: center;
    color: #ffc5df;
    text-shadow: 0 0 15px #ff4c9c;
    animation: glow 2s infinite alternate;
    z-index: 2;
}

.subtitle {
    margin-top: 10px;
    color: #ffe0ef;
    font-size: 15px;
    letter-spacing: 2px;
    z-index: 2;
}

.tree {
    width: 320px;
    height: 350px;
    position: relative;
    margin-top: 20px;
    animation: appear 2s ease-out;
}

.trunk {
    position: absolute;
    bottom: 0;
    left: 154px;
    width: 17px;
    height: 0;
    border-radius: 50% 50% 5px 5px;
    background: linear-gradient(90deg, #61331f, #b77a4b, #60321e);
    animation: trunkGrow 2s 0.5s forwards;
}

.branch {
    position: absolute;
    bottom: 100px;
    left: 160px;
    width: 9px;
    height: 0;
    border-radius: 20px;
    background: #a66a40;
    transform-origin: bottom;
    animation: branchGrow 1.5s 2s forwards;
}

.b1 { transform: rotate(-50deg); }
.b2 { transform: rotate(50deg); }
.b3 { transform: rotate(-20deg); }
.b4 { transform: rotate(20deg); }

.leaves {
    position: absolute;
    inset: 0;
}

.leaf {
    position: absolute;
    font-size: 27px;
    opacity: 0;
    filter: drop-shadow(0 0 8px #ff4c9c);
    animation: leafAppear 1s forwards, heartbeat 2s infinite;
}

.ground {
    position: absolute;
    bottom: -3px;
    left: 50%;
    transform: translateX(-50%);
    width: 190px;
    height: 12px;
    background: #ed8fbd;
    border-radius: 50%;
    box-shadow: 0 0 25px #ff68b2;
}

.message {
    text-align: center;
    line-height: 1.7;
    color: #ffe5f1;
    font-size: 15px;
    margin-top: 12px;
    z-index: 2;
}

.buttons {
    display: flex;
    gap: 12px;
    margin-top: 18px;
    z-index: 5;
}

button {
    padding: 12px 20px;
    border: 1px solid #ffb2d5;
    border-radius: 30px;
    background: linear-gradient(135deg, #ff6da9, #b83279);
    color: white;
    font-size: 14px;
    cursor: pointer;
    box-shadow: 0 0 15px #ff6da9;
    transition: .3s;
}

button:hover {
    transform: scale(1.08);
    box-shadow: 0 0 25px #ff6da9;
}

.heart-rain {
    position: fixed;
    top: -30px;
    pointer-events: none;
    z-index: 4;
    animation: fall linear forwards;
}

.modal {
    position: fixed;
    inset: 0;
    background: #13091ddf;
    display: none;
    align-items: center;
    justify-content: center;
    padding: 20px;
    z-index: 10;
}

.letter {
    width: 100%;
    max-width: 350px;
    background: linear-gradient(145deg, #ffe1ee, #ffc0d9);
    color: #8b315e;
    border-radius: 20px;
    padding: 30px 22px;
    text-align: center;
    box-shadow: 0 0 40px #ff69aa;
    animation: openLetter .6s ease;
}

.letter h2 {
    margin-bottom: 18px;
    color: #c02f76;
}

.letter p {
    line-height: 1.8;
    font-size: 15px;
}

.letter button {
    margin-top: 20px;
}

@keyframes glow {
    from { text-shadow: 0 0 8px #ff5ca7; }
    to { text-shadow: 0 0 30px #ff5ca7; }
}

@keyframes twinkle {
    from { opacity: .2; transform: scale(.7); }
    to { opacity: 1; transform: scale(1.3); }
}

@keyframes trunkGrow {
    to { height: 175px; }
}

@keyframes branchGrow {
    to { height: 115px; }
}

@keyframes leafAppear {
    to { opacity: 1; }
}

@keyframes heartbeat {
    0%, 100% { scale: 1; }
    50% { scale: 1.2; }
}

@keyframes appear {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
}

@keyframes fall {
    to {
        transform: translateY(110vh) rotate(360deg);
        opacity: 0;
    }
}

@keyframes openLetter {
    from { transform: scale(.5) rotate(-5deg); opacity: 0; }
    to { transform: scale(1) rotate(0); opacity: 1; }
}

@media(max-height: 750px) {
    .tree {
        transform: scale(.8);
        margin-top: -5px;
        margin-bottom: -20px;
    }

    .message {
        font-size: 13px;
    }
}
</style>
</head>

<body>

<div class="stars" id="stars"></div>

<div class="scene">

    <h1>Happy Birthday Sayang ❤️</h1>

    <p class="subtitle">A Special Day For You ✨</p>

    <div class="tree">

        <div class="trunk"></div>

        <div class="branch b1"></div>
        <div class="branch b2"></div>
        <div class="branch b3"></div>
        <div class="branch b4"></div>

        <div class="leaves" id="leaves"></div>

        <div class="ground"></div>
    </div>

    <div class="message">
        Selamat ulang tahun, orang tersayangku ❤️<br>
        Semoga kebahagiaan selalu menyertaimu.<br>
        Teruslah bersinar seperti bintang di langit.<br>
        You are special and deserve the best! 💗
    </div>

    <div class="buttons">
        <button onclick="openLetter()">💌 Open Letter</button>
        <button onclick="toggleMusic()" id="musicBtn">🎵 Play Music</button>
    </div>

</div>

<div class="modal" id="modal">
    <div class="letter">
        <h2>For You, My Love 💗</h2>

        <p>
            Happy Birthday, Sayang! ❤️<br><br>

            Hari ini adalah hari yang spesial,
            karena seseorang yang begitu istimewa
            telah bertambah usia.<br><br>

            Terima kasih sudah menjadi bagian
            dari cerita indah ini.
            Semoga semua harapanmu tercapai,
            selalu sehat, dan selalu bahagia.<br><br>

            Jangan pernah berhenti tersenyum.
            You deserve all the love in the world! 💕
            <br><br>
            With Love ❤️
        </p>

        <button onclick="closeLetter()">Close ❤️</button>
    </div>
</div>

<script>

// Membuat bintang
const stars = document.getElementById("stars");

for(let i = 0; i < 70; i++) {
    const star = document.createElement("span");
    star.className = "star";
    star.innerHTML = "✦";
    star.style.left = Math.random() * 100 + "%";
    star.style.top = Math.random() * 100 + "%";
    star.style.fontSize = (5 + Math.random() * 10) + "px";
    star.style.animationDelay = Math.random() * 3 + "s";
    stars.appendChild(star);
}

// Membuat daun berbentuk hati
const leaves = document.getElementById("leaves");

const positions = [
    [145, 5], [95, 25], [190, 25],
    [55, 65], [125, 55], [215, 65],
    [80, 110], [170, 105], [245, 110],
    [120, 135], [195, 145], [145, 175],
    [30, 100], [260, 75], [110, 5],
    [210, 5], [65, 145], [235, 145]
];

positions.forEach((pos, i) => {
    const leaf = document.createElement("div");
    leaf.className = "leaf";
    leaf.innerHTML = ["❤️", "💗", "💕", "💖"][i % 4];
    leaf.style.left = pos[0] + "px";
    leaf.style.top = pos[1] + "px";
    leaf.style.animationDelay = (2.5 + i * 0.12) + "s";
    leaves.appendChild(leaf);
});

// Hujan hati
function createHeart() {
    const heart = document.createElement("div");
    heart.className = "heart-rain";
    heart.innerHTML = ["❤️", "💗", "💕", "💖"][Math.floor(Math.random() * 4)];

    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = (12 + Math.random() * 20) + "px";
    heart.style.animationDuration = (4 + Math.random() * 4) + "s";

    document.body.appendChild(heart);

    setTimeout(() => heart.remove(), 8000);
}

setInterval(createHeart, 450);

// Surat cinta
function openLetter() {
    document.getElementById("modal").style.display = "flex";
}

function closeLetter() {
    document.getElementById("modal").style.display = "none";
}

// Musik sederhana menggunakan Web Audio API
let audioContext;
let musicTimer;
let playing = false;
let noteIndex = 0;

const melody = [
    261.63, 329.63, 392.00, 329.63,
    293.66, 349.23, 440.00, 349.23,
    261.63, 329.63, 392.00, 523.25
];

function playNote() {
    if(!playing) return;

    const osc = audioContext.createOscillator();
    const gain = audioContext.createGain();

    osc.type = "sine";
    osc.frequency.value = melody[noteIndex % melody.length];

    gain.gain.setValueAtTime(0.0001, audioContext.currentTime);
    gain.gain.exponentialRampToValueAtTime(0.12, audioContext.currentTime + 0.1);
    gain.gain.exponentialRampToValueAtTime(0.0001, audioContext.currentTime + 0.8);

    osc.connect(gain);
    gain.connect(audioContext.destination);

    osc.start();
    osc.stop(audioContext.currentTime + 0.85);

    noteIndex++;
}

function toggleMusic() {
    const btn = document.getElementById("musicBtn");

    if(!playing) {
        audioContext = audioContext || new (
            window.AudioContext || window.webkitAudioContext
        )();

        audioContext.resume();
        playing = true;
        playNote();
        musicTimer = setInterval(playNote, 650);
        btn.innerHTML = "🔇 Stop Music";
    } else {
        playing = false;
        clearInterval(musicTimer);
        btn.innerHTML = "🎵 Play Music";
    }
}

</script>

</body>
</html>

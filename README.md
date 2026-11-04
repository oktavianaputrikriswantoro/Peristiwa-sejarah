
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>History Mind Mapping</title>
<link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;500;600;700;800&family=Patrick+Hand&display=swap" rel="stylesheet">

<style>
:root {
  --cream: #fff8ed;
  --brown: #76533d;
  --pink: #f6dce5;
  --green: #e3edda;
  --blue: #dce9f5;
  --yellow: #faedc9;
  --purple: #eae0f1;
  --peach: #f7e0d2;
}

* { box-sizing: border-box; }

body {
  margin: 0;
  font-family: 'Quicksand', sans-serif;
  background: #f7e9d9;
  color: var(--brown);
}

button { font-family: inherit; cursor: pointer; }

.page {
  min-height: 100vh;
  padding: 35px 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background:
    radial-gradient(#d4b99d 1px, transparent 1px),
    linear-gradient(135deg,#f8eadb,#f3dfce);
  background-size: 18px 18px, auto;
}

.hidden { display: none !important; }

.intro {
  text-align: center;
  max-width: 650px;
  margin-bottom: 30px;
}

.intro h1 {
  font-family: 'Patrick Hand', cursive;
  font-size: clamp(38px,6vw,60px);
  margin: 0;
  color: #805a46;
}

.intro p { color: #987660; }

.choices {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 25px;
}

.choice {
  width: 270px;
  padding: 27px 20px;
  border: 3px solid #fff;
  border-radius: 24px;
  background: #fff8ed;
  color: #79563f;
  box-shadow: 0 9px 0 #dfc4ac, 0 15px 25px #9b75532b;
  transition: .3s;
}

.choice:hover {
  transform: translateY(-8px) rotate(-2deg);
}

.choice .emoji { font-size: 45px; }
.choice h2 { font-family: 'Patrick Hand'; font-size: 26px; }

.back {
  border: 0;
  background: #fff8ed;
  color: #805a46;
  border-radius: 30px;
  padding: 10px 20px;
  margin-bottom: 15px;
  font-weight: 700;
  box-shadow: 0 4px 0 #dfc4ac;
}

.board {
  position: relative;
  width: min(1100px, 100%);
  aspect-ratio: 1.55 / 1;
  min-height: 560px;
  overflow: hidden;
  border: 13px solid #b98b60;
  border-radius: 13px;
  box-shadow: 0 12px 25px #76533d40, inset 0 0 0 5px #d6b18b;
  background:
    radial-gradient(#ffffff16 1px, transparent 1px),
    linear-gradient(135deg,#956b4d,#79543c);
  background-size: 13px 13px, auto;
}

.board::before {
  content: "✦  ✧  ✦";
  position: absolute;
  top: 12px;
  left: 20px;
  color: #f9e4a6;
  font-size: 25px;
  z-index: 2;
}

.board::after {
  content: "✧  ✦  ✧";
  position: absolute;
  bottom: 10px;
  right: 20px;
  color: #f9e4a6;
  font-size: 25px;
  z-index: 2;
}

.arrows {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 1;
}

.arrows path {
  fill: none;
  stroke: #fff5df;
  stroke-width: 3;
  stroke-linecap: round;
  stroke-dasharray: 7 5;
  marker-end: url(#arrow);
}

.center-title {
  position: absolute;
  z-index: 3;
  left: 50%;
  top: 50%;
  transform: translate(-50%,-50%) rotate(-2deg);
  width: 23%;
  min-height: 145px;
  background: #fff0a9;
  border: 5px solid #f8e4a0;
  border-radius: 7px 7px 22px 8px;
  box-shadow: 4px 8px 12px #38231355;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 15px;
}

.center-title::before {
  content: "📌";
  position: absolute;
  top: -25px;
  left: 45%;
  font-size: 30px;
}

.center-title h2 {
  font-family: 'Patrick Hand', cursive;
  font-size: clamp(18px,2.4vw,31px);
  line-height: 1.15;
  margin: 0;
  color: #62452f;
}

.branch {
  position: absolute;
  z-index: 3;
  width: 25%;
  min-height: 115px;
  border: 4px solid #fffaf1;
  border-radius: 24px 10px 25px 12px;
  padding: 12px 13px;
  text-align: center;
  box-shadow: 3px 6px 9px #38231345;
  transition: transform .25s, box-shadow .25s;
  color: #634d40;
}

.branch:hover {
  transform: scale(1.06) rotate(1deg);
  box-shadow: 5px 10px 15px #38231355;
}

.branch:active { transform: scale(.96); }

.branch .symbol {
  font-size: 23px;
  display: block;
  margin-bottom: 3px;
}

.branch h3 {
  font-family: 'Patrick Hand', cursive;
  font-size: clamp(17px,2vw,24px);
  margin: 0 0 5px;
}

.branch p {
  font-size: clamp(9px,1vw,12px);
  line-height: 1.4;
  margin: 0;
  font-weight: 600;
}

.b1 { top: 5%; left: 4%; background: var(--pink); }
.b2 { top: 5%; right: 4%; background: var(--green); }
.b3 { top: 38%; left: 2%; background: var(--yellow); }
.b4 { top: 38%; right: 2%; background: var(--blue); }
.b5 { bottom: 5%; left: 4%; background: var(--purple); }
.b6 { bottom: 5%; right: 4%; background: var(--peach); }

.decoration {
  position: absolute;
  z-index: 2;
  font-size: 32px;
  pointer-events: none;
}
.star1 { top: 30%; left: 30%; }
.star2 { top: 27%; right: 30%; }
.star3 { bottom: 26%; left: 30%; }
.star4 { bottom: 26%; right: 30%; }

.overlay {
  position: fixed;
  inset: 0;
  z-index: 10;
  background: #33251e80;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  backdrop-filter: blur(3px);
}

.popup {
  width: min(470px, 100%);
  max-height: 80vh;
  overflow-y: auto;
  background: #fff9ee;
  border: 6px solid #e6c8ad;
  border-radius: 25px 12px 25px 12px;
  padding: 25px;
  box-shadow: 0 15px 40px #21160f55;
  animation: pop .3s ease;
  position: relative;
}

@keyframes pop {
  from { opacity: 0; transform: scale(.8) translateY(15px); }
  to { opacity: 1; transform: scale(1) translateY(0); }
}

.popup h2 {
  font-family: 'Patrick Hand', cursive;
  font-size: 31px;
  text-align: center;
  margin: 0 0 15px;
  color: #805a46;
}

.popup p {
  font-size: 15px;
  line-height: 1.8;
  color: #725744;
  white-space: pre-line;
}

.close {
  display: block;
  margin: 20px auto 0;
  border: 0;
  padding: 11px 25px;
  border-radius: 25px;
  background: #e9c9d7;
  color: #70485a;
  font-weight: 800;
}

@media(max-width:650px) {
  .page { padding: 20px 9px; }
  .board {
    aspect-ratio: auto;
    min-height: 760px;
    border-width: 8px;
  }
  .center-title {
    width: 36%;
    min-height: 105px;
    top: 50%;
  }
  .center-title h2 { font-size: 18px; }
  .branch {
    width: 35%;
    min-height: 105px;
    padding: 9px 6px;
    border-width: 3px;
  }
  .branch h3 { font-size: 17px; }
  .branch p { font-size: 9px; }
  .b1 { top: 5%; left: 3%; }
  .b2 { top: 5%; right: 3%; }
  .b3 { top: 39%; left: 2%; }
  .b4 { top: 39%; right: 2%; }
  .b5 { bottom: 5%; left: 3%; }
  .b6 { bottom: 5%; right: 3%; }
  .star1 { top: 27%; left: 35%; }
  .star2 { top: 27%; right: 35%; }
  .star3 { bottom: 27%; left: 35%; }
  .star4 { bottom: 27%; right: 35%; }
  .arrows { opacity: .8; }
  .popup { padding: 20px; }
}
</style>
</head>

<body>

<section class="page" id="home">
  <div class="intro">
    <h1>✿ History Mind Mapping ✿</h1>
    <p>Belajar sejarah dengan cara yang lebih menyenangkan dan menarik.</p>
    <p><b>Pilih materi yang ingin kamu pelajari!</b></p>
  </div>

  <div class="choices">
    <button class="choice" onclick="openMap('pki')">
      <div class="emoji">📜</div>
      <h2>Pemberontakan PKI Madiun 1948</h2>
      <p>Pelajari sejarah peristiwa Madiun tahun 1948.</p>
    </button>

    <button class="choice" onclick="openMap('azis')">
      <div class="emoji">🕊️</div>
      <h2>Peristiwa Andi Azis</h2>
      <p>Pelajari peristiwa yang terjadi di Makassar tahun 1950.</p>
    </button>
  </div>
</section>

<section class="page hidden" id="mindmap">
  <button class="back" onclick="goHome()">← Kembali ke pilihan materi</button>

  <div class="board">
    <svg class="arrows" viewBox="0 0 1000 640" preserveAspectRatio="none">
      <defs>
        <marker id="arrow" markerWidth="8" markerHeight="8"
          refX="6" refY="3" orient="auto">
          <path d="M0,0 L6,3 L0,6" fill="#fff5df"/>
        </marker>
      </defs>
      <path d="M470 290 Q380 190 280 130"/>
      <path d="M530 290 Q620 190 720 130"/>
      <path d="M400 320 Q280 320 250 320"/>
      <path d="M600 320 Q720 320 750 320"/>
      <path d="M460 365 Q370 465 280 520"/>
      <path d="M540 365 Q630 465 720 520"/>
    </svg>

    <div class="center-title">
      <h2 id="mapTitle">Judul Peristiwa</h2>
    </div>

    <button class="branch b1" onclick="showDetail(0)">
      <span class="symbol">🌷</span>
      <h3>Pengertian</h3>
      <p id="short0"></p>
    </button>

    <button class="branch b2" onclick="showDetail(1)">
      <span class="symbol">🌼</span>
      <h3>Sebab</h3>
      <p id="short1"></p>
    </button>

    <button class="branch b3" onclick="showDetail(2)">
      <span class="symbol">📖</span>
      <h3>Jalannya Peristiwa</h3>
      <p id="short2"></p>
    </button>

    <button class="branch b4" onclick="showDetail(3)">
      <span class="symbol">🕊️</span>
      <h3>Akhir Peristiwa</h3>
      <p id="short3"></p>
    </button>

    <button class="branch b5" onclick="showDetail(4)">
      <span class="symbol">⭐</span>
      <h3>Tokoh</h3>
      <p id="short4"></p>
    </button>

    <button class="branch b6" onclick="showDetail(5)">
      <span class="symbol">💌</span>
      <h3>Kesimpulan</h3>
      <p id="short5"></p>
    </button>

    <span class="decoration star1">✦</span>
    <span class="decoration star2">✧</span>
    <span class="decoration star3">✧</span>
    <span class="decoration star4">✦</span>
  </div>
</section>

<div class="overlay hidden" id="overlay" onclick="closeDetail(event)">
  <div class="popup">
    <h2 id="popupTitle"></h2>
    <p id="popupText"></p>
    <button class="close" onclick="hideDetail()">Tutup ✿</button>
  </div>
</div>

<script>
const lessons = {
  pki: {
    title: "Pemberontakan PKI Madiun 1948",
    details: [
      "Pemberontakan PKI Madiun adalah peristiwa pemberontakan yang terjadi pada 18 September 1948 di Madiun, Jawa Timur. Peristiwa ini berkaitan dengan upaya PKI mengambil alih kekuasaan dan membentuk pemerintahan berdasarkan ideologi komunis.",
      "• Adanya ketegangan politik antara pemerintah dan kelompok kiri.\n• Kekecewaan terhadap kebijakan pemerintah dan program reorganisasi serta rasionalisasi tentara.\n• Persaingan pengaruh politik setelah Indonesia merdeka.\n• Keinginan kelompok PKI untuk memperluas kekuasaannya.",
      "• Pada 18 September 1948, kelompok PKI melakukan pemberontakan di Madiun.\n• Mereka menguasai sejumlah tempat penting dan mengumumkan pembentukan pemerintahan baru.\n• Pemerintah Indonesia kemudian mengambil tindakan untuk mengatasi pemberontakan.\n• Pasukan pemerintah bergerak menuju Madiun untuk memulihkan keamanan.",
      "• Pasukan pemerintah berhasil menguasai kembali Madiun.\n• Musso tewas pada Oktober 1948.\n• Amir Sjarifuddin ditangkap pada Desember 1948 dan kemudian dihukum mati.\n• Pemberontakan berhasil ditumpas oleh pemerintah.",
      "• Musso: pemimpin PKI yang berperan dalam pemberontakan.\n• Amir Sjarifuddin: tokoh yang ikut memimpin gerakan.\n• Soekarno: Presiden Indonesia saat peristiwa berlangsung.\n• Mohammad Hatta: Wakil Presiden yang menyampaikan sikap pemerintah.\n• Jenderal Sudirman: Panglima Besar yang memimpin perjuangan mempertahankan negara.",
      "Peristiwa PKI Madiun menunjukkan pentingnya menjaga persatuan, kestabilan negara, dan tidak menggunakan kekerasan untuk menyelesaikan perbedaan politik. Sebagai warga negara, kita harus menjaga keutuhan NKRI."
    ]
  },

  azis: {
    title: "Peristiwa Andi Azis",
    details: [
      "Peristiwa Andi Azis adalah pemberontakan yang terjadi di Makassar, Sulawesi Selatan, pada April 1950. Gerakan ini dipimpin oleh Andi Azis, seorang mantan perwira KNIL, yang menolak masuknya pasukan APRIS dari unsur TNI ke Makassar.",
      "• Andi Azis dan kelompoknya menolak kedatangan pasukan APRIS dari unsur TNI.\n• Adanya ketegangan antara kelompok bekas KNIL dan TNI.\n• Keinginan mempertahankan pengaruh pasukan bekas KNIL di wilayah Negara Indonesia Timur.\n• Perselisihan mengenai proses penyatuan negara.",
      "• Pada 5 April 1950, kelompok Andi Azis melakukan aksi bersenjata di Makassar.\n• Mereka menguasai beberapa tempat penting dan menahan sejumlah anggota APRIS.\n• Pemerintah pusat memberikan ultimatum kepada Andi Azis agar segera datang ke Jakarta.\n• Pemerintah juga mengirim pasukan untuk memulihkan keamanan.",
      "• Andi Azis datang ke Jakarta pada 15 April 1950.\n• Ia kemudian ditangkap dan diproses oleh pemerintah.\n• Pasukan pemerintah berhasil memulihkan keadaan di Makassar.\n• Pemberontakan Andi Azis akhirnya dapat diatasi.",
      "• Andi Azis: pemimpin pemberontakan di Makassar.\n• Soekarno: Presiden Republik Indonesia.\n• Mohammad Hatta: Wakil Presiden dan tokoh pemerintah.\n• A.H. Nasution: tokoh militer yang berperan dalam penanganan keamanan.\n• Pasukan APRIS: pasukan yang terlibat dalam upaya pemulihan keamanan.",
      "Peristiwa Andi Azis mengajarkan pentingnya persatuan dan kesatuan bangsa. Perbedaan pendapat serta kepentingan kelompok seharusnya diselesaikan melalui musyawarah, bukan dengan pemberontakan atau kekerasan."
    ]
  }
};

const headings = [
  "Pengertian",
  "Sebab",
  "Jalannya Peristiwa",
  "Akhir Peristiwa",
  "Tokoh",
  "Kesimpulan dan Nilai yang Dipelajari"
];

let currentLesson = null;

function openMap(type) {
  currentLesson = lessons[type];

  document.getElementById("home").classList.add("hidden");
  document.getElementById("mindmap").classList.remove("hidden");
  document.getElementById("mapTitle").textContent = currentLesson.title;

  currentLesson.details.forEach((detail, index) => {
    document.getElementById("short" + index).textContent =
      detail.split("\n")[0].substring(0, 55) + "...";
  });
}

function showDetail(index) {
  document.getElementById("popupTitle").textContent = headings[index];
  document.getElementById("popupText").textContent =
    currentLesson.details[index];

  document.getElementById("overlay").classList.remove("hidden");
}

function hideDetail() {
  document.getElementById("overlay").classList.add("hidden");
}

function closeDetail(event) {
  if (event.target.id === "overlay") hideDetail();
}

function goHome() {
  hideDetail();
  document.getElementById("mindmap").classList.add("hidden");
  document.getElementById("home").classList.remove("hidden");
}
</script>

</body>
</html>

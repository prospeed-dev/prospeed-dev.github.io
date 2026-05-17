# KeraAutoParts.github.io
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width,initial-scale=1.0" />

<title>KERA Automotive – Kerala's Premier Auto Parts</title>

<style>
:root{
  --gold:#C9A84C;
  --gold2:#F0C94A;
  --neon:#00FFB2;
  --dark:#0A0B0F;
  --surf:#161A22;
  --surf2:#1E2330;
  --text:#E8E6E0;
  --muted:#6B7080;
}

*{
  margin:0;
  padding:0;
  box-sizing:border-box;
}

html{
  scroll-behavior:smooth;
}

body{
  background:var(--dark);
  color:var(--text);
  font-family:'Segoe UI',sans-serif;
  overflow-x:hidden;
  min-height:100vh;
}

button{
  cursor:pointer;
  font-family:inherit;
}

input,select,textarea{
  font-family:inherit;
}

::-webkit-scrollbar{
  width:6px;
}

::-webkit-scrollbar-thumb{
  background:var(--gold);
  border-radius:10px;
}

::-webkit-scrollbar-track{
  background:#111;
}

/* BACKGROUND */

#bgCanvas{
  position:fixed;
  inset:0;
  z-index:0;
  pointer-events:none;
}

/* NAV */

nav{
  position:sticky;
  top:0;
  z-index:999;
  height:70px;
  background:rgba(10,11,15,.92);
  backdrop-filter:blur(14px);
  border-bottom:1px solid rgba(201,168,76,.2);

  display:flex;
  align-items:center;
  justify-content:space-between;

  padding:0 22px;
}

.logoWrap{
  display:flex;
  align-items:center;
  gap:10px;
}

.logoIcon{
  font-size:28px;
  animation:spin 8s linear infinite;
}

@keyframes spin{
  to{
    transform:rotate(360deg);
  }
}

.logoText{
  font-size:24px;
  font-weight:900;
  font-family:Georgia,serif;

  background:linear-gradient(90deg,var(--gold),var(--gold2));
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
}

.logoSub{
  font-size:9px;
  letter-spacing:.2em;
  color:var(--muted);
}

.navBtns{
  display:flex;
  gap:10px;
  flex-wrap:wrap;
}

.navBtn{
  border:none;
  background:transparent;
  border:1px solid rgba(201,168,76,.25);

  color:var(--text);

  padding:9px 16px;
  border-radius:10px;

  transition:.3s;
  font-size:12px;
  font-weight:700;
}

.navBtn:hover,
.navBtn.active{
  background:linear-gradient(135deg,var(--gold),var(--gold2));
  color:#000;
}

/* PAGE */

.page{
  display:none;
  position:relative;
  z-index:2;

  max-width:1300px;
  margin:auto;

  padding:28px;
}

.page.active{
  display:block;
}

/* HERO */

.hero{
  text-align:center;
  padding:80px 20px 60px;
  position:relative;
}

.badge{
  display:inline-block;

  background:rgba(201,168,76,.12);
  border:1px solid rgba(201,168,76,.3);

  color:var(--gold);

  padding:8px 20px;
  border-radius:999px;

  font-size:11px;
  letter-spacing:.2em;

  margin-bottom:24px;
}

.hero h1{
  font-size:clamp(2.7rem,7vw,5.5rem);
  line-height:1.1;
  font-family:Georgia,serif;
  margin-bottom:20px;
}

.hero h1 span{
  background:linear-gradient(135deg,var(--gold),#fff,var(--gold2));
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
}

.hero p{
  max-width:620px;
  margin:auto;
  color:var(--muted);
  line-height:1.7;
  margin-bottom:36px;
}

.heroBtns{
  display:flex;
  justify-content:center;
  gap:14px;
  flex-wrap:wrap;
}

/* BUTTONS */

.btnPrimary{
  border:none;
  border-radius:12px;

  padding:14px 28px;

  background:linear-gradient(135deg,var(--gold),var(--gold2));

  color:#000;
  font-weight:900;

  transition:.3s;
}

.btnPrimary:hover{
  transform:translateY(-4px);
}

.btnOutline{
  border:1px solid rgba(201,168,76,.5);
  background:transparent;
  color:var(--gold);

  border-radius:12px;
  padding:14px 28px;

  font-weight:800;
}

.btnOutline:hover{
  background:rgba(201,168,76,.08);
}

.btnWA{
  border:none;
  border-radius:12px;

  padding:14px 28px;

  background:linear-gradient(135deg,#25D366,#128C7E);

  color:#fff;
  font-weight:800;

  transition:.3s;
}

.btnWA:hover{
  transform:translateY(-4px);
}

/* SECTION */

.sectionTitle{
  text-align:center;
  margin-bottom:28px;
}

.sectionTitle h2{
  font-size:28px;
  margin-bottom:8px;
}

.sectionTitle p{
  color:var(--muted);
  font-size:14px;
}

/* GRID */

.carGrid{
  display:grid;
  grid-template-columns:repeat(auto-fill,minmax(230px,1fr));
  gap:18px;
}

/* CARD */

.carCard{
  background:linear-gradient(135deg,var(--surf),var(--surf2));

  border:1px solid rgba(201,168,76,.18);

  border-radius:20px;

  padding:18px;

  transition:.35s;

  text-align:center;
  position:relative;

  overflow:hidden;
}

.carCard:hover{
  transform:translateY(-10px);
  border-color:var(--gold);

  box-shadow:0 20px 40px rgba(0,0,0,.45);
}

.carCard.selected{
  border-color:var(--gold);

  box-shadow:0 0 25px rgba(201,168,76,.25);
}

.csvg{
  width:100%;
  height:140px;
  overflow:hidden;
  margin-bottom:12px;
  border-radius:12px;
  background:#111;
}

.csvg img{
  width:100%;
  height:100%;
  object-fit:cover;
  transition:.3s;
}

.ccard:hover .csvg img{
  transform:scale(1.08);
}

.carBrand{
  color:var(--gold);
  font-size:11px;
  letter-spacing:.15em;
  margin-bottom:5px;
}

.carModel{
  font-size:18px;
  font-weight:800;
  margin-bottom:6px;
}

.carYear{
  color:var(--muted);
  font-size:12px;
  margin-bottom:16px;
}

.cardBtn{
  width:100%;
  border:none;
  border-radius:10px;

  background:linear-gradient(135deg,#25D366,#128C7E);

  color:#fff;
  font-weight:800;

  padding:11px;
}

/* PARTS */

.partsGrid{
  display:grid;
  grid-template-columns:repeat(auto-fill,minmax(250px,1fr));
  gap:18px;
}

.partCard{
  background:linear-gradient(135deg,var(--surf),var(--surf2));

  border-radius:18px;

  border:1px solid rgba(201,168,76,.18);

  padding:18px;

  transition:.35s;
}

.partCard:hover{
  transform:translateY(-10px);
  border-color:var(--gold);
}

.partImage{
  height:160px;
  border-radius:14px;

  background:#10131A;

  display:flex;
  align-items:center;
  justify-content:center;

  font-size:50px;

  margin-bottom:16px;

  position:relative;
}

.stock{
  position:absolute;
  bottom:10px;
  left:10px;

  padding:5px 10px;
  border-radius:8px;

  font-size:10px;
  font-weight:800;
}

.in{
  background:rgba(74,222,128,.14);
  color:#4ade80;
}

.low{
  background:rgba(201,168,76,.15);
  color:var(--gold);
}

.partName{
  font-size:15px;
  font-weight:800;
  margin-bottom:6px;
}

.partSku{
  font-size:10px;
  color:var(--muted);
  margin-bottom:12px;
}

.partDesc{
  color:var(--muted);
  line-height:1.6;
  font-size:12px;

  margin-bottom:16px;
}

/* MODAL */

.overlay{
  position:fixed;
  inset:0;

  background:rgba(0,0,0,.72);

  z-index:1000;

  display:none;
}

.modal{
  position:fixed;
  inset:0;

  z-index:1001;

  display:none;
  align-items:center;
  justify-content:center;

  padding:20px;
}

.modal.active{
  display:flex;
}

.modalBox{
  width:100%;
  max-width:620px;

  background:var(--surf);

  border-radius:24px;

  border:1px solid rgba(201,168,76,.25);

  overflow:hidden;
}

.modalHead{
  padding:22px;

  border-bottom:1px solid rgba(201,168,76,.18);

  display:flex;
  align-items:center;
  justify-content:space-between;
}

.modalHead h2{
  color:var(--gold);
}

.closeBtn{
  border:none;
  background:var(--surf2);

  color:#fff;

  padding:8px 14px;

  border-radius:10px;
}

.modalBody{
  padding:24px;

  display:flex;
  flex-direction:column;
  gap:16px;
}

.formRow{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:14px;
}

@media(max-width:600px){
  .formRow{
    grid-template-columns:1fr;
  }
}

.formGroup{
  display:flex;
  flex-direction:column;
  gap:8px;
}

.formGroup label{
  font-size:12px;
  color:var(--muted);
  font-weight:700;
}

.formGroup input,
.formGroup select,
.formGroup textarea{
  background:var(--surf2);

  border:1px solid rgba(201,168,76,.2);

  color:#fff;

  border-radius:10px;

  padding:12px 14px;

  outline:none;
}

.formGroup input:focus,
.formGroup select:focus,
.formGroup textarea:focus{
  border-color:var(--gold);
}

.whatsappSend{
  border:none;

  background:linear-gradient(135deg,#25D366,#128C7E);

  color:#fff;

  font-weight:900;

  padding:16px;

  border-radius:14px;
}

/* FOOTER */

footer{
  text-align:center;

  padding:40px 20px;

  border-top:1px solid rgba(201,168,76,.1);

  margin-top:40px;
}

.footerLogo{
  font-size:24px;
  font-weight:900;
  font-family:Georgia,serif;

  background:linear-gradient(90deg,var(--gold),var(--gold2));
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;

  margin-bottom:12px;
}

.footerText{
  color:var(--muted);
  font-size:13px;
}

/* FLOATING WA */

.floatingWA{
  position:fixed;
  right:20px;
  bottom:20px;

  width:60px;
  height:60px;

  border-radius:50%;

  background:#25D366;

  display:flex;
  align-items:center;
  justify-content:center;

  font-size:28px;

  z-index:999;

  text-decoration:none;

  box-shadow:0 10px 30px rgba(37,211,102,.4);
}
</style>
</head>

<body>

<canvas id="bgCanvas"></canvas>

<!-- NAV -->

<nav>
  <div class="logoWrap">
    <div class="logoIcon">⚙️</div>

    <div>
      <div class="logoText">KERA</div>
      <div class="logoSub">KERALA AUTOMOTIVE</div>
    </div>
  </div>

  <div class="navBtns">
    <button class="navBtn active" onclick="showPage('home',this)">Home</button>

    <button class="navBtn" onclick="showPage('catalog',this)">Catalog</button>

    <button class="navBtn" onclick="openBooking()">Book</button>
  </div>
</nav>

<!-- HOME -->

<div class="page active" id="homePage">

  <div class="hero">

    <div class="badge">
      ★ GOD'S OWN AUTOMOTIVE HOUSE ★
    </div>

    <h1>
      <span>Kerala's Premier</span><br>
      Auto Parts Hub
    </h1>

    <p>
      Genuine OEM & aftermarket automotive parts for premium and daily-use vehicles across Kerala.
    </p>

    <div class="heroBtns">
      <button class="btnPrimary" onclick="showPage('catalog')">
        Browse Catalog
      </button>

      <button class="btnWA" onclick="openBooking()">
        WhatsApp Booking
      </button>
    </div>
  </div>

  <div class="sectionTitle">
    <h2>Select Your Vehicle</h2>
    <p>Choose a car model to load its catalog</p>
  </div>

  <div class="carGrid" id="carGrid"></div>

</div>

<!-- CATALOG -->

<div class="page" id="catalogPage">

  <div class="sectionTitle">
    <h2 id="catalogTitle">
      Vehicle Parts
    </h2>

    <p id="catalogSub">
      Select a vehicle first
    </p>
  </div>

  <div class="partsGrid" id="partsGrid"></div>

</div>

<!-- MODAL -->

<div class="overlay" id="overlay" onclick="closeBooking()"></div>

<div class="modal" id="bookingModal">

  <div class="modalBox">

    <div class="modalHead">
      <div>
        <h2>WhatsApp Booking</h2>
      </div>

      <button class="closeBtn" onclick="closeBooking()">
        ✕
      </button>
    </div>

    <div class="modalBody">

      <div class="formRow">

        <div class="formGroup">
          <label>Full Name</label>
          <input type="text" id="customerName" />
        </div>

        <div class="formGroup">
          <label>Phone</label>
          <input type="tel" id="customerPhone" />
        </div>

      </div>

      <div class="formRow">

        <div class="formGroup">
          <label>Vehicle</label>

          <select id="customerCar"></select>
        </div>

        <div class="formGroup">
          <label>District</label>

          <select id="customerDistrict"></select>
        </div>

      </div>

      <div class="formGroup">
        <label>Parts Required</label>

        <textarea rows="4" id="customerParts"></textarea>
      </div>

      <button class="whatsappSend" onclick="sendWhatsApp()">
        Send via WhatsApp
      </button>

    </div>

  </div>

</div>

<!-- FOOTER -->

<footer>
  <div class="footerLogo">
    KERA AUTOMOTIVE
  </div>

  <div class="footerText">
    Kerala's Premier Automotive House • Genuine OEM & Aftermarket Parts
  </div>
</footer>

<a class="floatingWA" href="https://wa.me/918137804878" target="_blank">
  💬
</a>
<script>
const WA_NUMBER = "918137804878";

/* =========================
   CAR DATA
========================= */

const CARS = [
  {
    id:"innova",
    brand:"Toyota",
    model:"Innova Crysta",
    year:"2023",
    img:"https://images.unsplash.com/photo-1494976388531-d1058494cdd8?q=80&w=1200&auto=format&fit=crop"
  },

  {
    id:"swift",
    brand:"Maruti",
    model:"Swift",
    year:"2023",
    img:"https://images.unsplash.com/photo-1503376780353-7e6692767b70?q=80&w=1200&auto=format&fit=crop"
  },

  {
    id:"bmw3",
    brand:"BMW",
    model:"3 Series",
    year:"2024",
    img:"https://images.unsplash.com/photo-1555215695-3004980ad54e?q=80&w=1200&auto=format&fit=crop"
  },

  {
    id:"fortuner",
    brand:"Toyota",
    model:"Fortuner",
    year:"2023",
    img:"https://images.unsplash.com/photo-1549399542-7e3f8b79c341?q=80&w=1200&auto=format&fit=crop"
  },

  {
    id:"creta",
    brand:"Hyundai",
    model:"Creta",
    year:"2024",
    img:"https://images.unsplash.com/photo-1492144534655-ae79c964c9d7?q=80&w=1200&auto=format&fit=crop"
  },

  {
    id:"nexon",
    brand:"Tata",
    model:"Nexon EV",
    year:"2024",
    img:"https://images.unsplash.com/photo-1502877338535-766e1452684a?q=80&w=1200&auto=format&fit=crop"
  },

  {
    id:"kia",
    brand:"Kia",
    model:"Seltos",
    year:"2024",
    img:"https://images.unsplash.com/photo-1511919884226-fd3cad34687c?q=80&w=1200&auto=format&fit=crop"
  },

  {
    id:"audi",
    brand:"Audi",
    model:"Q7",
    year:"2024",
    img:"https://images.unsplash.com/photo-1606664515524-ed2f786a0bd6?q=80&w=1200&auto=format&fit=crop"
  }
];

/* =========================
   DISTRICTS
========================= */

const districts = [
  "Thiruvananthapuram",
  "Kollam",
  "Pathanamthitta",
  "Alappuzha",
  "Kottayam",
  "Idukki",
  "Ernakulam",
  "Thrissur",
  "Palakkad",
  "Malappuram",
  "Kozhikode",
  "Wayanad",
  "Kannur",
  "Kasaragod"
];

/* =========================
   PARTS
========================= */

const parts = [
  {
    icon:"⚙️",
    name:"Engine Block"
  },

  {
    icon:"🛑",
    name:"Brake Pads"
  },

  {
    icon:"💡",
    name:"Headlight Assembly"
  },

  {
    icon:"⚡",
    name:"Battery"
  },

  {
    icon:"🔧",
    name:"Clutch Kit"
  },

  {
    icon:"🚗",
    name:"Front Bumper"
  }
];

let selectedCar = null;

/* =========================
   INITIAL LOAD
========================= */

window.addEventListener("DOMContentLoaded",()=>{

  const carGrid = document.getElementById("carGrid");

  /* LOAD CARDS */

  CARS.forEach(car=>{

    const card = document.createElement("div");

    card.className = "carCard";

    card.innerHTML = `
      <div class="csvg">
        <img src="${car.img}" alt="${car.model}">
      </div>

      <div class="carBrand">
        ${car.brand}
      </div>

      <div class="carModel">
        ${car.model}
      </div>

      <div class="carYear">
        ${car.year}
      </div>

      <button class="cardBtn">
        Select Vehicle
      </button>
    `;

    card.onclick = ()=>selectCar(car,card);

    carGrid.appendChild(card);
  });

  /* LOAD DISTRICTS */

  const districtSelect =
    document.getElementById("customerDistrict");

  districts.forEach(d=>{

    districtSelect.innerHTML += `
      <option value="${d}">
        ${d}
      </option>
    `;
  });

  /* LOAD VEHICLES */

  const carSelect =
    document.getElementById("customerCar");

  CARS.forEach(c=>{

    carSelect.innerHTML += `
      <option value="${c.brand} ${c.model}">
        ${c.brand} ${c.model}
      </option>
    `;
  });

  renderParts();

  startParticles();
});

/* =========================
   PAGE SWITCH
========================= */

function showPage(name,btn){

  document.querySelectorAll(".page")
    .forEach(p=>p.classList.remove("active"));

  document.getElementById(name + "Page")
    .classList.add("active");

  if(btn){

    document.querySelectorAll(".navBtn")
      .forEach(n=>n.classList.remove("active"));

    btn.classList.add("active");
  }
}

/* =========================
   SELECT CAR
========================= */

function selectCar(car,card){

  selectedCar = car;

  document.querySelectorAll(".carCard")
    .forEach(c=>c.classList.remove("selected"));

  card.classList.add("selected");

  document.getElementById("catalogTitle")
    .textContent =
      `${car.brand} ${car.model} Parts`;

  document.getElementById("catalogSub")
    .textContent =
      `Premium OEM inventory for ${car.year}`;

  showPage("catalog");
}

/* =========================
   RENDER PARTS
========================= */

function renderParts(){

  const grid =
    document.getElementById("partsGrid");

  grid.innerHTML = "";

  parts.forEach(p=>{

    const stock =
      Math.floor(Math.random()*10)+1;

    const cls =
      stock > 4 ? "in" : "low";

    const status =
      stock > 4 ? "In Stock" : "Low Stock";

    const div =
      document.createElement("div");

    div.className = "partCard";

    div.innerHTML = `
      <div class="partImage">

        ${p.icon}

        <div class="stock ${cls}">
          ${status}
        </div>

      </div>

      <div class="partName">
        ${p.name}
      </div>

      <div class="partSku">
        SKU-${Math.random()
          .toString(36)
          .substring(2,8)
          .toUpperCase()}
      </div>

      <div class="partDesc">
        Genuine OEM automotive component
        with premium warranty support.
      </div>

      <button class="cardBtn"
        onclick="openBooking('${p.name}')">
        Book Part
      </button>
    `;

    grid.appendChild(div);
  });
}

/* =========================
   BOOKING MODAL
========================= */

function openBooking(part=""){

  document.getElementById("overlay")
    .style.display = "block";

  document.getElementById("bookingModal")
    .classList.add("active");

  if(part){

    document.getElementById("customerParts")
      .value = part;
  }

  if(selectedCar){

    document.getElementById("customerCar").value =
      `${selectedCar.brand} ${selectedCar.model}`;
  }
}

function closeBooking(){

  document.getElementById("overlay")
    .style.display = "none";

  document.getElementById("bookingModal")
    .classList.remove("active");
}

/* =========================
   WHATSAPP
========================= */

function sendWhatsApp(){

  const name =
    document.getElementById("customerName").value;

  const phone =
    document.getElementById("customerPhone").value;

  const vehicle =
    document.getElementById("customerCar").value;

  const district =
    document.getElementById("customerDistrict").value;

  const reqParts =
    document.getElementById("customerParts").value;

  if(!name || !phone){

    alert("Please fill required fields");

    return;
  }

  let msg = `
🚗 *KERA AUTOMOTIVE BOOKING*

👤 Name: ${name}

📞 Phone: ${phone}

🚙 Vehicle: ${vehicle}

📍 District: ${district}

🔧 Parts:
${reqParts}
`;

  const url =
    `https://wa.me/${WA_NUMBER}?text=${encodeURIComponent(msg)}`;

  window.open(url,"_blank");
}

/* =========================
   BACKGROUND PARTICLES
========================= */

function startParticles(){

  const canvas =
    document.getElementById("bgCanvas");

  const ctx =
    canvas.getContext("2d");

  let w,h,particles;

  function resize(){

    w = canvas.width =
      window.innerWidth;

    h = canvas.height =
      window.innerHeight;

    particles = [];

    for(let i=0;i<70;i++){

      particles.push({

        x:Math.random()*w,
        y:Math.random()*h,

        r:Math.random()*2,

        dx:(Math.random()-.5)*0.5,
        dy:(Math.random()-.5)*0.5
      });
    }
  }

  resize();

  window.addEventListener("resize",resize);

  function animate(){

    ctx.clearRect(0,0,w,h);

    particles.forEach(p=>{

      p.x += p.dx;
      p.y += p.dy;

      if(p.x < 0 || p.x > w)
        p.dx *= -1;

      if(p.y < 0 || p.y > h)
        p.dy *= -1;

      ctx.beginPath();

      ctx.arc(
        p.x,
        p.y,
        p.r,
        0,
        Math.PI*2
      );

      ctx.fillStyle =
        "rgba(201,168,76,.4)";

      ctx.fill();
    });

    requestAnimationFrame(animate);
  }

  animate();
}
</script>
</body>
</html>

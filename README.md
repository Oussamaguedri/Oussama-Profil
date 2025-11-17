<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="utf-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1"/>
<title>Oussama Guedri – Maschinenbau | Fertigung | Qualität</title>
<meta name="description" content="Maschinenbauingenieur mit Erfahrung in Fertigung, Simulation, Prozessoptimierung & Qualitätsmanagement. Standort Hannover. Remote/Onsite.">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;900&display=swap" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>

<style>
html { scroll-behavior: smooth; }
body { font-family: "Inter", sans-serif; }
[data-reveal] { opacity:0; transform:translateY(20px); transition:all .8s ease; }
.reveal-visible { opacity:1 !important; transform:translateY(0) !important; }

/* Hero Animations */
@keyframes float {0%{transform:translateY(0)}50%{transform:translateY(-10px)}100%{transform:translateY(0)}}
.float { animation: float 5s ease-in-out infinite; }

/* Button Components */
.btn-primary { @apply inline-flex items-center px-5 py-3 rounded-xl bg-blue-600 text-white font-semibold shadow hover:bg-blue-700 transition; }
.btn-secondary { @apply inline-flex items-center px-5 py-3 rounded-xl border border-slate-300 font-semibold hover:border-blue-400 transition; }

/* Dark mode */
.dark body { background:#0f1115; color:#e6e6e6; }
.dark .card { background:#1b1e24 !important; border-color:#2d313a !important; }
</style>
</head>

<body class="bg-slate-50 text-slate-900">

<!-- ========== NAVIGATION ========== -->
<header class="sticky top-0 bg-white/80 backdrop-blur border-b border-slate-200 z-40">
  <div class="max-w-6xl mx-auto flex justify-between items-center px-4 py-3">
    <a href="#top" class="font-bold text-lg">Oussama Guedri</a>
    <nav class="hidden md:flex gap-6 text-sm font-medium">
      <a href="#leistungen">Leistungen</a>
      <a href="#referenzen">Referenzen</a>
      <a href="#skills">Skills</a>
      <a href="#kontakt">Kontakt</a>
    </nav>
    <button id="toggleDark" class="text-sm px-3 py-1 border rounded-lg">🌓</button>
  </div>
</header>

<!-- ========== HERO ========== -->
<section id="top" class="relative min-h-[90vh] flex items-center overflow-hidden">
  <div class="absolute inset-0 bg-cover bg-center scale-110 opacity-80"
       style="background-image:url('consulting-bg.jpg')" data-parallax></div>
  <div class="absolute inset-0 bg-white/80 backdrop-blur-sm"></div>

  <div class="relative max-w-6xl mx-auto grid lg:grid-cols-2 gap-10 px-4 py-24">
    <div data-reveal>
      <span class="text-xs font-semibold uppercase text-blue-700 bg-blue-100 px-3 py-1 rounded-full">
        Verfügbar ab sofort
      </span>

      <h1 class="text-4xl md:text-6xl font-extrabold leading-tight mt-4">
        Oussama Guedri<br>
        <span class="text-blue-700">Maschinenbauingenieur</span>
      </h1>

      <p class="mt-4 text-slate-700 max-w-xl">
        Erfahrung in Antriebstechnik, Fertigung, Simulation, Lean-Production & Qualitätsmanagement.
        Standort: Hannover – remote oder vor Ort.
      </p>

      <div class="flex gap-3 mt-6">
        <a href="mailto:oussamaguedri@gmail.com" class="btn-primary">📩 E-Mail</a>
        <a href="tel:+491637254664" class="btn-secondary">📞 Anrufen</a>
      </div>
    </div>

    <div class="flex justify-center" data-reveal>
      <img src="profile.png" class="w-[360px] h-[460px] object-cover rounded-3xl shadow-2xl float"/>
    </div>
  </div>
</section>

<!-- ========== LEISTUNGEN ========== -->
<section id="leistungen" class="py-24">
  <div class="max-w-6xl mx-auto px-4">
    <h2 class="text-3xl font-extrabold" data-reveal>Leistungen</h2>

    <div class="grid md:grid-cols-3 gap-6 mt-10">
      <div class="card p-6 rounded-2xl border bg-white" data-reveal>
        <h3 class="font-bold text-lg">Fertigung & Produktion</h3>
        <ul class="mt-3 text-sm text-slate-700 space-y-1 list-disc list-inside">
          <li>Prozessoptimierung</li>
          <li>Konstruktion & Betriebsmittel</li>
          <li>Simulation & Automatisierung</li>
        </ul>
      </div>

      <div class="card p-6 rounded-2xl border bg-white" data-reveal>
        <h3 class="font-bold text-lg">Supply Chain & Planung</h3>
        <ul class="mt-3 text-sm text-slate-700 space-y-1 list-disc list-inside">
          <li>Einkauf & Lieferanten</li>
          <li>ERP/Power BI Workflows</li>
          <li>KPI & Prozessmodellierung</li>
        </ul>
      </div>

      <div class="card p-6 rounded-2xl border bg-white" data-reveal>
        <h3 class="font-bold text-lg">Qualitätsmanagement</h3>
        <ul class="mt-3 text-sm text-slate-700 space-y-1 list-disc list-inside">
          <li>FMEA, PPAP, 8D, ISO 9001</li>
          <li>Messtechnik & Prüfplanung</li>
          <li>Toleranz & Prozessverbesserung</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- ========== REFERENZEN LOGOS (GITHUB JSON) ========== -->
<section id="referenzen" class="py-24 bg-white border-y">
  <div class="max-w-6xl mx-auto px-4">
    <h2 class="text-3xl font-extrabold" data-reveal>Unternehmen & Projekte</h2>

    <div id="logoScroller" class="flex gap-4 overflow-x-auto mt-8 py-2"></div>
  </div>
</section>

<script>
// GitHub Logos laden
const GITHUB_USER = "DEIN_GITHUB_USER";
const REPO = "DEIN_REPO";
async function loadLogos(){
  const base = `https://raw.githubusercontent.com/${GITHUB_USER}/${REPO}/main/logos/`;
  const url = `https://raw.githubusercontent.com/${GITHUB_USER}/${REPO}/main/data/logos.json`;
  const data = await fetch(url).then(r=>r.json());
  document.getElementById("logoScroller").innerHTML = data.map(l=>`
    <div class="card min-w-[180px] p-4 rounded-xl border bg-white text-center">
      <img src="${base+l.img}" class="h-12 object-contain mx-auto mb-2"/>
      <p class="text-sm font-medium">${l.name}</p>
    </div>`).join("");
}
loadLogos();
</script>

<!-- ========== SKILLS ========== -->
<section id="skills" class="py-24">
  <div class="max-w-6xl mx-auto px-4">
    <h2 class="text-3xl font-extrabold" data-reveal>Skills & Tools</h2>

    <div class="grid md:grid-cols-2 gap-6 mt-10">
      <div class="card p-6 rounded-2xl border bg-white" data-reveal>
        <h3 class="font-bold">Methoden & Domänen</h3>
        <ul class="mt-3 grid grid-cols-2 gap-2 text-sm text-slate-700">
          <li>Ansys</li><li>CATIA V5</li><li>Simufact</li>
          <li>Qualitätsmanagement</li><li>SAP</li><li>Python</li>
        </ul>
      </div>

      <div class="card p-6 rounded-2xl border bg-white" data-reveal>
        <h3 class="font-bold">Tools & Software</h3>
        <ul class="mt-3 grid grid-cols-2 gap-2 text-sm text-slate-700">
          <li>Power BI</li><li>Excel/Outlook Workflows</li>
          <li>Jira/Confluence</li><li>SolidWorks</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- ========== KONTAKT ========== -->
<section id="kontakt" class="py-24 bg-white border-t">
  <div class="max-w-6xl mx-auto px-4 grid lg:grid-cols-3 gap-10">
    <div class="lg:col-span-2" data-reveal>
      <h2 class="text-3xl font-extrabold">Kontakt</h2>

      <form class="grid gap-4 mt-6" onsubmit="sendMail(event)">
        <input name="name" placeholder="Ihr Name" required class="border rounded-xl px-4 py-3"/>
        <input name="email" type="email" placeholder="Ihre E-Mail" required class="border rounded-xl px-4 py-3"/>
        <textarea name="msg" rows="4" placeholder="Kurze Nachricht" required class="border rounded-xl px-4 py-3"></textarea>
        <button class="btn-primary">Nachricht senden</button>
      </form>
    </div>

    <div class="card p-6 rounded-2xl border bg-white" data-reveal>
      <p><strong>E-Mail:</strong><br><a href="mailto:oussamaguedri@gmail.com">oussamaguedri@gmail.com</a></p>
      <p class="mt-2"><strong>Telefon:</strong><br><a href="tel:+491637254664">+49 163 7254664</a></p>
      <p class="mt-2"><strong>Ort:</strong><br>Hannover, Deutschland</p>
      <p class="mt-2"><strong>Verfügbar:</strong><br>ab sofort</p>
    </div>
  </div>
</section>

<!-- ========== FOOTER ========== -->
<footer class="py-8 text-center text-sm text-slate-600">
  © <span id="year"></span> Oussama Guedri – Alle Rechte vorbehalten.
</footer>

<script>
// Jahr
document.getElementById("year").textContent = new Date().getFullYear();

// Kontakt → Mailto
function sendMail(e){
  e.preventDefault();
  const d = Object.fromEntries(new FormData(e.target));
  window.location = `mailto:oussamaguedri@gmail.com?subject=Kontaktanfrage ${d.name}&body=${d.msg}%0A%0AEmail: ${d.email}`;
}

// Parallax
document.addEventListener("scroll",()=>{
  document.querySelectorAll("[data-parallax]").forEach(el=>{
    el.style.transform = `translateY(${window.scrollY * 0.12}px)`
  });
});

// Reveal on scroll
const io = new IntersectionObserver(e=>e.forEach(x=>x.isIntersecting && x.target.classList.add("reveal-visible")));
document.querySelectorAll("[data-reveal]").forEach(el => io.observe(el));

// Dark Mode
document.getElementById("toggleDark").onclick=()=>document.documentElement.classList.toggle("dark");
</script>

</body>
</html>

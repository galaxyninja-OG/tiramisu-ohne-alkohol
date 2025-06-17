# tiramisu-ohne-alkohol
Tiramisu klingt kompliziert? Ganz im Gegenteil! Dieses Rezept zeigt dir, wie einfach du ein köstliches, alkoholfreies Tiramisu ganz ohne Backofen und Schnickschnack selbst machen kannst. Ideal für Kinder, Gäste oder einfach nur zum Genießen!
<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Ein einfaches und leckeres Tiramisu-Rezept ganz ohne Alkohol – ideal für Kinder und Gäste.">
  <title>Tiramisu ohne Alkohol</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Open+Sans&display=swap');

    body {
      font-family: 'Open Sans', sans-serif;
      background: linear-gradient(to bottom right, #e0f7fa, #ffffff);
      color: #2e3c40;
      margin: 0;
      padding: 0;
    }

    header {
      background: linear-gradient(to right, #4fc3f7, #039be5);
      color: #ffffff;
      padding: 3rem 2rem 2rem;
      text-align: center;
      position: sticky;
      top: 0;
      z-index: 1000;
      box-shadow: 0 4px 12px rgba(0,0,0,0.15);
    }

    header h1 {
      font-family: 'Playfair Display', serif;
      font-size: 3.5rem;
      margin: 0;
      letter-spacing: 1.5px;
      text-shadow: 3px 3px 6px rgba(0,0,0,0.3);
      animation: titleZoom 2s ease;
    }

    header .auth-buttons {
      position: absolute;
      top: 20px;
      left: 20px;
    }

    .auth-buttons input {
      padding: 0.4rem;
      border-radius: 5px;
      border: none;
      margin-right: 0.5rem;
    }

    .auth-buttons button {
      padding: 0.5rem 1rem;
      font-size: 1rem;
      background-color: #ffffff;
      color: #0277bd;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      box-shadow: 0 2px 5px rgba(0,0,0,0.2);
    }

    .auth-buttons button:hover {
      background-color: #e1f5fe;
    }

    @keyframes titleZoom {
      from { transform: scale(0.9); opacity: 0; }
      to { transform: scale(1); opacity: 1; }
    }

    header::after {
      content: "♥";
      font-size: 2.5rem;
      position: absolute;
      right: 20px;
      top: 20px;
      color: #ffffff88;
      animation: float 3s ease-in-out infinite;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }

    main {
      max-width: 850px;
      margin: auto;
      padding: 2rem;
    }

    .intro {
      background-color: #f0f9ff;
      border-left: 6px solid #4fc3f7;
      padding: 1.5rem;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.05);
      margin-bottom: 2rem;
    }

    h2 {
      color: #0277bd;
      font-weight: 600;
    }

    img {
      width: 100%;
      border-radius: 12px;
      margin: 1.5rem 0;
      box-shadow: 0 4px 10px rgba(0,0,0,0.15);
    }

    ul, ol {
      padding-left: 1.5rem;
    }

    li {
      margin-bottom: 0.6rem;
      border-bottom: 1px solid #ccc;
      padding-bottom: 0.3rem;
      transition: background 0.3s;
    }

    li:hover {
      background-color: #e1f5fe;
    }

    .section {
      background-color: rgba(255, 255, 255, 0.95);
      padding: 1.5rem;
      border-radius: 15px;
      border: 1px solid #ccc;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      margin-bottom: 2rem;
    }

    .comment-section {
      margin-top: 3rem;
    }

    .comment-section textarea {
      width: 100%;
      padding: 1rem;
      border-radius: 8px;
      border: 1px solid #ccc;
      resize: vertical;
      margin-bottom: 1rem;
    }

    .comment-section button {
      background-color: #0277bd;
      color: white;
      border: none;
      padding: 0.8rem 1.5rem;
      border-radius: 6px;
      cursor: pointer;
    }

    .comment-section button:hover {
      background-color: #015f8b;
    }

    .comment-list {
      margin-top: 2rem;
    }

    .comment-item {
      padding: 0.8rem;
      background-color: #f9f9f9;
      border-left: 4px solid #0277bd;
      border-radius: 6px;
      margin-bottom: 1rem;
      position: relative;
    }

    .comment-item strong {
      display: block;
      color: #0277bd;
      margin-bottom: 0.2rem;
    }

    .comment-item button {
      position: absolute;
      top: 8px;
      right: 8px;
      background: transparent;
      border: none;
      color: red;
      cursor: pointer;
    }

    p {
      line-height: 1.6;
    }

    footer {
      background-color: #455a64;
      text-align: center;
      padding: 1rem;
      color: #fafafa;
    }
  </style>
  <script>
    document.cookie = "nutzerHinweis=1; path=/; max-age=31536000";

    function anmelden() {
      const nutzer = document.getElementById('nutzerInput').value;
      if (nutzer && nutzer.length >= 2) {
        localStorage.setItem('nutzerName', nutzer);
        alert('Angemeldet als: ' + nutzer);
        document.querySelector('.comment-section button').onclick = kommentarAbsenden;
      } else {
        alert('Bitte einen gültigen Nutzernamen eingeben (mind. 2 Zeichen).');
      }
    }

    function kommentarAbsenden() {
      const kommentarText = document.querySelector('.comment-section textarea').value;
      const nutzer = localStorage.getItem('nutzerName');
      if (!nutzer) {
        alert('Bitte zuerst anmelden.');
        return;
      }
      if (kommentarText.trim()) {
        const kommentarListe = document.getElementById('kommentarListe');
        const neuesElement = document.createElement('div');
        neuesElement.className = 'comment-item';
        neuesElement.innerHTML = `<strong>@${nutzer}</strong><span>${kommentarText}</span><button onclick="this.parentElement.remove()">✖</button>`;
        kommentarListe.prepend(neuesElement);
        document.querySelector('.comment-section textarea').value = '';
      } else {
        alert('Bitte einen Kommentar eingeben.');
      }
    }

    window.onload = () => {
      const nutzer = localStorage.getItem('nutzerName');
      if (nutzer) {
        document.querySelector('.comment-section button').onclick = kommentarAbsenden;
      }
    }
  </script>
</head>
<body>
  <header>
    <div class="auth-buttons">
      <input type="text" id="nutzerInput" placeholder="Nutzername (sichtbar für alle)">
      <button onclick="anmelden()">Anmelden</button>
    </div>
    <h1>Tiramisu ohne Alkohol</h1>
    <p>Ein klassisches italienisches Dessert – ganz ohne Alkohol und perfekt für die ganze Familie!</p>
  </header>

  <main>
    <div class="intro">
      <p><strong>Tiramisu klingt kompliziert?</strong> Ganz im Gegenteil! Dieses Rezept zeigt dir, wie einfach du ein köstliches, alkoholfreies Tiramisu ganz ohne Backofen und Schnickschnack selbst machen kannst. Ideal für Kinder, Gäste oder einfach nur zum Genießen!</p>
    </div>

    <section class="section">
      <h2>Zutaten</h2>
      <ul>
        <li>200 g Löffelbiskuits</li>
        <li>500 g Mascarpone</li>
        <li>250 ml Sahne</li>
        <li>100 g Zucker</li>
        <li>1 Päckchen Vanillezucker</li>
        <li>3 frische Eier</li>
        <li>200 ml starker Kaffee (abgekühlt)</li>
        <li>Kakaopulver zum Bestäuben</li>
      </ul>
    </section>

    <img src="https://cdn.pixabay.com/photo/2020/01/25/19/42/tiramisu-4791464_1280.jpg" alt="Frisches Tiramisu ohne Alkohol in einer Glasschale, mit Kakao bestäubt" loading="lazy">

    <section class="section">
      <h2>Zubereitung</h2>
      <ol>
        <li>Trenne die Eier und schlage das Eiweiß steif.</li>
        <li>Schlage die Sahne steif und stelle sie beiseite.</li>
        <li>Verrühre Eigelb, Zucker und Vanillezucker cremig.</li>
        <li>Rühre die Mascarpone unter die Eigelb-Zucker-Mischung.</li>
        <li>Hebe die geschlagene Sahne und den Eischnee vorsichtig unter die Creme.</li>
        <li>Tauche die Löffelbiskuits kurz in den kalten Kaffee und lege den Boden einer Form damit aus.</li>
        <li>Verteile die Hälfte der Creme auf den Biskuits.</li>
        <li>Wiederhole den Vorgang mit einer weiteren Schicht getränkter Biskuits und der restlichen Creme.</li>
        <li>Bestäube das Tiramisu großzügig mit Kakaopulver.</li>
        <li>Stelle das Tiramisu mindestens 4 Stunden (besser über Nacht) kalt.</li>
      </ol>
    </section>

    <section class="section">
      <h2>Serviervorschlag</h2>
      <p>Das Tiramisu lässt sich wunderbar mit frischen Beeren oder etwas Minze garnieren. Ideal für Kindergeburtstage oder als festliches Dessert!</p>
    </section>

    <section class="section comment-section">
      <h2>Kommentare</h2>
      <p><em>Nur angemeldete Benutzer dürfen kommentieren. Der Nutzername ist öffentlich sichtbar.</em></p>
      <textarea placeholder="Dein Kommentar..."></textarea>
      <button>Kommentar absenden</button>
      <div id="kommentarListe" class="comment-list"></div>
    </section>
  </main>

  <footer>
    © 2025 Tiramisu Rezept – alkoholfrei & köstlich
  </footer>
</body>
</html>

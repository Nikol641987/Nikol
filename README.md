<!DOCTYPE html>
<html lang="sk">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Slovenské meniny dnes</title>
<style>
  body {
    font-family: Arial, sans-serif;
    text-align: center;
    padding: 20px;
    margin: 0;
    background: #f9f9f9;
    color: #333;
  }
  .container {
    background: white;
    border-radius: 8px;
    padding: 15px 30px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    display: inline-block;
  }
  h1 {
    margin: 0 0 10px;
    font-size: 1.8em;
  }
  .date {
    font-weight: bold;
    margin-bottom: 10px;
  }
  .names {
    font-size: 1.4em;
    color: #0078d7;
  }
</style>
</head>
<body>
<div class="container">
  <h1>Meniny dnes</h1>
  <div class="date" id="date"></div>
  <div class="names" id="names"></div>
</div>

<script>
  // Slovenský kalendár menín: mesiac-den : mená
  const meniny = {
    "1-1": "Nový rok",
    "1-2": "Alexandra",
    "1-3": "Daniela",
    "1-4": "Drahomíra",
    "1-5": "Dalimil",
    // (Pridaj ďalšie dni a mená podľa potreby)
    "5-30": "Félix, Ferdinand",  // 30.5. pre príklad
    "5-31": "Petronela",
    "6-1": "Laura",
    "6-2": "Jarmila"
    // ... môžeme doplniť celý kalendár, alebo aj len pár dní pre demo
  };

  function formatDate(d) {
    return d.toLocaleDateString('sk-SK', { day: 'numeric', month: 'numeric', year: 'numeric' });
  }

  const today = new Date();
  const key = (today.getMonth() + 1) + "-" + today.getDate();
  const names = meniny[key] || "Meniny dnes nie sú";

  document.getElementById('date').textContent = formatDate(today);
  document.getElementById('names').textContent = names;
</script>
</body>
</html>

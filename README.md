<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HMC MAKER PRO — ECD SARL</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root { --bg: #0f0f14; --side: #16161d; --gold: #d4a84b; --costume: #2e86de; --makeup: #ff4757; --hair: #ff9f43; }
        body { background: var(--bg); color: #fff; font-family: 'Montserrat', sans-serif; display: flex; height: 100vh; margin: 0; }
        
        /* Menu Latéral */
        nav { width: 260px; background: var(--side); border-right: 1px solid #222; padding: 20px; display: flex; flex-direction: column; }
        .nav-item { padding: 12px; margin: 5px 0; cursor: pointer; border-radius: 4px; font-size: 13px; border-left: 3px solid transparent; }
        .nav-item:hover { background: #252535; }
        .active-c { border-left-color: var(--costume); background: #1a1a2b; }
        .active-m { border-left-color: var(--makeup); background: #2b1a1a; }
        .active-h { border-left-color: var(--hair); background: #2b231a; }

        /* Zone de Travail */
        main { flex: 1; overflow-y: auto; padding: 30px; }
        .section-panel { display: none; }
        .active-panel { display: block; }
        .card { background: #1c1c24; padding: 20px; border-radius: 8px; margin-bottom: 20px; border: 1px solid #2a2a35; }
        
        /* Outils Visuels */
        .moodboard-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 15px; margin-top: 20px; }
        .drop-zone { height: 150px; border: 2px dashed #444; display: flex; align-items: center; justify-content: center; background: #111; }
    </style>
</head>
<body>

<nav>
    <h2 style="color:var(--gold); font-size:18px; margin-bottom:30px;">HMC MAKER</h2>
    <div class="nav-item active-c" onclick="switchTab('costume')">👕 DÉPT. COSTUME</div>
    <div class="nav-item" onclick="switchTab('makeup')">💄 DÉPT. MAQUILLAGE</div>
    <div class="nav-item" onclick="switchTab('hair')">💇 DÉPT. COIFFURE</div>
    <hr style="border:0; border-top:1px solid #333; margin:20px 0;">
    <div class="nav-item" onclick="switchTab('moodboard')">🖼️ MOODBOARD / FICHES</div>
    <div class="nav-item" onclick="switchTab('devis')">💰 DEVIS & EXPORT</div>
</nav>

<main>
    <div id="panel-costume" class="section-panel active-panel">
        <h1>Gestion Costume</h1>
        <div class="card">
            <h3>Dépouillement Textile</h3>
            <textarea placeholder="Liste des costumes par scène..." style="width:100%; height:100px; background:#000; color:#fff; border:1px solid #444; padding:10px;"></textarea>
        </div>
    </div>

    <div id="panel-moodboard" class="section-panel">
        <h1>Générateur de Propositions Visuelles</h1>
        <div class="card">
            <input type="text" placeholder="Nom du Personnage" style="padding:10px; width:300px;">
            <div class="moodboard-grid">
                <div><label>Réf. Costume</label><div class="drop-zone">IMAGE</div></div>
                <div><label>Réf. Maquillage</label><div class="drop-zone">IMAGE</div></div>
                <div><label>Réf. Coiffure</label><div class="drop-zone">IMAGE</div></div>
            </div>
            <button style="margin-top:20px; padding:10px 20px; background:var(--gold); border:none; cursor:pointer;">GÉNÉRER FICHE PDF</button>
        </div>
    </div>

    </main>

<script>
    function switchTab(tabId) {
        document.querySelectorAll('.section-panel').forEach(p => p.classList.remove('active-panel'));
        document.getElementById('panel-' + tabId).classList.add('active-panel');
        
        document.querySelectorAll('.nav-item').forEach(i => {
            i.classList.remove('active-c', 'active-m', 'active-h');
        });
        // Logique simplifiée pour l'exemple
    }
</script>
</body>
</html>

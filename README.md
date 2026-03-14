<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MANSION EDITS | VISUAL ARCHITECT</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Montserrat:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg: #050505; 
            --neon-purple: #bc13fe;
            --light-glow: rgba(188, 19, 254, 0.2); 
            --text-main: #ffffff;
            --font-mansion: 'Playfair Display', serif; /* Classic serif font for Mansion Edits */
            --font-sub: 'Montserrat', sans-serif; /* Modern sans-serif font for other text */
        }

        * { box-sizing: border-box; }
        body {
            margin: 0;
            font-family: var(--font-sub); /* Default sans-serif font */
            background-color: var(--bg);
            color: var(--text-main);
            overflow-x: hidden;
        }

        /* Ambient Background Glow */
        body::before {
            content: "";
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle at 50% 50%, #1a0033 0%, #050505 100%);
            z-index: -1;
        }

        /* DRIVE LINK HIGHLIGHT (Top Corner) */
        .drive-link {
            position: absolute;
            top: 30px;
            right: 30px;
            background: rgba(188, 19, 254, 0.1);
            border: 1px solid var(--neon-purple);
            padding: 12px 25px;
            border-radius: 50px;
            color: white;
            text-decoration: none;
            font-family: var(--font-sub);
            font-size: 0.75rem;
            box-shadow: 0 0 10px var(--light-glow);
            transition: 0.4s;
            z-index: 1001;
        }
        .drive-link:hover { background: var(--neon-purple); box-shadow: 0 0 25px var(--neon-purple); }

        /* HEADER SECTION */
        header {
            height: 80vh; 
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
        }

        header h1 {
            font-family: var(--font-mansion); /* Classic serif font */
            font-size: clamp(3rem, 7vw, 5rem);
            margin: 0;
            color: white;
            text-transform: uppercase;
            filter: drop-shadow(0 0 10px var(--neon-purple));
        }

        header p { 
            font-family: var(--font-sub);
            font-size: 1.2rem;
            color: var(--neon-purple);
            letter-spacing: 2px;
            margin-top: 15px;
            text-transform: uppercase;
        }

        /* DM FOR EDITS BUTTON - UPDATED & IMPROVED */
        .dm-btn {
            margin-top: 40px;
            padding: 18px 50px;
            background: linear-gradient(to right, #bc13fe, #7000ff); /* Purple gradient */
            color: white;
            font-family: var(--font-sub);
            text-decoration: none;
            border-radius: 50px; /* Fully rounded button */
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: 0.5s;
            box-shadow: 0 5px 20px rgba(188, 19, 254, 0.4);
        }
        .dm-btn:hover { background: linear-gradient(to right, #7000ff, #bc13fe); box-shadow: 0 8px 30px rgba(188, 19, 254, 0.6); transform: translateY(-5px); }

        .container { padding: 60px 10%; }

        h2 {
            font-family: var(--font-sub);
            font-size: 1.6rem;
            margin-bottom: 60px;
            border-left: 6px solid var(--neon-purple);
            padding-left: 25px;
            letter-spacing: 4px;
        }

        /* 01 // EDITING SECTION (With animations) */
        .editing-grid { display: flex; flex-direction: column; gap: 100px; }
        .project-row { display: flex; align-items: center; gap: 50px; }
        .project-row:nth-child(even) { flex-direction: row-reverse; }

        .video-wrapper {
            flex: 1;
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid rgba(188, 19, 254, 0.3);
            transition: 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }
        .video-wrapper:hover { transform: scale(1.03); border-color: var(--neon-purple); box-shadow: 0 0 40px var(--light-glow); }
        .video-wrapper img { width: 100%; display: block; }

        .meta-side { width: 160px; text-align: center; font-family: var(--font-sub); }
        .serial { font-size: 4.5rem; font-weight: 900; opacity: 0.1; color: var(--neon-purple); }
        
        .animation-zone { height: 70px; margin: 15px 0; background: rgba(188, 19, 254, 0.03); border-radius: 12px; position: relative; overflow: hidden; }
        .ani-1::after { content: "⚡"; position: absolute; font-size: 35px; animation: bounce 1s infinite; left: 35%; top: 15%; }
        .ani-2::after { content: "🌀"; position: absolute; font-size: 35px; animation: spin 2.5s infinite; left: 35%; top: 15%; }
        .ani-3::after { content: "🔥"; position: absolute; font-size: 35px; animation: flicker 0.6s infinite; left: 35%; top: 15%; }
        .ani-4::after { content: "✨"; position: absolute; font-size: 35px; animation: pulse 1.2s infinite; left: 35%; top: 15%; }

        /* 02 // THUMBNAIL GALLERY */
        .thumb-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 25px;
            margin-top: 50px;
        }
        .thumb-card { border-radius: 18px; overflow: hidden; border: 1px solid #222; transition: 0.4s; }
        .thumb-card:hover { transform: translateY(-12px); border-color: var(--neon-purple); box-shadow: 0 10px 30px var(--light-glow); }
        .thumb-card img { width: 100%; height: 100%; object-fit: cover; }

        /* SOCIAL / FOOTER */
        .contact-footer { text-align: center; padding: 120px 0; background: linear-gradient(to top, #0d001f, transparent); }
        .social-row { display: flex; justify-content: center; gap: 25px; flex-wrap: wrap; }
        .social-box {
            text-decoration: none; color: white; padding: 15px 35px;
            border: 1px solid rgba(255,255,255,0.08); border-radius: 60px;
            font-family: var(--font-sub); font-size: 0.8rem; transition: 0.4s;
            background: rgba(255,255,255,0.01); display: flex; align-items: center; gap: 12px;
        }
        .social-box:hover { background: var(--neon-purple); border-color: var(--neon-purple); box-shadow: 0 0 25px var(--neon-purple); transform: scale(1.05); }

        /* Keyframes */
        @keyframes bounce { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-20px); } }
        @keyframes spin { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
        @keyframes flicker { 0%, 100% { opacity: 0.5; } 50% { opacity: 1; } }
        @keyframes pulse { 0% { transform: scale(0.9); opacity: 0.5; } 100% { transform: scale(1.3); opacity: 0; } }

        @media (max-width: 768px) {
            .project-row, .project-row:nth-child(even) { flex-direction: column; text-align: center; }
            .meta-side { width: 100%; }
        }
    </style>
</head>
<body>

    <a href="https://drive.google.com/drive/folders/1uZUfMlsbqeC8xt79_IdqsWwaXF1Ea9ex?usp=drive_link" target="_blank" class="drive-link">
        <i class="fas fa-folder-open"></i> ABOUT ME / ASSETS
    </a>

    <header>
        <h1>MANSION EDITS</h1>
        <p>Turning Frames Into Masterpieces</p> 
        <a href="https://instagram.com/mansion.edits" class="dm-btn" target="_blank">DM FOR EDITS</a> </header>

    <div class="container">
        <section>
            <h2>01 // EDITING PROJECTS</h2>
            <div class="editing-grid">
                
                <div class="project-row">
                    <div class="meta-side"><div class="serial">01</div><div class="animation-zone ani-1"></div></div>
                    <div class="video-wrapper"><a href="https://youtu.be/ChK9hKMTEW0" target="_blank"><img src="https://img.youtube.com/vi/ChK9hKMTEW0/maxresdefault.jpg"></a></div>
                </div>

                <div class="project-row">
                    <div class="meta-side"><div class="serial">02</div><div class="animation-zone ani-2"></div></div>
                    <div class="video-wrapper"><a href="https://youtu.be/jxEi23vVKo8" target="_blank"><img src="https://img.youtube.com/vi/jxEi23vVKo8/maxresdefault.jpg"></a></div>
                </div>

                <div class="project-row">
                    <div class="meta-side"><div class="serial">03</div><div class="animation-zone ani-3"></div></div>
                    <div class="video-wrapper"><a href="https://youtu.be/Dm6mS-R_DHU" target="_blank"><img src="https://img.youtube.com/vi/Dm6mS-R_DHU/maxresdefault.jpg"></a></div>
                </div>

                <div class="project-row">
                    <div class="meta-side"><div class="serial">04</div><div class="animation-zone ani-4"></div></div>
                    <div class="video-wrapper"><a href="https://youtu.be/feVFs8OMfmg" target="_blank"><img src="https://img.youtube.com/vi/feVFs8OMfmg/maxresdefault.jpg"></a></div>
                </div>

            </div>
        </section>

        <section style="margin-top: 150px;">
            <h2>02 // STATIC DESIGNS</h2>
            <div class="thumb-grid">
                <div class="thumb-card"><img src="999+ FPS Thumbnail.jpg"></div>
                <div class="thumb-card"><img src="Senpai Thumb.jpg"></div>
                <div class="thumb-card"><img src="SenpaiSpider Thumb.jpg"></div>
            </div>
        </section>
    </div>

    <div class="contact-footer">
        <div class="social-row">
            <a href="https://instagram.com/mansion.edits" class="social-box" target="_blank"><i class="fab fa-instagram"></i> INSTAGRAM</a>
            <a href="https://discord.gg/rbdWAn94Ec" class="social-box" target="_blank"><i class="fab fa-discord"></i> DISCORD</a>
            <a href="https://x.com/tejasflow_" class="social-box" target="_blank"><i class="fab fa-twitter"></i> X / TWITTER</a>
            <a href="mailto:tejasraj172@email.com" class="social-box"><i class="fas fa-envelope"></i> MAIL</a>
        </div>
    </div>

    <footer style="padding: 40px; text-align: center; font-family: var(--font-sub); font-size: 0.6rem; opacity: 0.3; letter-spacing: 2px;">
        MANSION EDITS // VISUAL ARCHITECT // 2024
    </footer>

</body>
</html>

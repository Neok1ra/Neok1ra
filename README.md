<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="Content-Security-Policy">
    <title>🐇 Light 🐇</title>
    <meta itemprop="name" content="Light~ - About me">
    <meta itemprop="description" content="about me ~~">
    <meta itemprop="image" content="./js/placeholder.png">
    <meta property="og:url" content="https://your-site.netlify.app">
    <meta property="og:type" content="website">
    <meta property="og:title" content="Light~ - About me">
    <meta property="og:description" content="about me ~~">
    <meta name="description" content="Welcome to Light's personal space!">
    <meta property="og:image" content="./js/placeholder.png">
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Light~ - About me">
    <meta name="twitter:description" content="about me ~~">
    <meta name="twitter:image" content="./js/placeholder.png">
    <meta name="twitter:site" content="@yourtwitter">
    <link rel="shortcut icon" id="favicon" href="./js/placeholder.png">
    <meta name="viewport" content="width=device-width, height=device-height, initial-scale=1.0, minimum-scale=1.0">
    <style>
        html, body {
            height: 100%;
            margin: 0;
            padding: 0;
            overflow-x: hidden;
        }
        body {
            min-height: 100vh;
            overflow-y: auto;
            position: relative;
            scroll-behavior: smooth;
            font-family: 'Segoe UI', sans-serif;
            font-weight: 400;
            font-style: normal;
            color: rgb(240, 230, 230);
            background: #000; /* Fallback if image fails */
        }
        * {
            text-wrap: initial;
        }
        h2 {
            font-weight: 700;
        }
        p {
            font-size: clamp(0.9em, 1vw, 1.3em);
        }
        a {
            font-weight: 600;
            text-underline-offset: 2px;
            color: #ff69b4;
        }
        a:hover {
            text-decoration: underline;
        }
        #wallpaper {
            background-size: cover;
            background-position: center;
            filter: brightness(30%);
            position: fixed;
            top: 0;
            right: 0;
            bottom: 0;
            left: 0;
            z-index: -1;
        }
        #background-video {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            min-height: 100%;
            object-fit: cover;
            z-index: -1;
            opacity: 1;
            transition: opacity 0.5s ease-in-out;
            pointer-events: none;
        }
        .box-body {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            margin: auto;
            width: 90%;
            max-width: 48rem;
        }
        .marginalized {
            width: 100%;
        }
        #smallbox {
            margin: 10px 0;
        }
        #spacer {
            height: 20px;
        }
        #head-hr {
            font-size: 1.2em;
            margin: 10px 0;
        }
        hr {
            border: none;
            height: 1px;
            background: #ccc;
            margin: 20px 0;
        }
        .time, .birthday {
            font-weight: bold;
            color: #ff69b4;
        }
        .tooltiptext {
            font-size: 0.9em;
            color: #fff;
        }
        #nothing-message {
            font-style: italic;
        }
        #discord-box {
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 10px 0;
        }
        #discord-profilepic, #gameimg {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            margin-right: 10px;
        }
        #flex-styled {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }
        .playlist-songs {
            font-size: 0.9em;
            text-align: left;
            margin-top: 10px;
        }
        .playlist-songs p {
            margin: 5px 0;
        }
        .gifs img {
            margin: 10px;
        }
        .badges img {
            margin: 5px;
        }
    </style>
</head>
<body>
    <div id="wallpaper">
        <div id="background-video">
            <img id="video-source" src="/wallpaper.jpg" alt="Background Image">
        </div>
    </div>
    <div class="box-body">
        <p id="head-hr">・———— ・ ✦ Light Selene ✦ ・———— ・</p>
        <hr>
        <div id="spacer"></div>
        <div class="marginalized">
            <div id="smallbox">
                <p id="question">Current Local Time</p>
                <span id="modal" class="time">
                    <script>
                        function clock() {
                            let current = new Date();
                            let hours = current.getHours();
                            let minutes = current.getMinutes();
                            let seconds = current.getSeconds();
                            let date = `${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
                            document.querySelector('.time').innerHTML = `${date}`;
                        }
                        clock();
                        setInterval(clock, 1000);
                    </script>
                    <span class="tooltiptext">+1 CEST</span>
                </span>
            </div>
            <div id="smallbox">
                <div style="display: flex; align-items: center; justify-content: center;">
                    <img id="discord-decoration">
                    <img id="discord-profilepic" src="/placeholder.png" alt="Discord Profile">
                </div>
                <p id="question">
                    <span id="discord-tag">Hey, thats me ૮ ˶ᵔ ᵕ ᵔ˶ ა</span>
                </p>
            </div>
            <div id="smallbox">
                <p id="question">Birthday</p>
                <span id="modal" class="birthday">
                    <script>
                        let start = new Date('2007-08-23');
                        let now = new Date();
                        let defaultText = true;
                        let birthday = document.querySelector('.birthday');
                        let originalText = (birthday.innerHTML = `${Math.ceil((now.getTime() - start.getTime()) / (1000 * 60 * 60 * 24))} Days ago`);
                        birthday.addEventListener('click', function () {
                            if (!defaultText) {
                                birthday.innerHTML = originalText;
                                defaultText = !defaultText;
                            } else {
                                birthday.innerHTML = `~ ${now.getFullYear() - start.getFullYear()} Years ago`;
                                defaultText = !defaultText;
                            }
                        });
                    </script>
                    <span class="tooltiptext">23rd August 2007</span>
                </span>
            </div>
        </div>
        <div id="spacer"></div>
        <div id="nothing-message">
            <p>Currently doing nothing...</p>
        </div>
        <div id="discord-box" class="gamestatus">
            <img id="gameimg" alt="game" src="/placeholder.png">
            <div id="textbox">
                <p id="playing"></p>
                <p id="playing2"></p>
                <p id="playing3"></p>
            </div>
        </div>
        <div id="spacer"></div>
        <div id="alignment-left">
            <p>My Name is Light, i'm a guy from Germany. I went to the <a href="https://www.hs-mannheim.de/">Hochschule Mannheim</a> for a whole 3 Semesters of Computer Science. I quit in 2024 and now do vocational training for servers and network stuff. My Linux journey started in 2016 while i started Docker in 2022.</p>
            <p>Additionally I write <a href="https://archiveofourown.org/users/yourusername">Yuri webnovels</a> and read books in my free time. I'm midly obssessed with Vector from Girls Frontline and Symboli Rudolf from Umamusume. I love everything with stars and planets and space in general.</p>
            <p>If you want to know what i play you can find <a href="[Your Steam URL, e.g., https://steamcommunity.com/id/yourname]">Steam profile</a> or my <a href="https://koito.egirl.ing/">entire music history</a> on these sites as well as under here in the discord status.</p>
        </div>
        <div id="spacer"></div>
        <p style="display: none !important;" id="usercount">0 User's connected</p>
        <div id="spacer"></div>
        <p id="head-hr">✦•┈๑⋅⋯ My playlists ⋯⋅๑┈·✦</p>
        <div id="flex-styled">
            <iframe data-testid="embed-iframe" style="border-radius: 12px" src="https://open.spotify.com/embed/playlist/39fdnhHDN9tdXxPILJUyPN?utm_source=generator&theme=0" width="80%" height="352" frameborder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
            <div class="playlist-songs">
                <p><strong>Manipulate Playlist</strong></p>
                <p>Like A Drug - Jordyne, SWIM</p>
                <p>Manipulate - mxze, Clarei</p>
                <p>Bleed - Connor Kauffman</p>
                <p>Ride for Me - Daniel Di Angelo</p>
                <p>Talk Dirty - Daniel Di Angelo</p>
                <p>Outta my head - Omido, Rick Jansen, Ordell</p>
                <p>Advantage - Daniel Di Angelo</p>
                <p>PLEASE - Omido, Ex Habit</p>
                <p>Bad for Me - Always Never</p>
                <p>Secrets - Omido, Ordell, Rick Jansen</p>
                <p>BAD IDEA - Chris Grey</p>
                <p>ONE MORE NIGHT - Chris Grey</p>
                <p>Right Ways - Nick Alexandr</p>
                <p>In Private - Daniel Di Angelo</p>
                <p>DANGEROUS GAME - Chris Grey</p>
                <p>Fumes - Oscen</p>
                <p>Death of Me - WizTheMc</p>
                <p>stalker - Stevie Howie</p>
                <p>Therapy - VOILÀ</p>
                <p>COLOR ME BLUE - GRANT KNOCHE</p>
                <p>Searing - Imaginary Ambition</p>
                <p>Try Me - The Weeknd</p>
                <p>First - SoMo</p>
                <p>DEVIL IN DISGUISE - EIGHTYEIGHTWAV</p>
                <p>Temptations - Daniel Di Angelo</p>
                <p>The Room - Jaymie Deville</p>
            </div>
            <iframe data-testid="embed-iframe" style="border-radius: 12px" src="https://open.spotify.com/embed/playlist/6LlQcsrU0WjWvhfT9UqJwT?utm_source=generator&theme=0" width="80%" height="352" frameborder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
        </div>
        <!-- GIFs from Previous Requests -->
        <div class="gifs">
            <img src="https://media.giphy.com/media/IXnygGeB6LPPi/giphy.gif" alt="Cyber Vibe" width="200">
            <img src="https://media.giphy.com/media/RDZo7znAdn2u7sAcWH/giphy.gif" alt="Hacking Mode" width="200">
        </div>
        <!-- Cybersecurity Badges -->
        <div class="badges">
            <img src="https://img.shields.io/badge/-Python-3776AB?logo=python" alt="Python">
            <img src="https://img.shields.io/badge/-Nmap-4682B4" alt="Nmap">
            <img src="https://img.shields.io/badge/-Wireshark-1679A7" alt="Wireshark">
            <img src="https://img.shields.io/badge/-Metasploit-FF0000" alt="Metasploit">
            <img src="https://img.shields.io/badge/-Burp_Suite-FF5733" alt="Burp Suite">
            <img src="https://img.shields.io/badge/-Kali_Linux-557C94" alt="Kali Linux">
            <img src="https://img.shields.io/badge/-John_the_Ripper-FF4500" alt="John the Ripper">
        </div>
    </div>
    <div id="spacer"></div>
    <script defer src="https://static.cloudflareinsights.com/beacon.min.js/vcd15cbe7772f49c399c6a5babf22c1241717689176015" integrity="sha512-ZpsOmlRQV6y907TI0dKBHq9Md29nnaEIPlkf84rnaERnq6zvWvPUqr2ft8M1aS28oN72PdrCzSjY4U6VaAw1EQ==" data-cf-beacon='{"version":"2024.11.0","token":"2c53d9595dc043bc8e74d48867569eae","r":1,"server_timing":{"name":{"cfCacheStatus":true,"cfEdge":true,"cfExtPri":true,"cfL4":true,"cfOrigin":true,"cfSpeedBrain":true},"location_startswith":null}}' crossorigin="anonymous"></script>
    <script>
        // Discord status placeholder (replace with Lanyard for dynamic status)
        document.getElementById('discord-profilepic').src = 'https://lanyard-profile-readme.vercel.app/api/YOUR_DISCORD_ID?theme=dark';
    </script>
</body>
</html>

# index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>System Diagnostic</title>
    <style>
        body {
            background-color: #0d1117;
            color: #00ff66;
            font-family: 'Courier New', Courier, monospace;
            padding: 20px;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 90vh;
        }
        #terminal {
            width: 100%;
            max-width: 500px;
            background: #000;
            padding: 20px;
            border-radius: 8px;
            border: 1px solid #00ff66;
            box-shadow: 0 0 15px rgba(0, 255, 102, 0.2);
            box-sizing: border-box;
        }
        .line { 
            margin-bottom: 10px; 
            line-height: 1.4;
        }
        .reveal {
            color: #ff4d4d;
            font-weight: bold;
            border-top: 1px dashed #444;
            padding-top: 15px;
            margin-top: 20px;
            text-align: center;
        }
    </style>
</head>
<body>

<div id="terminal"></div>

<script>
    const target = "Benito";
    const logs = [
        `[+] Initializing connection to ${target}'s device...`,
        `[+] Bypassing firewall and security protocols...`,
        `[+] Extracting photos, messages, and saved passwords...`,
        `[!] Downloading private data: 25%`,
        `[!] Downloading private data: 70%`,
        `[!] Downloading private data: 100%`,
        `[!] ACCESS COMPLETE: Device fully compromised.`,
        `REVEAL`
    ];

    const terminal = document.getElementById('terminal');

    async function runHack() {
        for (let i = 0; i < logs.length; i++) {
            if (logs[i] === 'REVEAL') {
                await new Promise(r => setTimeout(r, 1500));
                const revealDiv = document.createElement('div');
                revealDiv.className = 'line reveal';
                revealDiv.innerHTML = `===================================<br>` +
                                     `Just kidding! Your phone isn't hacked...<br><br>` +
                                     `I just wanted to hack your heart. ❤️<br>` +
                                     `===================================`;
                terminal.appendChild(revealDiv);
            } else {
                const div = document.createElement('div');
                div.className = 'line';
                div.textContent = logs[i];
                terminal.appendChild(div);
                await new Promise(r => setTimeout(r, 1200));
            }
        }
    }

    runHack();
</script>
</body>
</html>

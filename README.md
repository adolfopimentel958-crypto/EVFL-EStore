<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>EPFCL E-Store</title>
<style>
    body {
        background: #111;
        color: white;
        text-align: center;
        font-family: Arial;
        overflow: hidden;
    }

    .circle {
        position: absolute;
        width: 40px;
        height: 40px;
        border-radius: 50%;
        background: rgba(255,255,255,0.2);
        animation: move 6s infinite linear;
    }

    @keyframes move {
        0% { transform: translateY(0); }
        100% { transform: translateY(100vh); }
    }

    #welcome {
        font-size: 30px;
        margin-top: 40vh;
    }

    #skip {
        margin-top: 20px;
        background: white;
        color: black;
        padding: 10px 20px;
        border-radius: 10px;
    }

    #nameScreen {
        display: none;
        margin-top: 40vh;
        font-size: 28px;
        animation: explode 1.5s ease-out forwards;
    }

    @keyframes explode {
        0% { letter-spacing: 1px; opacity: 0; }
        100% { letter-spacing: 8px; opacity: 1; }
    }
</style>
</head>
<body>

<div id="welcome">BIENVENIDOS</div>
<div id="skip">TOCAR PARA OMITIR</div>

<div id="nameScreen">EPFCL E-Store</div>

<script>
    // círculos flotantes
    for (let i=0; i<20; i++) {
        let c = document.createElement("div");
        c.className = "circle";
        c.style.left = Math.random()*100 + "vw";
        c.style.animationDuration = (4 + Math.random()*4) + "s";
        document.body.appendChild(c);
    }

    // saltar animación
    document.getElementById("skip").onclick = () => {
        document.getElementById("welcome").style.display = "none";
        document.getElementById("skip").style.display = "none";
        document.getElementById("nameScreen").style.display = "block";
    };
</script>

</body>
</html>

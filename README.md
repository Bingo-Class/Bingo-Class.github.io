<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">

<style>
html, body {
  margin:0;
  padding:0;
  height:100%;
  overflow:hidden;
  background:black;
}

iframe{
  position:fixed;
  inset:0;
  width:100vw;
  height:100vh;
  border:0;
  display:block;
}
</style>
</head>

<body>

<iframe
  id="digicardFrame"
  allow="camera; microphone; fullscreen"
  allowfullscreen
></iframe>

<script>
const HOME = "https://bingo-class.lovable.app/?embed=true";

const frame = document.getElementById("digicardFrame");

// restore last page (same tab only)
frame.src = sessionStorage.getItem("digicardPage") || HOME;

// store iframe source every second
setInterval(() => {
  sessionStorage.setItem("digicardPage", frame.src);
}, 1000);
</script>

</body>
</html>

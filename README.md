<details markdown="1">
<summary>PRIMER STORYBOARD</summary>

<div style="text-align: center;">
<img class="zoom" src="https://raw.githubusercontent.com/kminugami/Multimedial/refs/heads/main/img/StoryBoard.jpg" style="width: 400px; max-width: 100%; border-radius: 12px; margin: 10px 0;">
</div>

</details>

<img id="mi-cursor" src="https://raw.githubusercontent.com/kminugami/Multimedial/refs/heads/main/img/cursor.gif" style="position: fixed; top: 0; left: 0; width: 32px; pointer-events: none; z-index: 9999; display: none;">

<script>
var cursor = document.getElementById("mi-cursor");
var escondido = false;
document.addEventListener("mousemove", function(e) {
  if (!escondido) {
    var estilo = document.createElement("style");
    estilo.innerHTML = "* { cursor: none !important; }";
    document.head.appendChild(estilo);
    cursor.style.display = "block";
    escondido = true;
  }
  cursor.style.left = e.clientX + "px";
  cursor.style.top = e.clientY + "px";
});
</script>

<div id="zoom-fondo"><img id="zoom-img" src=""></div>

<script>
var fondo = document.getElementById("zoom-fondo");
var fotoGrande = document.getElementById("zoom-img");
document.querySelectorAll("img.zoom").forEach(function(img) {
  img.addEventListener("click", function() {
    fotoGrande.src = img.src;
    fondo.style.display = "flex";
  });
});
fondo.addEventListener("click", function() { fondo.style.display = "none"; });
document.addEventListener("keydown", function(e) { if (e.key === "Escape") fondo.style.display = "none"; });
</script>

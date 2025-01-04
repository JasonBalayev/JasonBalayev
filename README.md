<!-- 
  "Out of This World" Aesthetic Snippet
  -------------------------------------
  1) Includes a starfield background.
  2) Dark blue wave header + footer via Capsule Render.
  3) Rotating planet GIF in the middle (CSS keyframes).
  4) Minimal/no content—purely aesthetic.
-->

<style>
/* Keyframes for spinning the planet gif */
@keyframes spin {
  0%   { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
</style>

<!-- Outer container with starfield background -->
<div style="
  position: relative;
  max-width: 900px;
  margin: 0 auto;
  background: #000 
    url('https://media.giphy.com/media/RKH2yLePqR5T0F3rxg/giphy.gif') 
    no-repeat center center;
  background-size: cover;
  overflow: hidden;
  border-radius: 15px;
  box-shadow: 0 0 20px #0d6efd;
">

  <!-- Wave Header -->
  <div style="text-align: center;">
    <img
      src="https://capsule-render.vercel.app/api?type=wave&color=0:000000,100:0d6efd&height=140&section=header&animation=fadeIn"
      alt="wave header"
      style="width: 100%; filter: drop-shadow(0 0 10px #0d6efd);"
    />
  </div>

  <!-- Rotating Planet/Galaxy GIF -->
  <div style="text-align: center; margin: 20px 0;">
    <img
      src="https://media.giphy.com/media/XoWQ3hR7PmPE4ryPKW/giphy.gif"
      alt="rotating planet"
      style="
        width: 250px;
        height: 250px;
        border-radius: 50%;
        animation: spin 20s linear infinite;
        filter: drop-shadow(0 0 15px #0d6efd);
      "
    />
  </div>

  <!-- Wave Footer -->
  <div style="text-align: center;">
    <img
      src="https://capsule-render.vercel.app/api?type=wave&height=100&section=footer&animation=fadeIn&color=0:000000,100:0d6efd"
      alt="wave footer"
      style="width: 100%; filter: drop-shadow(0 0 10px #0d6efd);"
    />
  </div>
</div>

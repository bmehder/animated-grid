<script>
  export let name = ''
  export let color = ''
</script>

<div class="item">
  <p>{name}</p>
  <p class="color">{color}</p>
</div>

<style>
  .item {
    background-color: #eee;
    text-align: center;
    display: grid;
    align-content: center;
    container: item / size;
    transition: scale 0.2s;
    background-position: center;
    background-size: cover;
    overflow: hidden;
  }

  .item p {
    font-size: 15cqmin;
    color: black;
    font-weight: 900;
    margin: 0;
    padding: 5px;
    position: relative;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: white;
  }

  .item p:before {
    content: '';
    display: block;
    background: var(--purp);
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: -1;
    mix-blend-mode: color;
  }

  .item p.color {
    font-size: 5cqw;
    text-transform: uppercase;
    letter-spacing: 0.2cqmin;
  }

  .item:where(:hover, :focus) {
    color: white;
    scale: 1.1;
    z-index: 2;
    border-radius: 20px;
    box-shadow: 0 0 50px 20px rgba(0, 0, 0, 0.5);
    align-content: space-between;
  }

  :global(.grid:has(.item:hover) .item:not(:hover)) {
    mix-blend-mode: luminosity;
  }

  .item:nth-child(1) {
    background-image: url(/shoes/vapormax-plus-black.jpg);
    transform-origin: top left;
  }
  .item:nth-child(2) {
    background-image: url(/shoes/vapirmax-ashphalt.jpg);
    transform-origin: top center;
  }
  .item:nth-child(3) {
    background-image: url(/shoes/vaporma-plus-grape.jpg);
    transform-origin: top right;
  }
  .item:nth-child(4) {
    background-image: url(/shoes/airmax-leopard.webp);
    transform-origin: left center;
  }
  .item:nth-child(5) {
    background-image: url(/shoes/airmax-wheat-gold.jpg);
    transform-origin: center center;
  }
  .item:nth-child(6) {
    background-image: url(/shoes/flyknit-zebra.jpg);
    transform-origin: right center;
  }
  .item:nth-child(7) {
    background-image: url(/shoes/Nike-Air-Max-270-React-Camo-Black-On-Foot-Side_w900.jpg);
    transform-origin: bottom left;
  }
  .item:nth-child(8) {
    background-image: url(/shoes/270-black-gold.png);
    transform-origin: bottom center;
  }
  .item:nth-child(9) {
    background-image: url(/shoes/270-black-gold.png);
    transform-origin: bottom right;
  }
</style>

<script>
  export let name = ''
  export let color = ''
</script>

<article>
  <p>{name}</p>
  <p class="color">{color}</p>
</article>

<style>
  article {
    --size: 1.5rem;
    display: grid;
    align-content: center;
    container: item / size;
    background-position: center;
    background-size: cover;
    background-color: #eee;
    text-align: center;
    overflow: hidden;
    transition: scale 0.2s ease-in-out;
  }

  article p {
    position: relative;
    margin: 0;
    padding: calc(var(--size) / 2);
    color: black;
    font-size: 15cqmin;
    font-weight: 900;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: white;
  }

  article p:before {
    content: '';
    display: block;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: var(--purple);
    mix-blend-mode: color;
    z-index: -1;
  }

  article p.color {
    font-size: 5cqw;
    text-transform: uppercase;
    letter-spacing: 0.2cqmin;
  }

  article:where(:hover, :focus) {
    align-content: space-between;
    color: white;
    border-radius: var(--size);
    box-shadow: 0 0 calc(var(--size) * 2) var(--size) rgba(0, 0, 0, 0.5);
    scale: 1.1;
    z-index: 2;
  }

  :global(.grid:has(article:hover) article:not(:hover)) {
    mix-blend-mode: luminosity;
  }

  article:nth-child(1) {
    background-image: url(/shoes/vapormax-plus-black.jpg);
    transform-origin: top left;
  }
  article:nth-child(2) {
    background-image: url(/shoes/vapirmax-ashphalt.jpg);
    transform-origin: top center;
  }
  article:nth-child(3) {
    background-image: url(/shoes/vaporma-plus-grape.jpg);
    transform-origin: top right;
  }
  article:nth-child(4) {
    background-image: url(/shoes/airmax-leopard.webp);
    transform-origin: left center;
  }
  article:nth-child(5) {
    background-image: url(/shoes/airmax-wheat-gold.jpg);
    transform-origin: center center;
  }
  article:nth-child(6) {
    background-image: url(/shoes/flyknit-zebra.jpg);
    transform-origin: right center;
  }
  article:nth-child(7) {
    background-image: url(/shoes/Nike-Air-Max-270-React-Camo-Black-On-Foot-Side_w900.jpg);
    transform-origin: bottom left;
  }
  article:nth-child(8) {
    background-image: url(/shoes/270-black-gold.png);
    transform-origin: bottom center;
  }
  article:nth-child(9) {
    background-image: url(/shoes/270-black-gold.png);
    transform-origin: bottom right;
  }
</style>

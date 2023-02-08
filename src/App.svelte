<script>
  import shoes from './db'
  import Card from './Card.svelte'
</script>

<div class="grid">
  {#each shoes as { name, color }}
    <Card {name} {color} />
  {/each}
</div>

<style>
  *,
  *:before,
  *:after {
    box-sizing: border-box;
  }

  :root {
    --purple: radial-gradient(
      circle farthest-corner at 10% 20%,
      rgb(64, 84, 178) 0%,
      rgb(219, 2, 234) 90%
    );
  }

  :global(body) {
    margin: 0;
    padding: 0;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu,
      Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }

  .grid {
    --col1: 1fr;
    --col2: 1fr;
    --col3: 1fr;
    --row1: 1fr;
    --row2: 1fr;
    --row3: 1fr;
    display: grid;
    grid-template-columns: var(--col1) var(--col2) var(--col3);
    grid-template-rows: var(--row1) var(--row2) var(--row3);
    height: 100vh;
    background-image: var(--purple);
    transition: all 0.2s ease-in-out;
  }

  .grid:has(.item:nth-child(3n + 1):hover) {
    --col1: 2fr;
  }

  .grid:has(.item:nth-child(3n + 2):hover) {
    --col2: 2fr;
  }

  .grid:has(.item:nth-child(3n + 3):hover) {
    --col3: 2fr;
  }

  .grid:has(.item:nth-child(n + 1):nth-child(-n + 3):where(:hover, :focus)) {
    --row1: 2fr;
  }

  .grid:has(.item:nth-child(n + 4):nth-child(-n + 6):where(:hover, :focus)) {
    --row2: 2fr;
  }

  .grid:has(.item:nth-child(n + 7):nth-child(-n + 9):hover) {
    --row3: 3fr;
  }
</style>

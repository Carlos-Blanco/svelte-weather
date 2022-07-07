<script>
  import Weather from './lib/Weather.svelte'

  let city="Madrid";
</script>

<main>
  <input type="text" placeholder="Enter a city" bind:value={city} />

  <Weather location={city}/>


</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }

  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }

</style>

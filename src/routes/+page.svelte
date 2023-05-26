<script>
  import Details from "../lib/Details.svelte";
  import { onMount } from "svelte";

  const BASE_URL = "https://rickandmortyapi.com/";
  let locationData = "";
  let img = "";

  onMount(async () => {
    fetch(`${BASE_URL}api/character`)
      .then((r) => r.json())
      .then((data) => {
        img = data.results[0].image;
        locationData = data.results[0].location.name;
      });
  });
</script>

<div class="grid">
  {#each { length: 6 } as item}
    <Details {locationData} {img} />
  {/each}
</div>

<style>
  .grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 30px;
  }
</style>

<script>
  import { page } from "$app/stores";
  import { onMount } from "svelte";

  const BASE_URL = "https://rickandmortyapi.com/";
  let dimension = "";
  let type;
  let residents = 0;
  let name;
  onMount(async () => {
    fetch(`${BASE_URL}/api/location?id=4`)
      .then((r) => r.json())
      .then((data) => {
        dimension = data.results[0].dimension;
        type = data.results[0].type;
        residents = data.results[0].residents.length;
        name = data.results[0].name;
      });
  });

  const location_id = $page.url.searchParams.get("/location?id=4");
  console.log(location_id);
</script>

<div>
  <h1>{name}</h1>
  <h3>{type} | {dimension}</h3>
  <h5>{residents} residents</h5>
</div>

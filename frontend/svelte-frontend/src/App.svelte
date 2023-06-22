<script>
  // Source : https://www.sitepoint.com/svelte-fetch-data/
  // Fetch Method 
  
  import { onMount } from "svelte";

  const endpoint = "http://127.0.0.1:8000/book";

  let posts = [];

  onMount(async function () {
    const response = await fetch(endpoint);
    const data = await response.json();
    posts = data;
    console.log(posts);
  });

</script>

{#each posts as key}
  <div>
    <p>{key.title}</p>
    <p>{key.author}</p>
  </div>
{/each}
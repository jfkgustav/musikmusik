<script>
	import { onMount } from 'svelte';
	let music_table = [];

	onMount(async () => {
		const response = await fetch('https://localhost:7114/Song/');
		const data = await response.json();
		music_table = data;
    console.log(data);
  });


</script>

<svelte:head>
	<title>Musik API</title>
	<meta name="description" content="Musik API" />
</svelte:head>

<section class="container">
	<div class="grid grid-cols-2 justify-between">
		<p>id</p> <p>song name</p>
		{#each music_table as song}
   
			<p>{song.id}</p>
      <p>{song.name}</p>
	 
  {/each}
	</div>
</section>

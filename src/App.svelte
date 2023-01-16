<script>
  	import { jobListingStore } from './stores.js';
  	import Card from './lib/Card.svelte';
</script>

<header/>

<main>
	{#each $jobListingStore as jobListing}
    	<Card {...jobListing}/>
  	{/each}
</main>

<style>
	header {
		width: 100%;
		height: 156px;
		background-color: #5CA5A5;
		background-image: url(/images/bg-header-desktop.svg);
  	}

  	main {
		width: 100%;
		max-width: 1190px;
		display: flex;
		flex-direction: column;
		gap: 24px;
		margin: 76px 0;
		padding: 0 40px;
  	}
</style>

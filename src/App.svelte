<script>
  	import { jobListings, userFilters, filteredJobListings } from './stores.js';
  	import Card from './lib/Card.svelte';
	import FilterControls from './lib/FilterControls.svelte';
</script>

<header/>

<main>
	<div class="container">
		{#if $userFilters.length > 0}
			<FilterControls/>
		{/if}
		{#each $jobListings as job}
			<Card {...job}/>
		{/each}
	</div>
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
		padding: 0 40px;
		display: flex;
		justify-content: center;
	}

	.container {
		width: 100%;
		max-width: 1110px;
		display: flex;
		flex-direction: column;
		gap: 24px;
		margin: 76px 0;
		position: relative;
  	}
</style>

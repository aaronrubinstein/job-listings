<script>
  	import { jobListings, userFilters, filteredJobListings } from './stores.js';
  	import JobCard from './lib/JobCard.svelte';
	import FilterControlCard from './lib/FilterControlCard.svelte';
</script>

<header/>

<main>
	<div class="container">
		{#if $userFilters.length > 0}
			<FilterControlCard/>
			{#each $filteredJobListings as job (job.id)}
				<JobCard {...job}/>
			{/each}
		{:else}
			{#each $jobListings as job (job.id)}
				<JobCard {...job}/>
			{/each}
		{/if}
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

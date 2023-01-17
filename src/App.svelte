<script>
  	import { jobListings, userFilters, filteredJobListings } from './stores.js';
  	import JobCard from './lib/JobCard.svelte';
	import FilterControlCard from './lib/FilterControlCard.svelte';
</script>

<header/>
<main>
	<div class="main-container">
		{#if $userFilters.length > 0}
			<div class="filter-container">
				<FilterControlCard/>
			</div>
			<div class="job-listing-container">
				{#each $filteredJobListings as job (job.id)}
					<JobCard {...job}/>
				{/each}
			</div>
		{:else}
			<div class="job-listing-container" style="margin-top: 232px;">
				{#each $jobListings as job (job.id)}
					<JobCard {...job}/>
				{/each}
			</div>
		{/if}
	</div>
</main>

<style>
	header {
		width: 100%;
		height: 156px;
		background-color: #5CA5A5;
		background-image: url(/images/bg-header-desktop.svg);
		position: absolute;
  	}

  	main {
		width: 100%;
		padding: 0 40px;
		display: flex;
		justify-content: center;
	}

	.main-container {
		width: 100%;
		max-width: 1110px;
		display: flex;
		flex-direction: column;
	}

	.filter-container {
		width: 100%;
		max-width: 1110px;
		margin-top: 120px;
		margin-bottom: 40px;
		position: relative;
	}

	.job-listing-container {
		display: flex;
		flex-direction: column;
		gap: 24px;
		margin-bottom: 76px;
		position: relative;
  	}
</style>

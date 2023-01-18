<script>
    import { userFilters } from '../stores.js';
    import FilterControl from './FilterControl.svelte';

    function clearFilters() {
        userFilters.set([]);
    }
</script>

<div class="card">
    <div class="filters">
        {#each $userFilters as filter}
            <FilterControl value={filter}/>
        {/each}
    </div>
    <button class="clear-button" type="button" on:click={clearFilters}>Clear</button>
</div>

<style>
    .card {
        min-height: 72px;
        width: 100%;
        border-radius: 5px;
        background: #FFF;
        padding: 20px 40px;
        box-shadow: 0px 15px 20px -5px hsla(189, 81%, 28%, 0.15);
        display: flex; 
        align-items: center;
    }

    .filters {
        display: flex;
        flex-wrap: wrap;
        gap: 16px;
        margin-right: 40px;
    }

    .clear-button {
        font-size: 16px;
        font-weight: 700;
        line-height: 24px;
        letter-spacing: -0.12px;
        margin-left: auto;
        color: #7C8F8F;
        background: none;
        border: none;
        cursor: pointer;
        padding: 0;
    }
    
    .clear-button:hover {
        color: #5CA5A5;
    }

    @media (max-width: 780px) {
        .card {
            padding: 20px 25px 20px 20px;
        }

        .filters {
            margin-right: 20px;
        }
    }
</style>
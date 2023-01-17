<script>
    import { userFilters } from '../stores.js';
    import FilterControl from './FilterControl.svelte';

    function clearFilters() {
        userFilters.set([]);
    }
</script>

<div class="card">
    {#each $userFilters as filter}
        <FilterControl value={filter}/>
    {/each}
    <button type="button" on:click={clearFilters}>Clear</button>
</div>

<style>
    .card {
        height: 72px;
        width: 100%;
        border-radius: 5px;
        background: #FFF;
        padding: 0 40px;
        box-shadow: 0px 15px 20px -5px hsla(189, 81%, 28%, 0.15);
        display: flex; 
        align-items: center;
        position: absolute;
        top: -112px;
        display: flex;
        align-items: center;
        column-gap: 16px;
    }

    button {
        font-size: 16px;
        font-weight: 700;
        line-height: 24px;
        letter-spacing: -0.12px;
        margin-left: auto;
        color: #5CA5A5;
        background: none;
        border: none;
        cursor: pointer;
    }
    
    button:hover {
        color: #2B3939;
    }
</style>
<script>
    import Pill from './Pill.svelte';
    import FilterChip from './FilterChip.svelte';

    export let id;
    export let company;
    export let logo;
    export let newJob;
    export let featured;
    export let position;
    export let role;
    export let level;
    export let postedAt;
    export let contract;
    export let location;
    export let languages;
    export let tools;

    let filterChipValues = [role, level, ...languages, ...tools];

</script>

<div class="card {featured ? 'featured': ''}">
    <img src="{logo}" alt="Company logo" class="logo">
    <div class="job-details">
        <div class="top-row">
            <span class="company">{company}</span>
            <div class="pill-container">
                {#if newJob}
                    <Pill type="newJob"/>
                {/if}
                {#if featured}
                    <Pill type="featured"/>
                {/if}
            </div>
        </div>
        <div class="position">{position}</div>
        <div class="bottom-row">
            <span class="posted-at">{postedAt}</span>
            <span class="dot"></span>
            <span class="contract">{contract}</span>
            <span class="dot"></span>
            <span class="location">{location}</span>
        </div>
    </div>
    <div class="filter-chips">
        {#each filterChipValues as filterChipValue}
            <FilterChip value={filterChipValue}/>
        {/each}
    </div>
</div>

<style>
    .card {
        height: 152px;
        width: 100%;
        border-radius: 5px;
        background: #FFF;
        padding: 32px 40px;
        box-shadow: 0px 15px 20px -5px hsla(189, 81%, 28%, 0.15);
        display: flex; 
        align-items: center;
    }

    .featured {
        border-left: 5px solid #5CA5A5;
    }

    .job-details {
        margin: 0 24px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        min-width: 265px;
    }
    
    .top-row {
        display: flex;
        align-items: center;
        column-gap: 14px;
    }

    .company {
        font-weight: 700;
        font-size: 18px;
        line-height: 16.56px;
        color: #5CA5A5;
    }
    
    .pill-container {
        display: flex;
        align-items: center;
        column-gap: 8px;
    }

    .position {
        font-size: 22px;
        line-height: 24px;
        font-weight: 700;
        color: #2B3939;
        margin-top: 10px;
        margin-bottom: 7px;
        cursor: pointer;
    }

    .position:hover {
        color: #5CA5A5;
    }

    .bottom-row {
        display: flex;
        align-items: center;
        column-gap: 16px;
        font-size: 18px;
        line-height: 24px;
        letter-spacing: -0.14px;
        color: #7C8F8F;
    }
    
    .dot {
        height: 4px;
        width: 4px;
        border-radius: 50%;
        background: #B7C4C4;
    }

    .filter-chips {
        display: flex;
        justify-content: flex-end;
        align-items: center;
        gap: 16px;
        flex-wrap: wrap;
        margin-left: auto;
    }
</style>
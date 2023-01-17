<script>
    import { userFilters } from '../stores.js';
    
    export let value;

    function removeFilter(e) {
        userFilters.set($userFilters.filter(item => item !== e.target.value));
    }
</script>

<div class="chip">
    <div class="chip-content">
        {value}
    </div>
    <button class="remove-filter" type="button" {value} on:click={removeFilter}>
        <img src="/images/icon-remove.svg" alt="Remove filter">
    </button>
</div>

<style>
    .chip {
        height: 32px;
        background: hsla(180, 29%, 50%, 0.1);
        border-radius: 4px;
        display: flex;
        column-gap: 9px;
        overflow: hidden;
    }

    .chip-content {
        height: 100%;
        padding-left: 9px;
        padding-top: 3px;
        font-size: 16px;
        font-weight: 700;
        line-height: 24px;
        letter-spacing: -0.12px;
        color: #5CA5A5;
        display: flex;
        align-items: center;
    }

    .remove-filter {
        height: 100%;
        width: 32px;
        background: #5CA5A5;
        border: none;
        display: flex;
        justify-content: center;
        align-items: center;
        cursor: pointer;
    }

    .remove-filter:hover {
        background: #2B3939;
    }

    img {
        pointer-events: none;
    }
</style>
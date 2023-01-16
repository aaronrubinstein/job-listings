<script>
    import { userFilters } from '../stores.js';
    export let value;
    
    function addFilter(e) {
        if ($userFilters.includes(e.target.value)) {return}
        userFilters.update(filters => [...filters, e.target.value]);
    }
</script>

<button class="chip" type="button" {value} on:click={addFilter}>
    {value}
</button>

<style>
    .chip {
        height: 32px;
        background: hsla(180, 29%, 50%, 0.1);
        border-radius: 4px;
        border: none;
        padding: 0 9px;
        padding-top: 3px;
        font-size: 16px;
        font-weight: 700;
        line-height: 24px;
        letter-spacing: -0.12px;
        color: #5CA5A5;
        display: flex;
        align-items: center;
        cursor: pointer;
    }

    .chip:hover {
        background: #5CA5A5;
        color: #FFF;
    }
</style>
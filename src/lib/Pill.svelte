<script>
    export let type;
</script>

<span class="pill {type}"></span>

<style>
    .pill {
        display: flex;
        align-items: center;
        height: 24px;
        border-radius: 12px;
        padding: 0 8px;
        font-size: 14px;
        font-weight: 700;
        letter-spacing: -0.11px;
        color: #FFF;
        text-transform: uppercase;
        padding-top: 3px;
    }

    .newJob {
        background: #5CA5A5;
    }

    .newJob::before {
        content: 'NEW!';
    }

    .featured {
        background: #2B3939;
    }

    .featured:before {
        content: 'FEATURED';
    }
</style>
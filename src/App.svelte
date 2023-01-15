<script>
  import Card from './lib/Card.svelte';
</script>

<header/>

<main>
      <Card/>
      <Card/>
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
    max-width: 1110px;
    display: flex;
    flex-direction: column;
    gap: 24px;
    margin: 76px 165px 76px 165px;
  }


</style>

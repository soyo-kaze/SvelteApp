<script>
  import Header from "./components/Header.svelte";
  import TodoBox from "./components/TodoBox.svelte";
  let time = new Date(Date.now()).getHours();
</script>

<main>
  <Header />
  <div class="title">
    {#if time < 12}
      <p>Good Morning🌄</p>
    {:else if time < 17}
      <p>Good Afternoon🕛</p>
    {:else if time < 20}
      <p>Good Evening🌆</p>
    {:else}
      <p>Good Night🌃</p>
    {/if}
  </div>
  <TodoBox />
</main>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
  }
  .title {
    display: flex;
    justify-content: center;
    width: 100%;
    align-items: center;
    margin-top: 40px;
    font-family: google;
    font-size: 40px;
    font-weight: 600;
  }
  .title > p::selection {
    color: purple;
    /* background-color: cornflowerblue; */
    text-shadow: 3px 3px 14px rgba(117, 52, 191, 0.3);
  }
</style>

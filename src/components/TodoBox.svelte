<script>
  import { store } from "../store";
  import Tasks from "./Tasks.svelte";
  let item = "";
  $: console.log($store);
</script>

<main>
  <div class="container">
    <form
      on:submit|preventDefault={() => {
        store.update((n) =>
          item.length != 0
            ? [...n, { item, key: n.length + 1 }]
            : alert("Task is empty")
        );
        item = "";
      }}
    >
      <input type="text" bind:value={item} style="margin-right: 5px;" />
      <button type="submit">Add</button>
    </form>
    <Tasks />
    <p style="margin-bottom:0;color:gray;font-family:google;font-size:14px">
      <cite>
        {$store.length} Remaning tasks
      </cite>
    </p>
  </div>
</main>

<style>
  main {
    height: 100%;

    display: flex;
    justify-content: center;
    align-items: center;
  }
  form {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .container {
    display: flex;
    /* align-items: center; */
    border-radius: 20px;
    border: 1px solid rgb(182, 182, 182);
    padding: 20px;
    min-width: 300px;
    margin: 10px;
    flex-direction: column;
  }
</style>

<script>
  import { store } from "../store";
  function handleDelete(key) {
    $store = $store.filter((task) => task.key != key);
  }
</script>

<main>
  <ul>
    {#each $store as task}
      <li>
        <div class="tasks">
          <p>
            {task.item}
          </p>
          <p on:click={() => handleDelete(task.key)} class="delete">❌</p>
        </div>
      </li>
    {/each}
  </ul>
</main>

<style>
  .tasks {
    /* flex-direction: column; */
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-family: google;
  }
  p {
    margin: 2px;
  }
  .delete {
    cursor: pointer;
  }
</style>

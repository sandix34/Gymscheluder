<script>
  import { onMount } from "svelte";
  export let summary;
  export let days;
  let formattedData;
  let isDataFormated = false;

  const prepareSummary = () => {
    formattedData = summary.reduce((acc, curr) => {
      if (Object.keys(acc).includes(curr.title)) {
        acc[curr.title] = [...acc[curr.title], curr];
      } else {
        acc[curr.title] = [curr];
      }
      return acc;
    }, {});
    isDataFormated = true;
    console.log(formattedData);
  };

  onMount(() => {
    prepareSummary();
  });
</script>

<style>

</style>

{#if isDataFormated}
  <h2>Summary</h2>
  {#if summary.length}
    {#each Object.keys(formattedData) as day}
      <h2>{day}</h2>
      {#each formattedData[day] as ex}
        {ex.activity}: {ex.sets} set of {ex.reps} reps
        <br />
      {/each}
    {/each}
  {:else}
    <div>Missing data: please add exercises</div>
  {/if}
{/if}

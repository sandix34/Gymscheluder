<script>
  import TrainingDayDetails from './TrainingDayDetails.svelte'

  const nbOfDays = [
    { id: 1, text: "One day", value: [1] },
    { id: 2, text: "Two days", value: [1, 2] },
    { id: 3, text: "Three days", value: [1, 2, 3] },
    { id: 4, text: "Four day", value: [1, 2, 3, 4] },
    { id: 5, text: "Five days", value: [1, 2, 3, 4, 5] },
    { id: 6, text: "Six days", value: [1, 2, 3, 4, 5, 6] },
    { id: 7, text: "Seven day", value: [1, 2, 3, 4, 5, 6, 7] }
  ];

  let ndDaysTrainingPerWeek;
</script>

<style>

</style>

<div>
  <form>
    <select bind:value={ndDaysTrainingPerWeek}>
      {#each nbOfDays as day (day.id)}
        <option value={day}>{day.text} per week</option>
      {/each}
    </select>
  </form>
   {JSON.stringify(ndDaysTrainingPerWeek)}
</div>

{#if ndDaysTrainingPerWeek}
<div>
  {#each ndDaysTrainingPerWeek.value as dayNumber, i}
    <div>
      <TrainingDayDetails title={ `day ${++i}` } />
    </div>
  { /each }
</div>
{/if}

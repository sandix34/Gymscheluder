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
  .all-days {
        border: 2px solid purple;
        margin: 5px;
    }

    .training-day-details {
        border: 2px solid green;
        margin: 5px;
    }
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
<div class="all-days ">
  {#each ndDaysTrainingPerWeek.value as dayNumber, i}
    <div class="training-day-details">
      <TrainingDayDetails title={ `day ${++i}` } />
    </div>
  { /each }
</div>
{/if}

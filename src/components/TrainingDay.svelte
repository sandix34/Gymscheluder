<script>
  const nbOfDays = [
    { id: 1, text: "One day", value: 1 },
    { id: 2, text: "Two days", value: 2 },
    { id: 3, text: "Three days", value: 3 },
    { id: 4, text: "Four day", value: 4 },
    { id: 5, text: "Five days", value: 5 },
    { id: 6, text: "Six days", value: 6 },
    { id: 7, text: "Seven day", value: 7 }
  ];

  let ndDaysTrainingPerWeek;
</script>

<style>

</style>

<div>
  <form>
    <select bind:value={ndDaysTrainingPerWeek}>
      {#each nbOfDays as day (day.id)}
        <option value={day}>{day.text}</option>
      {/each}
    </select>
  </form>
   {JSON.stringify(ndDaysTrainingPerWeek)}
</div>

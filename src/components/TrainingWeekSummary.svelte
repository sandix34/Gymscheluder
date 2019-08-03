<script>
    import { onMount} from 'svelte';
    export let summary;
    export let days;
    let formattedData;
    let isDataFormated = false;

    const prepareSummary = () => {
        formattedData = summary.reduce((acc, curr)=>{
            if (Object.keys(acc).includes(curr.title)) {
                acc[curr.title] = [...acc[curr.title], curr]
            } else {
                acc[curr.title] = [curr];
            }
            return acc;
        }, {});
        isDataFormated = true;
        console.log(formattedData);
        
    }

    onMount(()=> {
        prepareSummary();
    })
    
</script>
<style></style>
<h2>Summary</h2>
{#if isDataFormated}
{formattedData}
{/if}
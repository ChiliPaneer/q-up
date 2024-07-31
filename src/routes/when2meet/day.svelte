<script>
    export let updateDay;
    import Hour from './hour.svelte';
    let dayBegin = 6;
    let dayEnd = 20;
    let hours = []
    for (let i = dayBegin; i < dayEnd; i++) {
      hours.push(i)
    }



</script>
<div>
 {#each hours as hour}
    <Hour updateHour={updateDay(hour)}/>
{/each}
</div>

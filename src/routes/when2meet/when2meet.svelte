<script>
	import Day from './day.svelte';
	let week = []
	for (let i = 0; i < 7; i++) {
  	 week.push(i)
	}
	let updateWeek = (day) => (hour) => (minute) => {
	  console.log("Day:" + day)
      console.log("Hour:" + hour)
      console.log("Minute" + minute)
    }
</script>

<div class="flex flex-row mx-5">
    {#each week as day}
        <!-- <h2> Day {day} </h2> -->
        <div>
            <Day updateDay={updateWeek(day)}/>
        </div>
    {/each}
</div>

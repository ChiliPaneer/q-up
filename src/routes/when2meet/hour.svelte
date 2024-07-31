<script>
    export let updateHour;
</script>
<div class="bg-red-50 border-4 rounded w-20 h-16">
    <div on:mouseover={() => updateHour(0)}>a</div>
	<div on:mouseover={() => updateHour(15)}>b</div>
	<div on:mouseover={() => updateHour(30)}></div>
	<div on:mouseover={() => updateHour(45)}></div>
</div>

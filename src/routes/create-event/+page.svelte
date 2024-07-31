<script lang="ts">
	const daysOfWeek = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
	const today = new Date();
	const nextDates = [...Array(28).keys()].map(
		(i) => new Date(today.getFullYear(), today.getMonth(), today.getDate() + i - today.getDay())
	);
</script>

<div class="m-10">
	<div class="grid grid-cols-7 gap-2 max-w-50">
		{#each daysOfWeek as day}
			<div class="mx-1">{day}</div>
		{/each}
		{#each nextDates as date}
			<div class="{date.getDate() == today.getDate() ? 'font-bold' : 'font-normal'} bg-gray-200">
				{date.getDate()}
			</div>
		{/each}
	</div>
	<a href="/">home</a>
</div>

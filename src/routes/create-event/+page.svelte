<script lang="ts">
	const daysOfWeek = ['S', 'M', 'T', 'W', 'T', 'F', 'S'];
	const today = new Date();
	const nextDates = [...Array(28).keys()].map(
		(i) => new Date(today.getFullYear(), today.getMonth(), today.getDate() + i - today.getDay())
	);
	let selectedDates: Date[] = [];
	const handleOnClickDates = (date: Date) => {
		selectedDates.includes(date)
			? (selectedDates = [...selectedDates.filter((d) => d !== date)])
			: (selectedDates = [...selectedDates, date]);
	};
</script>

<div class="flex justify-left m-10">
	<div class="grid grid-cols-7 gap-2">
		{#each daysOfWeek as day}
			<div class="mx-1 flex justify-center">{day}</div>
		{/each}
		{#each nextDates as date}
			<div
				on:click={() => handleOnClickDates(date)}
				class="{date.getDate() == today.getDate()
					? 'font-bold'
					: 'font-normal'} {selectedDates.includes(date)
					? 'bg-primary'
					: 'bg-white hover:bg-primary'} flex justify-center hover:cursor-pointer"
			>
				{date.getDate()}
			</div>
		{/each}
	</div>
</div>

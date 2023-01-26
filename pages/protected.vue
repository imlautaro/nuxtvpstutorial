<script setup lang="ts">
definePageMeta({
	middleware: 'authenticated',
})

useHead({
	title: 'Protected page',
})
</script>

<template>
	<div>
		<img
			src="https://upload.wikimedia.org/wikipedia/commons/c/c1/Six_weeks_old_cat_%28aka%29.jpg"
		/>
	</div>
</template>

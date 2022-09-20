<script setup>
const props = defineProps(["data"]);
</script>

<template>
	<h2 class="grouplist__group" :class="data.group.toLowerCase() + '__text'">
		{{ data.group }}
	</h2>
</template>

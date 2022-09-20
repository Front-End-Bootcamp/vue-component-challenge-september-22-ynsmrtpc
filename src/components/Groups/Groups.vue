<script setup>
const props = defineProps(["data"]);
</script>

<template>
	<h2 class="grouplist__group" :class="'text_' + data.group.toLowerCase()">
		{{ data.group }}
	</h2>
</template>

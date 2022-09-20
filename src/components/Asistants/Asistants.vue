<script setup>
const props = defineProps(["data"]);
</script>

<template>
	<div class="asistant" :class="data.group.toLowerCase()">
		{{ data.asistants }}
	</div>
</template>

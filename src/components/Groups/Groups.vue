<script setup>
const props = defineProps(["data"]);
</script>

<template>
	<h3 class="grouplist__group">
		{{ data.group }}
	</h3>
</template>

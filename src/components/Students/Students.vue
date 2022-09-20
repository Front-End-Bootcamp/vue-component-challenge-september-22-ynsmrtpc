<script setup>
const props = defineProps(["students"]);
</script>

<template>
	<ul class="students" v-for="student in students" :key="student.id">
		<li class="students__list" :class="'text_' + student.group.toLowerCase()">
			{{ student.name }}
		</li>
	</ul>
</template>

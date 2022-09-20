<template>
	<div class="container" v-for="data in datas" :key="data.name">
		<div class="grouplist">
			<h3 class="grouplist__group">
				{{ data.group }}
			</h3>

			<hr class="line" />

			<ul class="students" v-for="student in data.students" :key="student.id">
				<li class="students__list">{{ student.name }}</li>
			</ul>

			<div class="asistant" :class="data.group.toLowerCase()">
				{{ data.asistants }}
			</div>
		</div>
	</div>
</template>

<script setup>
const props = defineProps(["datas"]);
</script>

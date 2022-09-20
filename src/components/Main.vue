<script setup>
import Groups from "./Groups/Groups.vue";
import Students from "./Students/Students.vue";
import Asistants from "./Asistants/Asistants.vue";
const props = defineProps(["datas"]);
</script>

<template>
	<div class="container" v-for="data in datas" :key="data.name">
		<div class="grouplist">
			<Groups :data="data" />
			<hr class="line" />
			<Students :students="data.students" />
			<Asistants :data="data" />
		</div>
	</div>
</template>

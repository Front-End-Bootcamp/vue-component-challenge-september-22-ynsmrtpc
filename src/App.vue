<script setup>
import Main from "./components/Main.vue";
import axios from "axios";
import { ref, onMounted } from "vue";

const filteredData = ref();

async function getStudents() {
	const students = await axios
		.get("src/assets/data/students.json")
		.then((student) => student.data);
	return students;
}

function getGroupNames(data) {
	const groups = data.map((student) => student.group);
	const uniqNames = [...new Set(groups)];
	return uniqNames;
}

function filterByAsistants(data) {
	let asistants = data.filter((student) => student.type);
	let students = data.filter((student) => !student.type);

	asistants = asistants.map((asistant) => {
		const filteredStudents = students.filter(
			(student) => student.group === asistant.group
		);
		return {
			group: asistant.group,
			asistants: asistant.name,
			students: filteredStudents,
		};
	});
	return asistants;
}
onMounted(async () => {
	const data = await getStudents();
	getGroupNames(data);
	filteredData.value = filterByAsistants(data);
});
</script>

<template>
	<Main :data="filteredData" />
</template>

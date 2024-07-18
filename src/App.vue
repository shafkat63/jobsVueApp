<script>
import { ref } from "vue";

export default {
	setup() {
		const name = ref("Ezio Altair");
		const status = ref("active");
		const tasks = ref([
			"Task one",
			"Task two",
			"Task three",
			"Task four",
			"Task five",
			"Task six",
			"Task seven",
			"Task eight",
			"Task nine",
			"Task ten",
		]);

		const toggleStatus = () => {
			if (status.value === "active") {
				status.value = "pending";
			} else if (status.value === "pending") {
				status.value = "inactive";
			} else {
				status.value = "active";
			}
		};

		return {
			name,
			status,
			tasks,
			toggleStatus,
		};
	},
};
</script>

<template>
	<h1>{{ name }}</h1>
	<p v-if="status === 'active'">User is Active</p>
	<p v-else-if="status === 'pending'">User is Pending</p>
	<p v-else>User is InActive</p>
	<h3>Tasks:</h3>
	<ul>
		<li v-for="task in tasks" :key="task">
			{{ task }}
		</li>
	</ul>
	<!-- <a v-bind:href="link">Click for MDN</a> -->
	<a :href="link">Click for MDN</a>
	<br />
	<!-- <button v-on:click="toggleStatus" >Change Status</button> -->
	<button @click="toggleStatus">Change Status</button>
</template>

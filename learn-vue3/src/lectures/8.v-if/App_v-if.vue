<template>
	<div>
		<h2 v-if="visable">Hello Vue3</h2>
		<h2 v-else>false 입니다.</h2>
		<button v-on:click="visable = !visable">toggle</button>
		<hr />
		<button v-on:click="type = 'A'">A</button>
		<button v-on:click="type = 'B'">B</button>
		<button v-on:click="type = 'C'">C</button>
		<button v-on:click="type = 'D'">D</button>

		<h2 v-if="type === 'A'">A입니다.</h2>
		<h2 v-else-if="type === 'B'">B입니다.</h2>
		<h2 v-else-if="type === 'C'">C입니다.</h2>
		<h2 v-else>A,B,C가 아닙니다.</h2>
		<hr />
		<template v-if="visable">
			<h1>Title</h1>
			<p>Paragraph 1</p>
			<p>Paragraph 2</p>
		</template>
		<hr />
		<h1 v-show="ok">Title 입니다.</h1>
		<!--무언가를 자주 전환해야한다면 v-show가 효율적-->
		<button v-on:click="ok = !ok">show toggle</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const visable = ref(true);
		const type = ref('A');
		const ok = ref(true);

		return { visable, type, ok };
	},
};
</script>

<style scoped></style>

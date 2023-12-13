<template>
	<div>
		<div v-bind:class="classObject">텍스트입니다.</div>
		<button v-on:click="toggle">toggle</button>
		<button v-on:click="hasError = !hasError">toggleError</button>
	</div>
</template>

<script>
import { reactive, ref } from 'vue';

export default {
	setup() {
		const isActive = ref(true);
		const hasError = ref(false);

		// const classObject = reactive({
		// 	active: true,
		// 	'text-danger': false,
		// });

		const toggle = () => {
			isActive.value = !isActive.value;
		};

		return {
			isActive,
			toggle,
			hasError,
			classObject,
		};
	},
};
</script>

<style scoped>
.text-danger {
	color: red;
}
</style>

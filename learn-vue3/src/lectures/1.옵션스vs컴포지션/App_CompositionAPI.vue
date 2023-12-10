<template>
	<div>
		<button v-on:click="increament">Counter : {{ counter }}</button>
	</div>
</template>

<script>
import { onMounted, ref } from 'vue';

export default {
	setup() {
		const counter = ref(0);

		const increament = () => counter.value++;

		onMounted(() => {
			console.log('컴포넌트가 마운트 되었습니다.');
		});

		return {
			counter,
			increament,
		};
	},
};
</script>

<style lang="scss" scoped></style>

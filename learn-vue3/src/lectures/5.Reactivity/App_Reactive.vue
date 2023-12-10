<template>
	<div>
		<button v-on:click="increament">Click{{ state.count }}</button>
		<button v-on:click="increament">Deep Click{{ state.deep.count }}</button>
	</div>
</template>

<script>
import { reactive } from 'vue';

export default {
	setup() {
		const state = reactive({
			count: 0,
			deep: {
				count: 0,
			},
		});

		const increament = () => {
			state.count++;
			state.deep.count++;
		};
		return {
			state,
			increament,
		};
	},
};
</script>

<style lang="scss" scoped></style>

<template>
	<div></div>
</template>

<script>
import { reactive, ref } from 'vue';

export default {
	setup() {
		//ref > Object에서 사용 > 값을 가져올때 .value필요없음
		const count = ref(0);
		const state = reactive({
			count,
		});
		console.log(count.value);
		console.log('state.count : ', state.count);

		//ref > Array에서 사용 > 값을 가져올때 .value  필요함
		const message = ref('Hello');
		const arr = reactive([message]);
		console.log('arr[0] : ', arr[0].value);
		return {
			count,
			state,
		};
	},
};
</script>

<style lang="scss" scoped></style>

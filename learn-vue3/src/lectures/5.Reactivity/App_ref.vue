<template>
	<div>
		<p>{{ message }}</p>
		<button v-on:click="addMessage">add click</button>
	</div>
</template>

<script>
import { reactive, ref } from 'vue';

export default {
	setup() {
		//let message = reactive('Hello Vue!'); //reactive로 반응형으로 만들려면 객체화 시켜서 message.value 같은 식으로 사용해야함
		let message = ref('Hello Vue'); //ref는 알아서 반응형으로 랩핑한다.

		const addMessage = () => {
			message.value = message.value + '!';
		};

		console.log('message : ', message); //이런식으로  reactive로 정의하면 반응형으로 사용할 수 없다. > ref 사용!
		console.log('message type : ', typeof message.value);

		return {
			message,
			addMessage,
		};
	},
};
</script>

<style lang="scss" scoped></style>

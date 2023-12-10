<template>
	<div>
		<h2>보간법</h2>
		<p>{{ message }}</p>
		<p v-once>{{ message }}</p>
		<button v-on:click="message = message + '!'">Click!</button>
		<hr />
		<h2>v-html</h2>
		<!--v-html은 xss 취약점으로 이어질수 있기때문에 신뢰할수 있는 컨텐츠에서만 사용하고 일반 사용자가 제공하는 컨텐츠에서는 사용하지 않는것을 권장 -->
		<p>{{ reteral }}</p>
		<p v-html="reteral"></p>
		<hr />
		<h2>속성 바인딩</h2>
		<div v-bind:title="dynamicTitle">마우스를 올려보세요.</div>
		<input type="text" value="홍길동" v-bind:disabled="isInputDisabled" />
		<!--객체를 바인딩 시킴으로서 다중 속성 바인딩이 가능-->
		<input v-bind="attribute" />
		<hr />
		<!--java script 문법도 사용 가능-->
		<h2>Java Script</h2>
		{{ message.split('').reverse().join('') }}
		<br />
		{{ isInputDisabled ? '예' : '아니요' }}
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const message = ref('안녕하세요!');
		const reteral = ref('<strong>안녕하세요</strong>');

		const dynamicTitle = ref('안녕하세요@@@@@@!!!!');
		const isInputDisabled = ref(false);
		const attribute = ref({
			type: 'password',
			value: '1234',
			disabled: false,
		});

		return {
			message,
			reteral,
			dynamicTitle,
			isInputDisabled,
			attribute,
		};
	},
};
</script>

<style lang="scss" scoped></style>

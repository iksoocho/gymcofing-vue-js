<template>
	<div>
		<p>{{ teacher.name }}</p>
		<h3>강의가 있습니까?</h3>
		<p>{{ hasLecture }}</p>
		<p>{{ hasLecture }}</p>
		<p>{{ existLeecture() }}</p>
		<p>{{ existLeecture() }}</p>
		<button v-on:click="counter++">Counter : {{ counter }}</button>
		<h2>이름</h2>
		<p>{{ fullName }}</p>
	</div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
	setup() {
		const teacher = reactive({
			name: '짐코딩',
			lectures: ['HTML/CSS', 'Java Script', 'Vue3'],
		});

		//computed 미리 계산되어서 캐쉬에 저장 되어 계속 사용가능
		const hasLecture = computed(() => {
			console.log('computed');
			return teacher.lectures.length > 0 ? '있음👨' : '없음👎';
		});
		//method는 사용할때마다 새로 호출, 화면이 렌더링 될때도 다시 호출
		const existLeecture = () => {
			console.log('method');
			return teacher.lectures.length > 0 ? '있음👨' : '없음👎';
		};

		const counter = ref(0);

		const firstName = ref('홍');
		const lastName = ref('길동');

		// const fullName = computed(() => {
		// 	return firstName.value + ' ' + lastName.value;
		// });
		const fullName = computed({
			get() {
				return firstName.value + ' ' + lastName.value;
			},
			set(value) {
				console.log('value : ', value);
				console.log(value.split(' '));
				[firstName.value, lastName.value] = value.split(' ');
			},
		});
		console.log(fullName.value);
		fullName.value = '짐 코딩';
		return {
			teacher,
			hasLecture,
			existLeecture,
			counter,
			fullName,
		};
	},
};
</script>

<style lang="scss" scoped></style>

<template>
	<div>
		<h2>input value</h2>
		<!-- <input type="text" v-model.lazy="inputValue"> -->
		<!-- <input type="text" v-model.number="inputValue"> .number은 입력받은 value로 바로 사칙연산을 해야 할때 유용하다 -->
		<input type="text" v-model.trim="inputValue">
		<!-- :value="inputValue" v-on:input="event => (inputValue = event.target.value)" -->
		<div>{{ inputValue }}</div>
		<div>{{ typeof inputValue }}</div>

		<h2>textarea value</h2>
		<textarea v-model="textareaValue"></textarea>
		<div>{{ textareaValue }}</div>

		<h2>checkbox value</h2>
		<label for="checkbox">{{ checkboxValue }}</label>
		<input type="checkbox" id="checkbox" 
		 v-model="checkboxValue"
		 true-value="yes" false-value="no">
		<!-- :checked="checkboxValue" @change="event => checkboxValue = event.target.checked" -->
	</div>

	<h2>radio value</h2>
	<label >
		<input type="radio" name="type" value="O" v-model="radioValue">O형
	</label>
	<label >
		<input type="radio" name="type" value="A" v-model="radioValue">A형
	</label>
	<div>
		{{ radioValue }}
	</div>
 
	<h2>select value</h2>
		<select v-model="selectValue">
			<option value="html">HTML 수업</option>
			<option value="css">CSS 수업</option>
			<option value="javascript">JavaScript 수업</option>
		</select>	
	<div>{{ selectValue }}</div> 

	<h2>checkbox values</h2>
	<label>
		<input type="checkbox" value="html" v-model="checkboxValues">html
	</label>
	<label >
		<input type="checkbox" value="css" v-model="checkboxValues">css
	</label>
	<label >
		<input type="checkbox" value="javascript" v-model="checkboxValues">javascript
	</label>
	<div>{{ checkboxValues }}</div>

</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const inputValue = ref(null)
		const textareaValue = ref(null)
		const checkboxValue = ref('yes')
		const radioValue = ref('O')
		const selectValue = ref('html')
		const checkboxValues = ref([])

		return {inputValue,textareaValue,checkboxValue,radioValue,selectValue,checkboxValues};
	},
};
</script>

<style lang="scss" scoped></style>

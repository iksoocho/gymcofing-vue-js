<template>
	<div>
		<div v-bind:style="styleObject">
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo minus
			reiciendis impedit et non, magnam facilis sequi perferendis voluptates,
			dolor quia esse dignissimos repellat architecto repellendus earum
			necessitatibus? Itaque, voluptatem.
		</div>
		<button v-on:click="fontsize++">+</button>
		<button v-on:click="fontsize--">-</button>
	</div>
</template>

<script>
import { reactive, computed, ref } from 'vue';

export default {
	setup() {
		// const styleObject = reactive({
		// 	color: 'red',
		// 	fontsize: '13px',
		// });

		const fontsize = ref(13);
		const styleObject = computed(() => {
			return {
				color: 'red',
				fontSize: fontsize.value + 'px',
			};
		});
		return { styleObject, fontsize };
	},
};
</script>

<style lang="scss" scoped></style>

<template>
	<div class="card">
		<div class="card-body">
			<!-- type : news, notice -->
			<span class="badge bg-secondary">{{ typeName }}</span>
			<h5 class="card-title red mt-2">{{ title }}</h5>
			<p class="card-text">{{ contents }}</p>
			<a href="#" class="btn" :class="isLikeClass" @click="toggleLike"
				>좋아요</a
			>
		</div>
	</div>
</template>

<script>
import { computed } from 'vue';

export default {
	props: {
		type: {
			type: String,
			default: 'news',
			validator: value => {
				return ['news', 'notice'].includes(value);
			},
		},
		title: {
			type: String,
			required: true,
		},
		contents: {
			type: String,
			//required: true,
		},
		isLike: {
			type: Boolean,
			default: false,
		},
		obj: {
			type: Object,
			default: function () {
				return {};
			},
		},
	},
	setup(props) {
		// console.log('props.title : ', props.title)
		const isLikeClass = computed(() => {
			return props.isLike ? 'btn-danger' : 'btn-outline-danger';
		});
		const typeName = computed(() => {
			return props.type === 'news' ? '뉴스' : '공지사항';
		});
		const toggleLike = () => {
			return (props.isLike = !props.isLike);
		};
		return { isLikeClass, typeName, toggleLike };
	},
};
</script>

<!-- <style scoped>
 .red{
  color: red !important;
 }
</style> -->
<style module>
.red {
	color: red !important;
}
</style>

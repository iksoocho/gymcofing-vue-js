<template>
	<div>
		<div id="modifiers">
			<div @click="clickDiv">
				div 영역
				<p @click.self="clickP">
					p 영역
					<!-- <span @click.stop="clickSpan"> span 영역 </span> -->
					<span @click="clickSpan"> span 영역 </span>
				</p>
			</div>
		</div>
		<a href="https://naver.com" @click.prevent="clickA">a 영역</a>
		<button @click.once="clickDiv">once</button>
	</div>
</template>

<script>
export default {
	setup() {
		const clickDiv = () => {
			console.log('clickDiv');
			//location.href = 'https://naver.com';
		};
		const clickP = () => {
			console.log('clickP');
		};
		const clickSpan = () => {
			console.log('clickSpan');
			//e.stopPropagation();
			//alert('좋아요');
		};
		const clickA = e => {
			//e.preventDefault();
			alert('어떤기능~~');
		};
		return { clickDiv, clickP, clickSpan, clickA };
	},
};
</script>

<style scoped>
#modifiers div,
#modifiers p,
#modifiers span {
	padding: 40px;
}
#modifiers div {
	background-color: aliceblue;
}
#modifiers p {
	background-color: rgb(179, 177, 177);
}
#modifiers span {
	background-color: rgb(131, 131, 131);
	display: block;
}
</style>

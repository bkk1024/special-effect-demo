<!-- 按钮hover翻转 -->
<template>
	<div class="flip-hover-btn">
		<div class="btn1">按钮1</div>
		<div class="btn2">按钮2</div>
	</div>
</template>

<script setup>
	defineOptions({
		name: "flip-hover-btn",
	})
</script>

<style lang="less" scoped>
	.flip-hover-btn {
		display: inline-block;
		position: relative;
		width: 130px;
		height: 40px;
		perspective: 1500px;
		user-select: none;
		cursor: pointer;

		div[class^="btn"] {
			position: absolute;
			display: flex;
			align-items: center;
			justify-content: center;
			width: 130px;
			height: 40px;
			transition: all 0.3s;
		}

		.btn1 {
			transform: rotateX(-90deg);
			transform-origin: 50% 50% -20px;
			background-color: pink;
		}

		.btn2 {
			transform: rotateX(0deg);
			transform-origin: 50% 50% -20px;
			background-color: skyblue;
		}

		&:hover .btn1 {
			transform: rotateX(0deg);
		}

		&:hover .btn2 {
			transform: rotateX(90deg);
		}
	}
</style>

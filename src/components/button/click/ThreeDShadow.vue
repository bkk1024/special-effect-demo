<template>
	<div class="three-d-shadow">点&nbsp;&nbsp;击</div>
</template>

<script setup>
	defineOptions({
		name: "three-d-shadow",
	})
</script>

<style lang="less" scoped>
	.three-d-shadow {
		width: 100px;
		height: 50px;
		border-radius: 10px;
		box-shadow: 0px 15px 0px 0px #f39c12;
		text-align: center;
		line-height: 50px;
		color: #fff;
		font-size: 20px;
		text-shadow: -2px 2px 2px rgb(209 132 0), -2px 2px 2px rgb(209 132 0), -2px 2px 2px rgb(209 132 0), -2px 2px 2px rgb(209 132 0), -2px 2px 2px rgb(209 132 0), -2px 2px 2px rgb(209 132 0);
		background-color: #f1c40f;
		user-select: none;
		cursor: pointer;
		transition: all 0.2s;

		&:hover {
			background-color: #fcdc5e;
		}

		&:active {
			transform: translate(0, 4px);
			box-shadow: 0px 0px 0px 0px #f39c12;
		}
	}
</style>

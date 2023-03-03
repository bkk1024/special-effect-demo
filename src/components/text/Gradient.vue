<template>
	<div class="text-gradient">
		<slot></slot>
	</div>
</template>

<script setup>
	defineOptions({
		name: "text-gradient",
	})
</script>

<style lang="less" scoped>
	.text-gradient {
		font-size: 20px;
		font-weight: 700;
		color: transparent;
		background: linear-gradient(135deg, #fce38a, #f38181);
		// 背景被裁剪到文字
		-webkit-background-clip: text;
		// 设置文字的填充色
		-webkit-text-fill-color: transparent;
	}
</style>

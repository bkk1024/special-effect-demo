<template>
	<div class="text-piercing">
		<slot></slot>
	</div>
</template>

<script setup>
	defineOptions({
		name: "text-piercing",
	})
</script>

<style lang="less" scoped>
	.text-piercing {
		font-family: "华文彩云";
		font-size: 20px;
		font-weight: 700;
		color: transparent;
		-webkit-text-stroke: 1px pink;
		// 设置文字的填充色
		-webkit-text-fill-color: transparent;
	}
</style>

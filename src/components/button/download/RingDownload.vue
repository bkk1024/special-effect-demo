<template>
	<div class="ring-download">
		<span>{{ showProgress }}</span>
	</div>
</template>

<script setup>
	defineOptions({
		name: "ring-download",
	})

	const props = defineProps({
		progress: {
			type: Number,
			default: 0,
		},
	})

	const showProgress = computed(() => `${props.progress * 100}%`)
</script>

<style lang="less" scoped>
	.ring-download {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 70px;
		height: 70px;
		border-radius: 50%;
		// 锥形渐变
		background-image: conic-gradient(#2ecc71 0%, #2ecc71 v-bind(showProgress), #eee v-bind(showProgress));

		span {
			display: flex;
			align-items: center;
			justify-content: center;
			width: 50px;
			height: 50px;
			border-radius: 50%;
			background-color: #fff;
		}
	}
</style>

<!-- 水波下载按钮 -->
<template>
	<div class="water-download">
		<span class="ptAbs Center">
			<!-- <svg-icon name="complete" :size="20" /> -->
			{{ `${trueProgress * 100}%` }}
		</span>
	</div>
</template>

<script setup>
	defineOptions({
		name: "water-download",
	})

	const props = defineProps({
		// 这是真实的进度
		trueProgress: {
			type: Number,
			default: 0,
		},
	})

	// 这是在按钮上展示的样式的进度，因为使用top进行展示，因此需要用 1 减去
	const showProgress = computed(() => `${(1 - props.trueProgress) * 100}%`)
</script>

<style lang="less" scoped>
	@btnWidth: 100px;
	@btnHeight: 50px;
	@circleSize: 200px;
	.water-download {
		position: relative;
		display: inline-block;
		width: @btnWidth;
		height: @btnHeight;
		border-radius: 25px;
		background-color: #2980b9;
		cursor: pointer;
		user-select: none;
		overflow: hidden;

		span {
			display: flex;
			align-items: center;
			justify-content: center;
			font-size: 20px;
			color: #fff;
			z-index: 1;
		}

		&::before,
		&::after {
			position: absolute;
			top: v-bind(showProgress);
			content: "";
			display: inline-block;
			width: @circleSize;
			height: @circleSize;
			border-radius: 42%;
			transform: translateX(-(@circleSize - @btnWidth) * 0.5) rotate(45deg);
			background-color: #4cd137;
			animation: rotate 10s linear infinite;
		}

		&::after {
			border-radius: 45%;
			background-color: #44bd32;
			animation: rotate 11s linear infinite;
		}

		@keyframes rotate {
			0% {
				transform: translateX(-(@circleSize - @btnWidth) * 0.5) rotate(0);
			}
			50% {
				transform: translateX(-(@circleSize - @btnWidth) * 0.5) rotate(180deg);
			}
			100% {
				transform: translateX(-(@circleSize - @btnWidth) * 0.5) rotate(360deg);
			}
		}
	}
</style>

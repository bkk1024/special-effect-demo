<!-- 输入验证码 demo -->
<template>
	<div class="home">
		<h2>一些特殊效果</h2>
		<div class="demo-content">
			<!-- 验证码输入 -->
			<span>
				<h3>验证码输入</h3>
				<veri-input :size="4" />
			</span>
			<!-- 水波下载按钮 -->
			<span>
				<h3>水波下载按钮</h3>
				<water-download :trueProgress="0.25" />
			</span>
			<!-- 翻转hover按钮 -->
			<span>
				<h3>翻转hover按钮</h3>
				<flip-hover-btn />
			</span>
			<!-- 画线hover按钮 -->
			<span>
				<h3>画线hover按钮</h3>
				<line-hover-btn />
			</span>
			<!-- 环形下载进度 -->
			<span>
				<h3>环形下载进度</h3>
				<ring-download :progress="0.3" />
			</span>
			<!-- 波浪hover按钮 -->
			<span>
				<h3>波浪hover按钮</h3>
				<waves-hover-btn />
			</span>
			<!-- 文本渐变 -->
			<span>
				<h3>文本渐变</h3>
				<text-gradient>文本渐变</text-gradient>
			</span>
			<!-- 镂空文本 -->
			<span>
				<h3>镂空文本</h3>
				<text-piercing>镂空文本</text-piercing>
			</span>
			<!-- 立体阴影效果 -->
			<span>
				<h3>立体阴影效果</h3>
				<three-d-shadow />
			</span>
			<!-- 故障风文本 -->
			<span style="background: #000">
				<h3 style="color: #fff">故障风文本</h3>
				<text-fault></text-fault>
			</span>
			<!-- 环形导航 -->
			<span>
				<h3>环形导航</h3>
				<nav-circle />
			</span>
		</div>
	</div>
</template>

<script setup>
	import VeriInput from "@/components/input/VeriInput.vue"
	import WaterDownload from "@/components/button/download/WaterDownload.vue"
	import FlipHoverBtn from "@/components/button/hover/FlipHoverBtn.vue"
	import LineHoverBtn from "@/components/button/hover/LineHoverBtn.vue"
	import RingDownload from "@/components/button/download/RingDownload.vue"
	import WavesHoverBtn from "@/components/button/hover/WavesHoverBtn.vue"
	import TextGradient from "@/components/text/Gradient.vue"
	import TextPiercing from "@/components/text/Piercing.vue"
	import ThreeDShadow from "@/components/button/click/ThreeDShadow.vue"
	import TextFault from "@/components/text/Fault.vue"
	import NavCircle from "@/components/nav/Circle.vue"

	defineOptions({
		name: "home",
	})
</script>

<style lang="less" scoped>
	.home {
		width: 100%;

		h2 {
			padding: 20px 0;
			text-align: center;
			color: #adb5bd;
			border-bottom: 1px solid #eee;
		}

		.demo-content {
			display: flex;
			flex-wrap: wrap;
			width: 100%;

			span {
				padding: 0 20px;

				h3 {
					margin: 20px 0;
				}
			}
		}
	}
</style>

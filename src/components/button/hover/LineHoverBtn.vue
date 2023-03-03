<!-- 按钮hover翻转 -->
<template>
	<div class="line-hover-btn">
		<span>按钮</span>
	</div>
</template>

<script setup></script>

<style lang="less" scoped>
	.line-hover-btn {
		position: relative;
		display: inline-block;
		width: 130px;
		height: 40px;
		background-color: pink;
		cursor: pointer;
		user-select: none;
		overflow: hidden;

		&::before {
			content: "";
			position: absolute;
			top: 0;
			left: 0;
			width: 0;
			height: 2px;
			background-color: #eb4d4b;
			transition: all 0.2s linear;
		}

		&::after {
			content: "";
			position: absolute;
			bottom: 0;
			right: 0;
			width: 0;
			height: 2px;
			background-color: #eb4d4b;
			transition: all 0.2s linear;
		}

		span {
			position: absolute;
			display: flex;
			align-items: center;
			justify-content: center;
			width: 100%;
			height: 100%;

			&::before {
				content: "";
				position: absolute;
				left: 0;
				top: 0;
				// bottom: 0;
				width: 2px;
				height: 0;
				transition: all 0.2s linear;
				background-color: #eb4d4b;
			}

			&::after {
				content: "";
				position: absolute;
				right: 0;
				bottom: 0;
				// top: 0;
				width: 2px;
				height: 0;
				transition: all 0.2s linear;
				background-color: #eb4d4b;
			}
		}

		&:hover::before {
			width: 100%;
		}
		&:hover::after {
			width: 100%;
		}
		&:hover span::before {
			height: 100%;
		}
		&:hover span::after {
			height: 100%;
		}
	}
</style>

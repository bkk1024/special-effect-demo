<template>
	<div class="waves-hover-btn"></div>
</template>

<script setup>
	defineOptions({
		name: "waves-hover-btn",
	})
</script>

<style lang="less" scoped>
	.waves-hover-btn {
		position: relative;
		display: flex;
		width: 70px;
		height: 70px;
		border-radius: 50%;
		cursor: pointer;
		user-select: none;
		background-color: gray;

		&::before,
		&::after {
			content: "";
			position: absolute;
			z-index: -1;
			top: 0;
			bottom: 0;
			left: 0;
			right: 0;
			margin: auto;
			width: 100%;
			height: 100%;
			border-radius: 50%;
			box-shadow: 0px 0px 5px #b2bfc3, inset 0px 0px 5px #b2bfc3;
			filter: blur(1px);
		}

		&:hover::before {
			animation: waves 2s linear infinite;
		}

		&:hover::after {
			animation: waves 2s linear 1s infinite;
		}

		@keyframes waves {
			0% {
				opacity: 1;
				transform: scale(1);
			}
			50% {
				opacity: 1;
			}
			100% {
				opacity: 0;
				transform: scale(2);
			}
		}
	}
</style>

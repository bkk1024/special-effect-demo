<template>
	<div class="nav-circle">
		<div class="menu ptAbs" @mouseenter="setNavOne" @mouseleave="offNavOne">菜单</div>
		<div class="nav-one ptAbs" :class="{ 'show-nav-one': showNavOne }">
			<span class="nav-item item1" @mouseenter="setNavOneAndSec" @mouseleave="offNavOneAndSec">
				<span>1</span>
			</span>
			<span class="nav-item item2" @mouseenter="setNavOneAndSec" @mouseleave="offNavOneAndSec">
				<span>2</span>
			</span>
			<span class="nav-item item3" @mouseenter="setNavOneAndSec" @mouseleave="offNavOneAndSec">
				<span>3</span>
			</span>
		</div>
		<div class="nav-sec ptAbs" :class="{ 'show-nav-sec1': showNavOne, 'show-nav-sec2': showNavSec }" @mouseenter="setNavOneAndSec" @mouseleave="offNavOneAndSec"></div>
	</div>
</template>

<script setup>
	defineOptions({
		name: "nav-circle",
	})

	const showNavOne = ref(false)
	const showNavSec = ref(false)

	const setNavOne = () => {
		showNavOne.value = true
	}
	const offNavOne = () => {
		showNavOne.value = false
	}
	const setNavOneAndSec = () => {
		showNavOne.value = true
		showNavSec.value = true
	}
	const offNavOneAndSec = () => {
		showNavOne.value = false
		showNavSec.value = false
	}
</script>

<style lang="less" scoped>
	.nav-circle {
		// display: flex;
		// align-items: center;
		// justify-content: center;
		position: relative;
		width: 105px;
		height: 105px;
		background-color: #000;
		overflow: hidden;

		.menu {
			z-index: 3;
			left: -35px;
			top: -35px;
			width: 70px;
			height: 70px;
			border-radius: 50%;
			text-align: center;
			line-height: 70px;
			background-color: #ddd;
			user-select: none;
			cursor: pointer;
		}

		.nav-one {
			z-index: 2;
			left: -70px;
			top: -70px;
			width: 140px;
			height: 140px;
			border-radius: 50%;
			text-align: center;
			background-color: #bbb;
			transform: scale(0.5);
			user-select: none;
			cursor: pointer;
			overflow: hidden;
			transition: all 0.3s linear;

			.nav-item {
				position: absolute;
				display: inline-block;
				width: 50%;
				height: 50%;
				transform-origin: 0 100%;

				span {
					position: absolute;
					left: 20px;
					bottom: 0;
					transform: skewX(60deg);
				}
			}

			.item1 {
				transform: rotate(30deg) skewX(-60deg);
				background-color: blanchedalmond;
			}
			.item2 {
				transform: rotate(60deg) skewX(-60deg);
				background-color: pink;
			}
			.item3 {
				transform: rotate(90deg) skewX(-60deg);
				background-color: skyblue;
			}
		}

		.show-nav-one {
			transform: scale(1);
		}

		.nav-sec {
			z-index: 1;
			left: -105px;
			top: -105px;
			width: 210px;
			height: 210px;
			border-radius: 50%;
			text-align: center;
			background-color: #999;
			transform: scale(0.33);
			cursor: pointer;
			overflow: hidden;
			transition: all 0.3s linear;
		}

		.show-nav-sec1 {
			transform: scale(0.66);
		}
		.show-nav-sec2 {
			transform: scale(1);
		}
	}

	.ptAbs {
		position: absolute;
	}

	.Center {
		top: 0;
		bottom: 0;
		left: 0;
		right: 0;
		margin: auto;
	}
</style>

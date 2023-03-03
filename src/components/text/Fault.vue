<template>
	<div class="text-fault" data-text="故障风文本">故障风文本</div>
</template>

<script setup>
	defineOptions({
		name: "text-fault",
	})
</script>

<style lang="less" scoped>
	.text-fault {
		display: inline-block;
		font-size: 3.5em;
		font-weight: 600;
		padding: 0 4px;
		color: white;
		position: relative;

		&::before {
			content: attr(data-text);
			position: absolute;
			left: -2px;
			width: 100%;
			background: black;
			text-shadow: 2px 0 red;
			animation: animation-before 3s infinite linear alternate-reverse;
		}

		&::after {
			content: attr(data-text);
			position: absolute;
			left: 2px;
			width: 100%;
			background: black;
			text-shadow: -2px 0 blue;
			animation: animation-after 3s infinite linear alternate-reverse;
		}
	}

	@keyframes animation-before {
		0% {
			clip-path: inset(0 0 0 0);
		}

		5% {
			clip-path: inset(0.8em 0 0.4em 0);
		}

		10% {
			clip-path: inset(0.4em 0 0.8em 0);
		}

		15% {
			clip-path: inset(0.1em 0 1em 0);
		}

		20% {
			clip-path: inset(0.3em 0 0.6em 0);
		}

		25% {
			clip-path: inset(0.6em 0 0.3em 0);
		}

		30% {
			clip-path: inset(0.8em 0 0.5em 0);
		}

		35% {
			clip-path: inset(1em 0 0.1em 0);
		}

		40% {
			clip-path: inset(0.7em 0 0.35em 0);
		}

		45% {
			clip-path: inset(0.5em 0 0.2em 0);
		}

		50% {
			clip-path: inset(0.2em 0 0.5em 0);
		}

		55% {
			clip-path: inset(0.35em 0 0.7em 0);
		}

		60% {
			clip-path: inset(0.1em 0 0.9em 0);
		}

		65% {
			clip-path: inset(0.8em 0 0.46em 0);
		}

		70% {
			clip-path: inset(0.66em 0 0.33em 0);
		}

		75% {
			clip-path: inset(0.48em 0 0.23em 0);
		}

		80% {
			clip-path: inset(0.23em 0 0.48em 0);
		}

		85% {
			clip-path: inset(0.39em 0 0.79em 0);
		}

		90% {
			clip-path: inset(0.33em 0 0.66em 0);
		}

		95% {
			clip-path: inset(1em 0 0.3em 0);
		}

		100% {
			clip-path: inset(0.62em 0 0.29em 0);
		}
	}

	@keyframes animation-after {
		0% {
			clip-path: inset(0 0 0 0);
		}

		5% {
			clip-path: inset(0.4em 0 0.8em 0);
		}

		10% {
			clip-path: inset(0.8em 0 0.4em 0);
		}

		15% {
			clip-path: inset(1em 0 0.1em 0);
		}

		20% {
			clip-path: inset(0.6em 0 0.3em 0);
		}

		25% {
			clip-path: inset(0.3em 0 0.6em 0);
		}

		30% {
			clip-path: inset(0.5em 0 0.8em 0);
		}

		35% {
			clip-path: inset(0.1em 0 1em 0);
		}

		40% {
			clip-path: inset(0.35em 0 0.7em 0);
		}

		45% {
			clip-path: inset(0.2em 0 0.5em 0);
		}

		50% {
			clip-path: inset(0.5em 0 0.2em 0);
		}

		55% {
			clip-path: inset(0.7em 0 0.35em 0);
		}

		60% {
			clip-path: inset(0.9em 0 0.1em 0);
		}

		65% {
			clip-path: inset(0.46em 0 0.8em 0);
		}

		70% {
			clip-path: inset(0.3em 0 0.66em 0);
		}

		75% {
			clip-path: inset(0.23em 0 0.48em 0);
		}

		80% {
			clip-path: inset(0.48em 0 0.23em 0);
		}

		85% {
			clip-path: inset(0.79em 0 0.39em 0);
		}

		90% {
			clip-path: inset(0.66em 0 0.33em 0);
		}

		95% {
			clip-path: inset(0.3em 0 1em 0);
		}

		100% {
			clip-path: inset(0.29em 0 0.62em 0);
		}
	}
</style>

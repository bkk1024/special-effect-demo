<template>
	<div class="veri-input">
		<div class="real-input">
			<input type="text" ref="realInput" @input="input" v-focus />
		</div>
		<div class="fake-input" @click="fakeInput">
			<span v-for="(item, index) in size" :class="{ 'is-input': veri[index] }">
				{{ veri[index] }}
			</span>
		</div>
	</div>
</template>

<script setup>
	defineOptions({
		name: "veri-input",
	})

	const props = defineProps({
		size: {
			type: Number,
			default: 4,
		},
	})

	const realInput = ref(null)
	const veri = reactive([])

	// 真实输入框的输入事件
	const input = (e) => {
		if (e.inputType == "deleteContentBackward") {
			// 删除
			veri.pop()
			return false
		} else {
			// 输入
			const pattern = /[0-9]\d*/ // 只能输入数字
			if (pattern.test(e.data) && veri.length < props.size) {
				// 限制输入长度
				veri.push(e.data)
				return false
			}
		}
	}

	// 假输入框的点击事件
	const fakeInput = () => {
		nextTick(() => {
			realInput.value.focus()
		})
	}

	// 自定义指令，自动聚焦
	const vFocus = {
		mounted: (el) => el.focus(),
	}
</script>

<style lang="less" scoped>
	.veri-input {
		display: inline-block;
		overflow: hidden;

		.fake-input,
		.real-input {
			display: flex;
			align-items: center;
			justify-content: space-between;
			height: 40px;

			span {
				box-sizing: border-box;
				display: flex;
				align-items: center;
				justify-content: center;
				width: 40px;
				height: 40px;
				margin: 0 10px;
				font-size: 20px;
				border-radius: 7px;
				border: 1px solid #868e96;
				cursor: text;
				transition: all 0.3s linear;
			}

			.is-input {
				border: 1px solid #000;
				transition: all 0.3s linear;
			}
		}

		.real-input {
			width: 0;
			height: 0;
			opacity: 0;

			input {
				width: 0;
				height: 0;
			}
		}
	}
</style>

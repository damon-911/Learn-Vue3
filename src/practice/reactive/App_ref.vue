<template>
	<div>
		<p>{{ message }}</p>
		<button v-on:click="addDots">Click</button>
	</div>
</template>

<script>
import { reactive, ref } from 'vue';

export default {
	setup() {
		const count = ref(0);
		const state = reactive({
			count,
		});
		console.log(count.value);
		console.log(state.count);

		const text = ref('hello');
		const arr = reactive([text]);
		console.log(text.value);
		console.log(arr[0].value);

		const message = ref('Message');
		const addDots = () => {
			message.value += '.';
		};

		return {
			message,
			addDots,
		};
	},
};
</script>

<style lang="scss" scoped></style>

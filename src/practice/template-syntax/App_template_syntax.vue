<template>
	<div>
		<h2>텍스트 보간법</h2>
		<p>{{ message }}</p>
		<button v-on:click="message += '!'">Click!</button>
		<hr />
		<h2>HTML (v-html)</h2>
		<p v-html="rawHtml"></p>
		<hr />
		<h2>속성 바인딩 (v-bind)</h2>
		<div v-bind:title="dynamicTitle">마우스를 올려보세요.</div>
		<input type="text" value="입력" :disabled="isInputDisabled" />
		<input v-bind="attrs" />
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const message = ref('안녕하세요');
		const rawHtml = ref('<strong>안녕하세요</strong>');

		const dynamicTitle = ref('안녕하세요!!');
		const isInputDisabled = ref(true);
		const attrs = {
			id: 'password-id',
			type: 'password',
			placeholder: '비밀번호를 입력해주세요',
		};

		return {
			message,
			rawHtml,
			dynamicTitle,
			isInputDisabled,
			attrs,
		};
	},
};
</script>

<style lang="scss" scoped></style>

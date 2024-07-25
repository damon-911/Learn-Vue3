<template>
	<div class="text" :class="classObject">텍스트입니다.</div>
	<button v-on:click="toogle">toogle</button>
	<button v-on:click="hasError = !hasError">toogleError</button>
</template>

<script>
import { ref, computed } from 'vue';

export default {
	setup() {
		const isActive = ref(true);
		const hasError = ref(false);

		const toogle = () => {
			isActive.value = !isActive.value;
		};

		const classObject = computed(() => {
			return {
				active: isActive.value && !hasError.value,
				'text-danger': !isActive.value && hasError.value,
			};
		});

		return { isActive, toogle, hasError, classObject };
	},
};
</script>

<style scoped>
.active {
	font-weight: 900;
}
.text-danger {
	color: red;
}
</style>

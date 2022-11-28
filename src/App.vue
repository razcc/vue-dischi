<template>
	<div id="app">
		<HeaderComp
			:propsGeneri="arrGeneriApp"
			:propsAutori="arrAutoriApp"

		/>
		<MainComp
			@emitGeneriMain="methodsGeneriApp"
			@emitAutoriMain="methodsAutoriApp"
		/>
	</div>
</template>

<script>
import HeaderComp from "./components/HeaderComp.vue";
import MainComp from "./components/MainComp.vue";

export default {
	name: "App",
	data() {
		return {
			arrGeneriApp: [],
			arrAutoriApp: [],
		};
	},
	components: {
		HeaderComp,
		MainComp,
	},
	methods: {
		methodsGeneriApp(valEmitGeneriApp) {
			this.arrGeneriApp = valEmitGeneriApp;
		},
		methodsAutoriApp(valEmitAutoriApp) {
			this.arrAutoriApp = valEmitAutoriApp;
		},
	},
};
</script>

<style lang="scss">
* {
	box-sizing: border-box;
	margin: 0%;
	padding: 0;
}
#app {
	height: 100vh;
	display: flex;
	flex-direction: column;
}
</style>

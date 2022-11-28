<template>
	<div id="app">
		<HeaderComp />
		<MainComp />

	</div>
</template>

<script>


import HeaderComp from "./components/HeaderComp.vue";
import MainComp from "./components/MainComp.vue";


export default {
	name: "App",
	components: {
		HeaderComp,
    MainComp,
	},
};
</script>

<style lang="scss">
*{
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

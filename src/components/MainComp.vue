<template>
	<main>
		<AlbumsComp @emitGeneri="methodsGeneri" @emitAutori="methodsAutori" />
	</main>
</template>

<script>
import AlbumsComp from "./albums/AlbumsComp.vue";

export default {
	name: "MainComp",
	data() {
		return {
			arrGeneriMain: [],
			arrAutoriMain: [],
		};
	},
	components: {
		AlbumsComp,
	},
	methods: {
		methodsGeneri(valEmitGeneri) {
			this.arrGeneriMain = valEmitGeneri;
		},
		methodsAutori(valEmitAutori) {
			this.arrAutoriMain = valEmitAutori;
		},
	},
	mounted() {
		this.$emit("emitGeneriMain", this.arrGeneriMain);
        console.log(this.$emit("emitGeneriMain", this.arrGeneriMain))
		this.$emit("emitAutoriMain", this.arrAutoriMain);
	},
};
</script>

<style lang="scss" scoped>
main {
	background-color: rgba(30, 45, 59, 1);
	height: 90%;
	padding: 20px 0;
}
</style>
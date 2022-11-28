<template>
	<main>
		<AlbumsComp @emitGeneri="methodsGeneri" @emitAutori="methodsAutori" />
	</main>
</template>

<script>
import AlbumsComp from "./albums/AlbumsComp.vue";

export default {
	name: "MainComp",
	props: {
		propsSceltaGenere: String,
		propsSceltaAutore: String,
	},
	data() {
		return {
			arrGeneriMain: [],
			arrAutoriMain: [],
            sceltaGen: "",
            sceltaAutore: ""
            
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
		this.$emit("emitAutoriMain", this.arrAutoriMain);
       
       
        
	},
    updated(){
        this.sceltaGen = this.propsSceltaGenere;
        console.log(this.sceltaGen )

    }
};
</script>

<style lang="scss" scoped>
main {
	background-color: rgba(30, 45, 59, 1);
	height: 90%;
	padding: 20px 0;
}
</style>
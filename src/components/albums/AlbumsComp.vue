<template>
	<div class="container">
		<CardComp
			v-for="(element, index) in datiDischi"
			:key="index"
			:propsDischi="element"
		/>
	</div>
</template>

<script>
import CardComp from "./CardComp.vue";
import axios from "axios";

export default {
	name: "AlbumsComp",
	props: {
		props1Genere: String,
		props2Autore: String
	},
	components: {
		CardComp,
	},
	data() {
		return {
			datiDischi: "",
			arrGeneri: [],
			arrAutori: [],
		};
	},
	mounted() {
		axios
			.get("https://flynn.boolean.careers/exercises/api/array/music")
			.then((response) => {
				this.datiDischi = response.data.response;

				this.datiDischi.forEach((element) => {
					// Creazione array con generi
					if (!this.arrGeneri.includes(element.genre)) {
						this.arrGeneri.push(element.genre);
					}

					// Creazione array con autori
					if (!this.arrAutori.includes(element.author)) {
						this.arrAutori.push(element.author);
					}
				});
			});

            this.$emit('emitGeneri', this.arrGeneri)
            this.$emit('emitAutori', this.arrAutori)

	},
};
</script>

<style lang="scss" scoped>
.container {
	display: flex;
	flex-wrap: wrap;
	align-items: center;
	gap: 40px;
	width: 70%;
	height: 100%;
	margin: auto;
}
</style>
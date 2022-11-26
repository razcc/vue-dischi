<template>
	<main>
        <div class="container">
            <CardComp
			v-for="(element, index) in datiDischi"
			:key="index"
			:propsDischi="element"
		/>
        </div>
		
	</main>
</template>

<script>
import CardComp from "./CardComp.vue";
import axios from "axios";

export default {
    name: "MainComp",
    components: {
        CardComp,
    },
    data() {
		return {
			datiDischi: "",
		};
	},
    mounted() {
		axios
			.get("https://flynn.boolean.careers/exercises/api/array/music")
			.then((response) => {
				console.log(response.data.response);
				this.datiDischi = response.data.response;
				console.log(this.datiDischi);
			});
	},
};
</script>

<style lang="scss" scoped>
main{
    background-color: rgba(30, 45, 59, 1);
    height: 90%;
}
.container{
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 40px;
    width: 70%;
    height: 100%;
    margin: auto;
}
</style>
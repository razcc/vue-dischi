<template>
	<div class="card">
		<!-- Immagine -->
		<div class="copertina">
			<img :src="propsDischi.poster" alt="copertina disco" />
		</div>

		<!-- Titolo -->
		<div class="titoloDisco">
			<h2>{{ propsDischi.title }}</h2>
		</div>

		<!-- Attore -->
		<div class="autoreDisco">
			<span>{{ propsDischi.author }}</span>
		</div>

		<!-- Anno -->
		<div class="annoPubblicazione">
			<span>{{ propsDischi.year }}</span>
		</div>
	</div>
</template>

<script>
export default {
	name: "CardComp",
	components: {},
	props: {
		propsDischi: Object,
	},
};
</script>

<style lang="scss" scoped>
.card {
	width: calc(100% / 5 - 40px);
    height: calc(100% / 2 - 50px);
	display: flex;
	flex-direction: column;
	align-items: center;
	background-color: rgba(46, 58, 70, 1);
	padding: 10px 10px 100px 10px;
    text-align: center;
    color: rgba(125, 130, 125, 1);
}
.copertina {
	width: 80%;
    height: 100%;
    margin-bottom: 15px;
    display: flex;
    align-items: center;
   
	img {
		width: 100%;
	}
}
.titoloDisco{
    color: white;
    font-size: 20px;
    margin-bottom: 10px;
}
</style>
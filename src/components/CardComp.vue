<template>
	<div class="card">
        <!-- Immagine -->
        <div class="copertina">
            <img :src="propsDischi.poster" alt="copertina disco">
        </div>

        <!-- Titolo -->
        <div class="titoloDisco">
            <h2>{{propsDischi.title}}</h2>
        </div>
        
        <!-- Attore -->
        <div class="autoreDisco">
            <span>{{propsDischi.author}}</span>
        </div>

        <!-- Anno -->
        <div class="annoPubblicazione">
            <span>{{propsDischi.year}}</span>
        </div>
    </div>
</template>

<script>

    export default {
        name: 'CardComp',
        components: {

         },
         props: {
            propsDischi: Object
         }
        
    }
</script>

<style lang="scss" scoped>
.card{
    width: calc(100% / 5 - 20px);
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: rgba(46, 58, 70, 1);
    padding: 10px 10px 50px 10px;
}
.copertina{
    width: 80%;
}
img{
    width: 100%;
}
</style>
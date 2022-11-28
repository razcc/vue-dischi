<template>
	<header>
        <img src="../assets/SptifyLogo.png" alt="Logo">
        <div>
            <!-- Selezione per Genere -->
            <select name="genere" id="selezioneGenere">
                <option value="">Seleziona il genere preferito</option>
                <option v-for="(elem, index) in propsGeneri"  :key="index" :value="elem">{{elem}}</option>
            </select>

            <!-- Selezione per autore -->
            <select name="autore" id="selezioneAutore">
                <option value="">Seleziona l'autore</option>
                <option v-for="(elem, index) in propsAutori"  :key="index" value="elem">{{elem}}</option>
            </select>
        </div>
    </header>
</template>

<script>

    export default {
        name: 'HeaderComp',
        data(){

        },
        props: {
            propsGeneri: Array,
            propsAutori: Array
        }       
    }
</script>

<style lang="scss" scoped>
    header{
        width: 100%;
        height: 10%;
        background-color: rgba(46, 58, 70, 1);
        padding: 20px;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    img{
        height: 100%
    }
    select{
        padding: 10px 25px;
        font-size: 20px;
        margin-right: 20px;
        background-color: lightblue;
        border: none;
        border-radius: 10px;
    }
</style>
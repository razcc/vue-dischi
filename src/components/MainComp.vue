<template>
	<main>
        <AlbumsComp />
    </main>
</template>

<script>
import AlbumsComp from "./albums/AlbumsComp.vue";



export default {
	name: "MainComp",
	components: {
        AlbumsComp,
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
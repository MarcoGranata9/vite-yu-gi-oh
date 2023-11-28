<script>
import {store} from "../store";
export default {
    data() {
        return {
            store,
        };
    },
}
</script>

<template>
    <p>Carte visualizzate: {{ store.cards.length }}</p>
</template>

<style scoped>
p{
    text-align: end;
}
</style>
<script>
import AppCard from "./AppCard.vue"
import {store} from "../store"
export default {
    data() {
        return {
            store,
        }
    },
    components: {AppCard,}
}
</script>

<template>
<div class="container">
    <div class="row">
        <div class="col" v-for="card in store.cards">
            <AppCard :card="card"/>
        </div>
    </div>
</div>
</template>

<style scoped lang="scss">
.container{
    width: 80%;
    margin: auto;
    .row {
        display: flex;
        justify-content: start;
        align-items: start;
        flex-wrap: wrap;
    
        .col{
            width: calc(100% / 5);
            text-align: center;
            padding: 10px
        }
    }
}
</style>
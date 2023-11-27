<script>
import axios from "axios"
import {store} from "./store.js"
import AppHeader from "./components/AppHeader.vue"
import AppMain from "./components/AppMain.vue"
import AppLoader from "./components/AppLoader.vue"
 
export default {
    data() {
        return {
            store,
        }
    },
    created() {
        this.store.loading = true;
        axios.get(this.store.apiUrl).then((resp) => {
            this.store.cards = resp.data.data;
            this.store.loading = false;
        })
    },
    components: {
        AppHeader,
        AppMain,
        AppLoader,
    },
}
</script>

<template>
<AppHeader/>
<AppLoader v-if="store.loading"/>
<AppMain v-else/>
</template>

<style lang="scss">
@use "./style/general.scss";

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: sans-serif
}

</style>

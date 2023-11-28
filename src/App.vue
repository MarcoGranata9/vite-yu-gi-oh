<script>
import axios from "axios"
import {store} from "./store.js"
import AppHeader from "./components/AppHeader.vue"
import AppMain from "./components/AppMain.vue"
import AppLoader from "./components/AppLoader.vue"
import AppSearch from "./components/AppSearch.vue"
 
export default {
    data() {
        return {
            store,
        }
    },
    created() {
        this.store.loading = true;
        axios.get(this.store.apiUrl).then((resp) => {
            console.log(resp)
            this.store.cards = resp.data.data;
            this.store.loading = false;
        })
    },
    components: {
    AppHeader,
    AppMain,
    AppLoader,
    AppSearch
    },
    methods: {
        handleArchetype() {
            console.log("selezionato");
            console.log(store.select);
            if (store.select === "alien") {
                axios.get(this.store.apiUrl, {
                    params: {
                        num: 20,
                        offset: 0,
                        archetype: "Alien"
                    }
                })
                .then((resp) => {
                console.log(resp)
                this.store.cards = resp.data.data;
                })
            } else if (store.select === "ally") {
                axios.get(this.store.apiUrl, {
                    params: {
                        num: 20,
                        offset: 0,
                        archetype: "Ally of Justice"
                    }
                })
                .then((resp) => {
                console.log(resp)
                this.store.cards = resp.data.data;
                })
            } else if (store.select === "ancient"){
                axios.get(this.store.apiUrl, {
                    params: {
                        num: 20,
                        offset: 0,
                        archetype: "Ancient Gear"
                    }
                })
                .then((resp) => {
                console.log(resp)
                this.store.cards = resp.data.data;
                })
            } else {
                axios.get(this.store.apiUrl, {
                    params: {
                        num: 20,
                        offset: 0,
                    }
                })
                .then((resp) => {
                console.log(resp)
                this.store.cards = resp.data.data;
                })
            }
        }
    }
}
</script>

<template>
<AppHeader/>
<AppSearch @selectedArchetype="handleArchetype"/>
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

img {
    max-width: 100%;
}

body {
    font-family: sans-serif
}

</style>

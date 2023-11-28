<script>
import {store} from "../store"

export default {
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <div class="container">
        <label for="archetype">Scegli un Archetipo</label>
        <select name="archetype" id="archetype" v-model="store.select" @change="$emit('selectedArchetype')">
            <option value="">Scegli</option>
            <option value="alien">Alien</option>
            <option value="ally">Ally of Justice</option>
            <option value="ancient">Ancient Gear</option>
        </select>
    </div>
</template>

<style lang="scss">
    .container {
        width: 85%;
        margin: 0 auto;
    }
</style>
<script>
export default {
  props: {
    card: Object,
  },
};
</script>

<template>
<div class="card">
  <img :src="card.card_images[0].image_url" alt="">
  <h3>{{ card.name }}</h3>
  <p>{{ card.archetype }}</p>

</div>
</template>

<style scoped lang="scss">
.card{
  background-color: #d48f38;
    img {
    width: 200px;
  }
}

</style>
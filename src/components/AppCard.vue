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
  <div class="card-text">
     <h3>{{ card.name }}</h3>
      <p>{{ card.archetype }}</p>
  </div>
 

</div>
</template>

<style scoped lang="scss">
.card{


    img {
    width: 200px;
    display: block;
  }

  .card-text {
    background-color: #d48f38;
    max-width: 200px;
    min-height: 100px;
  }
}

</style>
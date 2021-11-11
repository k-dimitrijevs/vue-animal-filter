<template>
  <div class="animalCard">
    <div class="image">
      <img :src="animal.img" :alt="animal.name" />
    </div>
    <div class="content">
      <h2>{{ animal.name }}</h2>
    </div>
  </div>
</template>

<script>

export default {
  name: "AnimalCard",
  props: {
    animal: Object
  },
}
</script>

<style scoped>
  .animalCard {
    position: relative;
    border: 1px solid black;
    border-radius: 5px;
    background: #2c3e50;
    color: aliceblue;
    padding-bottom: 50px;
    margin: 30px;
    width: 400px;
    height: 410px;
  }

  .image {
    position: absolute;
    top: 0;
    left: 0;
    float: top;
  }

  .content {
    position: absolute;
    float: bottom;
    bottom: 100px;
    left: 150px;
    text-align: center;
  }
</style>
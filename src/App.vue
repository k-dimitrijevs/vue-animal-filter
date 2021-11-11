<template>
  <div>
    <Heading />
    <div class="buttonFilters">
      <Button v-for="item in buttonItems" :item="item.filter" :key="item.filter" :onClick="() => FilterAnimals(item.filter)" />
    </div>
    <div v-for="animal in animals" :key="animal.id" class="animalCards">
      <AnimalCard :hidden="!animal.visible" :animal="animal"/>
    </div>
  </div>
</template>

<script>
import Heading from "@/components/Heading";
import AnimalCard from "@/components/AnimalCard";
import Button from "@/components/Button";

export default {
  name: 'App',
  components: {
    Button,
    AnimalCard,
    Heading,
  },
  data: () => ({
    animals: [
      {
        "id": 1,
        "img": "https://picsum.photos/id/659/400/250",
        "type": "Dog",
        "name": "Reksis",
        "visible": true
      },
      {
        "id": 2,
        "img": "https://picsum.photos/id/1074/400/250",
        "type": "Cat",
        "name": "Muris",
        "visible": true
      },
      {
        "id": 3,
        "img": "https://picsum.photos/id/1024/400/250",
        "type": "Parrot",
        "name": "Ozijs",
        "visible": true
      },
      {
        "id": 1,
        "img": "https://picsum.photos/id/237/400/250",
        "type": "Dog",
        "name": "Mailo",
        "visible": true
      },
      {
        "id": 1,
        "img": "https://picsum.photos/id/837/400/250",
        "type": "Dog",
        "name": "Koko",
        "visible": true
      },
      {
        "id": 1,
        "img": "https://placekitten.com/400/250",
        "type": "Cat",
        "name": "Pūka",
        "visible": true
      },
    ],
    buttonItems: [{
        filter: "All"
      },
      {
        filter: "Dog"
      },
      {
        filter: "Cat"
      },
      {
        filter: "Parrot"
      }],
  }),
  methods: {
    FilterAnimals: function (filter) {
      this.animals.forEach(function (animal) {
        if (animal.type == filter) {
          animal.visible = true
        } else {
          animal.visible = false
        }

        if (filter == "All") animal.visible = true;
      })
    },
    ConsoleTest() {
      console.log(123)
    }
  }
}
</script>

<style>
* {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}

.animalCards {
  display: inline-block;
  justify-content: center;
  align-items: center;
}
</style>

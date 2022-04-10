<template>

  <table>
    <thead>
      <tr>
        <th>Photo</th>
        <th>Nom de la race</th>
        <th>Détails</th>
      </tr>
    </thead>
    <tbody>
      <!-- V-for for dogsList on tr below-->
      <tr v-for="dog in dogs" :key="dog.id_dog">
        <td> <img :src ="dog.photo"></td>
        <td>{{ dog.race }}</td>
        <!-- @click button go to dogCard component for details-->
        <td>
          <button @click="checkThisDog(dog.id_dog)">En savoir plus</button>
        </td>
          <td>
          <button @click="editThisDog(dog.id_dog)">Edit</button>
        </td>
         <td>
          <button @click="deleteThisDog(dog.id_dog)">delete</button>
        </td>
      </tr>
    </tbody>
  </table>
</template>


<script>
import axios from "axios";

export default {
  name: "dogsList",

  data: () => ({
    dogs: [],
  }),
  methods: {
    checkThisDog(dogsId) {
      this.$router.push({ name: "dogCard",params:{ cardId: dogsId } });
      console.log("test");
    },
    editThisDog(dogsId){
      this.$router.push({name:"updateDog", params:{ id_dog:dogsId}})
    },
    deleteThisDog(dogsId){
      this.$router.push({name:"deleteDog", params:{ id_dog:dogsId}})
    },
  },

  async created() {
    const dogs = await axios.get("http://localhost:8000/api/read.php");
    this.dogs = dogs.data;
    console.log(this.dogs);
  },
};
</script>

<style>
</style>
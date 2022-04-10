<template>
  <form @submit.prevent="submitDog" action="#">
    <div class="row gtr-uniform">
      <div class="col-12">
        <input
          v-model="dog.race"
          type="text"
          name="race"
          id="name"
          placeholder="Nom de la race"
        />
      </div>
      <div class="col-12">
        <select v-model="dog.type_de_poil">
          <!-- Link of angle-down for VueJS <font-awesome-icon icon="fa-solid fa-angle-down" /> -->
          <option value="type_de_poil" selected="true" disabled>
            Type de poil
          </option>
          <option value="Soyeux">Soyeux</option>
          <option value="Court">Court</option>
          <option value="Long">Long</option>
          <option value="Long ou court">Long ou court</option>
          <option value="Dur">Dur</option>
          <option value="Autre">Autre</option>
        </select>
      </div>
      <div class="col-12">
        <select v-model="dog.gabarit">
          <option value="gabarit" selected="true" disabled>Gabarit</option>
          <option value="Toy">Toy (&lsaquo;2kg)</option>
          <option value="Petit">Petit (&rsaquo;3kg à &lsaquo;10kg)</option>
          <option value="Moyen">Moyen (&rsaquo;10kg à &lsaquo;23kg)</option>
          <option value="Grand">Grand (&rsaquo;23kg à &lsaquo;55kg)</option>
          <option value="Géant">Géant (&rsaquo;55kg)</option>
        </select>
      </div>
      <div class="col-12">
        <select v-model="dog.origine">
          <option value="origine" selected="true" disabled>Origine</option>
          <option value="Europe">Europe</option>
          <option value="Asie">Asie</option>
          <option value="Afrique">Afrique</option>
          <option value="Océanie">Océanie</option>
          <option value="Amérique du Nord">Amérique du Nord</option>
          <option value="Amérique du Sud">Amérique du Sud</option>
        </select>
      </div>

      <div class="col-12">
        <textarea
          name="message"
          id="message"
          placeholder="Caractère"
          rows="6"
          v-model="dog.caractere"
        ></textarea>
      </div>
      <div class="col-12">
        <input type="text" placeholder="put image link" v-model="dog.image" />
        <br />
        <br />
        <ul class="actions">
          <li>
            <input type="submit" class="primary" value="Ajouter une race" />
          </li>
          <li><input type="reset" value="Reset Form" /></li>
        </ul>
      </div>
    </div>
  </form>
</template>

<script>
import axios from "axios";
export default {
  name: "updateDog",
  data() {
    return {
      dog: {
        race: "",
        type_de_poil: "",
        gabarit: "",
        origine: "",
        caractere: "",
        image: "" 
      },
    };
  },
methods:{
  async submitDog() {
  
    const id_dog = this.$route.params;
    console.log(id_dog)
    console.log(this.dog);
    const updateApi ="http://localhost:8000/api/update.php/";
    await axios.put(updateApi,id_dog,this.dog)
        .then(function () {
       

    console.log('function works !')
        })
  },
  }
};
</script>

<style>
</style>
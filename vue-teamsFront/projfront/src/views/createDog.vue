<template>
  <form method="post"
  @submit="submitDog"
   action="#">
    <div class="row gtr-uniform">
      <div class="col-12">
        <input type="text" name="race" id="name" placeholder="Nom de la race" />
      </div>
      <div class="col-12">
        <select>
          <!-- Link of angle-down for VueJS <font-awesome-icon icon="fa-solid fa-angle-down" /> -->
          <option value="type_de_poil" selected="true" disabled>Type de poil</option>
          <option value="type_de_poil">Soyeux</option>
          <option value="type_de_poil">Court</option>
          <option value="type_de_poil">Long</option>
          <option value="type_de_poil">Long ou court</option>
          <option value="type_de_poil">Dur</option>
          <option value="type_de_poil">Autre</option>
        </select>
      </div>
      <div class="col-12">
        <select>
          <option value="gabarit" selected="true" disabled>Gabarit</option>
          <option value="gabarit">Toy (&lsaquo;2kg)</option>
          <option value="gabarit">Petit (&rsaquo;3kg à &lsaquo;10kg)</option>
          <option value="gabarit">Moyen (&rsaquo;10kg à &lsaquo;23kg)</option>
          <option value="gabarit">Grand (&rsaquo;23kg à &lsaquo;55kg)</option>
          <option value="gabarit">Géant (&rsaquo;55kg)</option>
        </select>
      </div>
      <div class="col-12">
        <select>
          <option value="origine" selected="true" disabled>Origine</option>
          <option value="origine">Europe</option>
          <option value="origine">Asie</option>
          <option value="origine">Afrique</option>
          <option value="origine">Océanie</option>
          <option value="origine">Amérique du Nord</option>
          <option value="origine">Amérique du Sud</option>
        </select>
      </div>

      <div class="col-12">
        <textarea
          name="message"
          id="message"
          placeholder="Caractère"
          rows="6"
        ></textarea>
      </div>
      <div class="col-12">
        <input type="file" accept="image/*" @change="test" />
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
             <!-- <input type="file" accept="image/*" @change="test"> -->

<script>
export default {

};
</script>

<style>
@import "@/assets/css/main.css"

</style>
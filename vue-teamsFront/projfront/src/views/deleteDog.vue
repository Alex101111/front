<template>
  <h1>dog has been deleted</h1>
</template>

<script>
import axios from "axios";
export default {
  name: "deleteDog",

    async created() {
      const id_dog = this.$route.params;
      console.log(id_dog);
 
      const deleteApi =
        "http://localhost:8000/api/delete.php/"
      await axios.post(deleteApi,id_dog).then(function () {
        console.log("function works !");
      });
    },

};
</script>

<style>
</style>
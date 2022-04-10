<template>

		<div class="frame">
  <div class="center">
    
		<div class="profile">
			<div class="image">
				<div class="circle-1"></div>
				<div class="circle-2">	<img class='dogImage' :src="dog.photo"></div>
			
			</div>
			
			<div class="name">{{dog.race}}</div>
	
				<div class="box">
                    <br>
                    <br>
				<span class="value">{{dog.caractere}}</span>
              
			</div>
		</div>
		
		<div class="stats">
			<div class="box">
				<span class="value">type de poil</span>
				<span class="parameter">{{dog.type_de_poil}}</span>
			</div>
			<div class="box">
				<span class="value">gabarit</span>
				<span class="parameter">{{dog.gabarit}}</span>
			</div>
			<div class="box">
				<span class="value">origine</span>
				<span class="parameter">{{dog.origine}}</span>
			</div>
		</div>
  </div>

</div>
</template>

<script>
import axios from 'axios'
export default {
name:'dogCard',
data:()=>({
  dog:{}
}),
async created()
{
const {cardId} = this.$route.params
const apiDogs= "http://localhost:8000/api/single_read.php/?id_dog="+cardId
const oneDog = await axios.get(apiDogs)
this.dog = oneDog.data
console.log(oneDog)
}
}

</script>

<style>
@import "../assets/css/dogCard.css";
</style>
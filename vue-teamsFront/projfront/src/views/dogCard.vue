<template>

				<section class="first">
										<i class="icon solid featured fa-cog theimage"></i>
										<header>
											<h2>Ipsum consequat</h2>
										</header>
										<p>Nisl amet dolor sit ipsum veroeros sed blandit consequat veroeros et magna tempus.</p>
                                        <footer>
                                            <ul class="actions">
                                                <li><a href="#" class="button alt">Find out more</a></li>
                                                <li><a href="#" class="button alt">Find out more</a></li>

                                            </ul>
                                        </footer>
									</section>
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
const {cardId} =this.$route.parmas
const apiDogs= "http://localhost:8000/api/read.php"+cardId
const oneDog = await axios.get(apiDogs)
this.dog = oneDog.data

}
}

</script>

<style>

</style>
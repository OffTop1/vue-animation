<template>
	<div id="container">
		<div v-for="card in cards" :key="card.id" class="card"></div>
	</div>
</template>

<script>
import { gsap, TweenMax } from 'gsap';

export default {
	data(){
		return {
			cards: [
				{id:1},
				{id:2},
				{id:3},
				{id:4},
				{id:5},
				{id:6},
			]
		}
	},
	mounted(){
		TweenMax.staggerFrom('.card', 0.5, {opacity: 0, y:200, scale:0}, 0.1)
	}
}

</script>

<style scoped>
#container{
	display:flex;

}
	.card {
  height:12em;
  width: 12em;
  border-radius: 1%;
  background-color: teal;
  box-shadow: 0.08em 0.03em 0.4em #ababab;
  padding-top: 1em;
  margin:auto;
}
</style>
<template>
	<transition
	appear
	@before-enter="beforeEnter"
	@enter="enter"
	:css="false"
	>
		<div class="card"></div>
	</transition>
</template>


<script>

import { gsap, TweenMax } from 'gsap';

export default {
	methods: {
		beforeEnter(el){
			el.style.opacity = 0;
			el.style.transform = 'scale(0,0)'
		},
		enter(el, done){
			TweenMax.to(el, 1, {
				opacity:1,
				scale:1,
				onComplete: done
			})
		}
	}
}
</script>

<style scoped>
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
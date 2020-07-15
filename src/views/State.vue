<template>
	<div>
		<div :style="{width: tweenedNumber + 'px'}" class="bar">
			<span>{{tweenedNumber.toFixed(0)}}</span>
		</div>
	</div>
</template>

<script>
import gsap from "gsap";

export default {
	data(){
		return {
			number: 0,
			tweenedNumber: 0
		}
	},
	watch: {
		number(newValue){
			gsap.to(this.$data, {
				duration:1,
				ease:'circ.out',
				tweenedNumber: newValue
			})
		}
	}
	,
	methods: {
		randomNumber(){
			this.number = Math.floor(Math.random() * (800 - 0))
		}
	},
	created(){
		setInterval(this.randomNumber, 1500);
	}
}
</script>

<style>
.bar {
	padding:0.8em;
	background-color:#42b983;
	color:white
}
</style>
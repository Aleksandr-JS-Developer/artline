<template>
	<div class="laoder">
		<div id="loop" class="center"></div>
		<div id="bike-wrapper" class="center">
			<div id="bike" class="centerBike"></div>
		</div>
	</div>
</template>

<script>

export default {
	name: 'LoaderBike'
}

</script>

<style lang="scss" scoped>
	@import '@/assets/scss/vars.scss';
	
	.centerBike {
		position: absolute;
		top: 50%;
		left: 50%;
		margin-top: 26px;
		margin-left: -12px;
	}

	.center {
		position: absolute;
		top: 50%;
		left: 50%;
		margin-top: -50px;
		margin-left: -50px;
	}

	#loop {
		height: 108px;
    	width: 108px;
		border: $main-color solid 4px;
		border-radius: 200px;
	}

	#loop:before {
		background: linear-gradient(to left, rgba(187, 95, 39, 0) 0%, $main-color 30%, $main-color 70%, rgba(187, 95, 39, 0) 100%);
		content: "";
		display: block;
		height: 4px;
		left: -100px;
		position: relative;
		top: 100px;
		width: 300px;
	}

	#bike-wrapper {
		height: 108px;
		width: 108px;
		animation: drive 4s linear infinite;
	}

	#bike {
		height: 24px;
		width: 25px;
		background-image: url("https://s3-us-west-2.amazonaws.com/s.cdpn.io/133687/motorbike.png");
	}

	@keyframes drive {
		0% {
			margin-left: -364px;
			opacity: 0;
		}
		33% {
			transform: rotate(0deg);
			margin-left: -50px;
			opacity: 1;
		}
		66% {
			transform: rotate(-360deg);
			margin-left: -50px;
			opacity: 1;
		}
		100% {
			margin-left: 264px;
			transform: rotate(-360deg);
			opacity: 0;
		}
	}
</style>
<script lang="ts">
	export let size: string;
</script>

<img
	class="logo"
	style="--logo-size: {size}; width: {size}px; height: {size}px;"
	src="/liphium.png"
	alt="Logo"
/>
<img
	class="logo logo-glow"
	style="--logo-size: {size}; width: {size}px; height: {size}px;"
	src="/outline.png"
	alt=""
/>
<img
	class="logo-out-1"
	style="--logo-size: {size}; width: {size}px; height: {size}px;"
	src="/outline.png"
	alt=""
/>
<img
	class="logo-out-2"
	style="--logo-size: {size}; width: {size}px; height: {size}px;"
	src="/outline-2.png"
	alt=""
/>

<style lang="scss">
	.logo {
		transform: rotate(-5deg);
		z-index: -1;
		animation: float-main 20s infinite ease-in-out;
	}

	.logo-glow {
		position: absolute;
		z-index: 3;
		color: white;
		filter: blur(calc(10px * (var(--logo-size) / 100)));
	}

	.logo-out-1 {
		position: absolute;
		z-index: 1;
		transform: scale(1.2, 1) translateX(10px);
		filter: blur(calc(16px * (var(--logo-size) / 100))) saturate(3);
		animation: float-out-1 20s infinite ease;
	}

	.logo-out-2 {
		position: absolute;
		z-index: 2;
		transform: scale(1.5, 1.3) translateX(10px);
		transform-origin: bottom center;
		filter: blur(calc(14px * (var(--logo-size) / 100))) saturate(3);
		animation: float-out-2 20s infinite ease;
	}

	/*
    @function random-range($min, $max) {
        @return floor(random() * ($max - $min + 1)) + $min;
    }
    */

	@keyframes float-main {
		0% {
			transform: rotate(-5deg) translate(0px, 0px);
		}
		25% {
			transform: rotate(-10deg) translate(0px, -16px);
		}
		50% {
			transform: rotate(-5deg) translate(0px, 0px);
		}
		75% {
			transform: rotate(0deg) translate(0px, -24px);
		}
		100% {
			transform: rotate(-5deg) translate(0px, 0px);
		}
	}

	@keyframes float-out-1 {
		0% {
			transform: scale(1.2, 1) translate(10px, 0px);
		}
		25% {
			transform: scale(1.2, 1) translate(10px, 13px);
		}
		50% {
			transform: scale(1.2, 1) translate(10px, -20px);
		}
		75% {
			transform: scale(1.2, 1) translate(10px, 10px);
		}
		100% {
			transform: scale(1.2, 1) translate(10px, 0px);
		}
	}

	@keyframes float-out-2 {
		0% {
			transform: scale(1.5, 1.3) translate(10px, 0px);
		}
		25% {
			transform: scale(1.8, 1.3) translate(10px, -5px);
		}
		50% {
			transform: scale(1.4, 1.3) translate(10px, 10px);
		}
		75% {
			transform: scale(1.6, 1.3) translate(10px, -20px);
		}
		100% {
			transform: scale(1.5, 1.3) translate(10px, 0px);
		}
	}
</style>

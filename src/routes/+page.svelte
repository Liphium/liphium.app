<script lang="ts">
	import { onMount } from 'svelte';
	import Logo from './logo.svelte';

	onMount(() => {
		const observer = new IntersectionObserver((entries) => {
			entries.forEach((entry) => {
				console.log('change');

				if (entry.isIntersecting) {
					console.log('added');
					entry.target.classList.add('appear');
				}
			});
		});
		document.querySelectorAll('.aos').forEach((el) => {
			observer.observe(el);
		});
	});
</script>

<svelte:head>
	<title>Liphium</title>
</svelte:head>

<div class="main">
	<div class="leave-alone">
		<Logo size="300" />
	</div>

	<div class="text">
		<p class="headline">Rethinking chatting</p>
		<div class="spacer"></div>

		<div class="description">
			<p class="readable">
				With Liphium I created a secure and safe place for you and your friends, if you believe in
				this vision, be sure to join us on our journey.
			</p>
		</div>
		<div class="spacer"></div>
		<div class="description">
			<button class="secondary-action-button">Features</button>
			<button class="action-button">Join alpha</button>
		</div>
	</div>
</div>

<div class="center-maxwidth features">
	<div class="row aos">
		<div class="desc">
			<span class="material-symbols">public</span>
			<p>Find new ways to interact with your friends</p>
			<p class="secondary">
				Get your entire friends group together with next level features for sharing your calls
				(Spaces).
			</p>
		</div>
		<div class="desc left">
			<span class="material-symbols">select_check_box</span>
			<p>No setup needed</p>
			<p class="secondary">
				Liphium has all the features you need to interact with your friends group, no matter how
				big. And it all works out of the box.
			</p>
		</div>
	</div>

	<div class="spacer-gap"></div>

	<div class="row aos">
		<div class="desc">
			<span class="material-symbols">lock</span>
			<p>Privacy by default</p>
			<p class="secondary">
				Everything you share on the app is 100% end-to-end encrypted so not even we can see what you
				are doing with your friends.
			</p>
		</div>
		<div class="desc">
			<span class="material-symbols">sell</span>
			<p>Servers are expensive</p>
			<p class="secondary">
				A free app just doesn't pay for the server infrastructure needed for our app. That's why
				there will be a price tag on some features, but that doesn't mean it'll be expensive.
			</p>
		</div>
	</div>

	<div class="spacer-gap"></div>

	<div class="row aos">
		<div class="desc">
			<span class="material-symbols">equalizer</span>
			<p>High quality voice calls</p>
			<p class="secondary">
				Get secure voice chat that is made for the modern area of voice calls. You shouldn't have to
				hear someone while they're not talking.
			</p>
		</div>
		<div class="desc">
			<span class="material-symbols">content_copy</span>
			<p>Share (large) files quicker</p>
			<p class="secondary">
				With Live Share you can instantly share files of any size without someone else having to
				wait for a message. Of course they have to accept first.
			</p>
		</div>
	</div>
</div>

<div class="spacer-big"></div>

<p class="header-small aos"></p>
<p class="header aos">Join the alpha</p>
<div class="spacer-big"></div>

<style lang="scss">
	.main {
		display: flex;
		align-items: center;
		flex-direction: row;
		justify-content: space-evenly;
		height: 100vh;
		width: 100vw;

		.text {
			text-align: left;
			display: flex;
			flex-direction: column;
			justify-content: start;
		}
	}

	.leave-alone {
		display: flex;
		align-items: center;
	}

	.headline {
		font-size: 50px;
		color: var(--text);
		transition: transform 0.5s ease;
	}

	.header {
		font-size: 50px;
		color: var(--text);
		text-align: center;
		transition: transform 0.5s ease;
		transform: translateY(200px);
	}

	.header-small {
		font-size: 30px;
		color: var(--sec-text);
		text-align: center;
		transition: transform 0.5s ease;
		transform: translateY(200px);
	}

	.center-maxwidth {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		max-width: 1200px;
		margin: 0 auto;
	}

	.row {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
		gap: var(--section-spacing);
		transition: transform 0.5s ease;
		gap: 100px;
		transform: translateY(200px);

		span {
			font-size: 50px;
			color: var(--accent);
		}

		.desc {
			display: flex;
			flex-direction: column;
			align-items: start;
			justify-content: start;
			text-align: start;
			width: 500px;
			gap: var(--section-spacing);
			font-size: 30px;
			color: var(--text);

			.secondary {
				color: var(--sec-text);
				font-size: var(--large-font);
				line-height: 1.5;
			}
		}
	}

	.spacer-top {
		display: flex;
		align-items: center;
		justify-content: center;
		background: radial-gradient(circle at center, var(--header-bg) 0%, var(--background) 100px),
			var(--background);
		padding: calc(var(--section-spacing) * 4) 0;
		height: 16vh;
	}

	.spacer {
		height: 4vh;
	}

	.spacer-medium {
		height: 8vh;
	}

	.spacer-big {
		height: 30vh;
	}

	.logo {
		min-width: 70px;
		width: 5%;
		margin-right: 1rem;
		color: var(--background);
	}

	.description {
		display: flex;
		gap: var(--section-spacing);
		color: var(--text);

		p {
			max-width: 500px;
			font-size: var(--large-font);
		}
	}

	.features {
		display: flex;
		flex-direction: column;
		justify-content: center;
		gap: 4vh;
	}

	@media screen and (max-height: 700px) {
		.spacer-top {
			height: 1vh;
		}
	}

	@media screen and (max-width: 1100px) {
		.row {
			align-items: center;
			justify-content: center;
			text-align: center;
			gap: 10%;
			width: 100%;

			.desc {
				width: 40%;
			}
		}
	}

	@media screen and (max-width: 800px) {
		.features {
			gap: 2rem;
		}

		.row {
			align-items: center;
			flex-direction: column;
			justify-content: center;
			text-align: center;
			gap: 4rem;
			width: 100%;

			.desc {
				width: 90%;
			}
		}

		.gradient p {
			width: 90%;
		}

		.spacer-top {
			height: 4rem;
		}
	}

	@media screen and (max-width: 650px) {
		.gradient {
			font-size: 40px;
		}

		.header {
			font-size: 40px;
		}

		.header-small {
			font-size: 20px;
		}

		.description p {
			width: 90%;
		}
	}

	@media screen and (max-width: 400px) {
		.gradient {
			padding: 0 0 2rem 0;
			font-size: 40px;
		}

		.header {
			font-size: 40px;
		}

		.header-small {
			font-size: 20px;
		}

		.spacer-top {
			height: 1rem;
		}

		.description p {
			width: 90%;
		}
	}
</style>

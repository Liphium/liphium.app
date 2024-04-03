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
		<p class="headline">An app that's fun again</p>
		<div class="spacer"></div>

		<div class="description">
			<p class="readable">
				I could say I'm transforming chat apps and stuff, but we mostly just add really cool stuff
				no-one else thinks off.
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
			<p>We have a way to fix climate change</p>
			<p class="secondary">
				If you don't buy a table anymore and just use Liphium's Tabletop Simulator, you could save a
				couple of trees from being cut. That will reduce the carbon footprint (based on an internal
				trust me bro analysis). We'll be adding food very soon, trust us!
			</p>
		</div>
		<div class="desc left">
			<span class="material-symbols">select_check_box</span>
			<p>No setup needed, just different kinds of setup</p>
			<p class="secondary">
				Seriously, just add your friends, create a couple of group chats and our app will take care
				of everything else. No more setting up stupid permissions.
			</p>
		</div>
	</div>

	<div class="spacer-gap"></div>

	<div class="row aos">
		<div class="desc">
			<span class="material-symbols">lock</span>
			<p>We have crypto</p>
			<p class="secondary">
				We don't have NFTs and all of the other "great" Web 3 stuff, but 100% end-to-end encryption
				on almost everything should be a great fit as well. You know it's the technology powering
				all of this stuff, so it's basically Web 3.
			</p>
		</div>
		<div class="desc">
			<span class="material-symbols">sell</span>
			<p>Servers are expensive</p>
			<p class="secondary">
				We give this "amazing" piece of software to you for free, so you also have to pay for the
				servers yourself. Yes this is a crazy feature and it's totally not because I have no
				business experience.
			</p>
		</div>
	</div>

	<div class="spacer-gap"></div>

	<div class="row aos">
		<div class="desc">
			<span class="material-symbols">equalizer</span>
			<p>High quality Spaces (that's basically calls)</p>
			<p class="secondary">
				Secure voice and video calls are also integrated, you can even set stuff like microphone
				sensitivity or have an AI detect when you're talking. It's pretty great, but Average
				Intelligence often fails you.
			</p>
		</div>
		<div class="desc">
			<span class="material-symbols">content_copy</span>
			<p>Never worry about that silly big file again</p>
			<p class="secondary">
				With Live Share (not the one from Microsoft) you can share files up to any size with your
				friends. I know what you plan on using it for (it starts with "p"), but please don't tell
				your lawyers.
			</p>
		</div>
	</div>
</div>

<div class="spacer-big"></div>

<style lang="scss">
	.main {
		display: flex;
		align-items: center;
		flex-direction: row;
		justify-content: space-evenly;
		height: 100vh;
		width: 100%;

		.text {
			text-align: left;
			display: flex;
			flex-direction: column;
			justify-content: start;
		}
	}

	.footer {
		color: var(--sec-text);
		display: flex;
		justify-content: center;
		gap: var(--section-spacing);
		flex-direction: row;

		a {
			color: var(--accent);
			text-decoration: none;

			&:hover {
				text-decoration: underline;
			}
		}
	}

	.leave-alone {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 500px;
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
			line-height: 1.5;

			.secondary {
				color: var(--sec-text);
				font-size: var(--large-font);
				line-height: 1.5;
			}
		}
	}

	.spacer {
		height: 4vh;
	}

	.spacer-big {
		height: 30vh;
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
		.main {
			flex-direction: column;

			.leave-alone {
				transform: scale(0.8);
			}

			.text {
				text-align: center;

				.description {
					justify-content: center;
				}
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

		.main .leave-alone {
			transform: scale(0.6);
			height: 100px;
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

		.main .leave-alone {
			transform: scale(0.4);
			height: 100px;
		}

		.description p {
			width: 90%;
		}
	}
</style>

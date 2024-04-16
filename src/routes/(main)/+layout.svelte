<slot />

<svelte:head>
	<meta content="Liphium" property="og:title" />
	<meta content="A chat app that's fun again." property="og:description" />
	<meta content="https://liphium.com" property="og:url" />
	<meta content="https://liphium.com/favicon.png" property="og:image" />
	<meta content="#25bffc" data-react-helmet="true" name="theme-color" />
</svelte:head>

<div class="spacer"></div>

<div class="footer">
	<p>Copyright © 2024 Liphium</p>
	<a href="/">Home</a>
	<a href="/legal">Privacy & Terms</a>
	<a href="/impressum">Impressum</a>
	<a href="https://youtube.com/@unbreathable" target="_blank">Devlog Series</a>
</div>

<div class="spacer"></div>

<style lang="scss">
	.footer {
		color: var(--sec-text);
		display: flex;
		justify-content: center;
		gap: var(--section-spacing);
		flex-direction: row;
		flex-wrap: wrap;

		a {
			color: var(--accent);
			text-decoration: none;

			&:hover {
				text-decoration: underline;
			}
		}
	}

	.spacer {
		height: 4vh;
	}
</style>

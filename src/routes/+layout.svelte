<slot />

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

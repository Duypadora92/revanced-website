<script lang="ts">
	import type { Repository } from 'src/data/types';

	export let repositories: Repository[];
</script>

<hr />

<footer>
	<section class="main-content">
		<img src="/logo.svg" class="logo-image" alt="ReVanced Logo" />
		<div>
			<h1>
				<span>Re</span>Vanced
			</h1>
			<h6>Copyright © 2022, we are very legal</h6>
		</div>
	</section>

	<section class="links-container">
		<div class="link-column">
			<h5>Pages</h5>
			<a href="/"><h6>Home</h6></a>
			<a href="/download"><h6>Download</h6></a>
			<a href="/docs"><h6>Docs</h6></a>
			<a href="/patches"><h6>Patches</h6></a>
			<a href="/contributors"><h6>Contributors</h6></a>
		</div>
		{#if repositories.length}
			<div class="link-column">
				<h5>Repos</h5>
				{#each repositories as { name }}
					<a href="https://github.com/{name}" target="_blank" rel="noreferrer">
						<div>
							<h6>
								{name
									.replace(/-/g, ' ')
									.replace(/revanced\/revanced/g, '')
									.replace(/cli/g, 'CLI')
									.replace(/api/g, 'API')
									.replace(/(?:^|\s)\S/g, (x) => x.toUpperCase())}
							</h6>
						</div>
					</a>
				{/each}
			</div>
		{/if}
		<div class="link-column">
			<!-- to replace -->
			<h5>Socials</h5>
			<a href="/"><h6>Github</h6></a>
			<a href="/"><h6>Discord</h6></a>
			<a href="/"><h6>Reddit</h6></a>
			<a href="/"><h6>Twitter</h6></a>
			<a href="/"><h6>Telegram</h6></a>
			<a href="/"><h6>Video Site</h6></a>
		</div>
	</section>
</footer>

<style>
	footer {
		margin: 4rem 0 5rem 0;
		margin-inline: auto;
		display: flex;
		justify-content: space-between;
		width: min(85%, 90rem);
	}

	.main-content {
		display: flex;
		gap: 1rem;
	}

	.main-content span {
		color: var(--accent-color);
	}

	.main-content h1 {
		letter-spacing: -0.04rem;
		margin-bottom: 0.5rem;
	}

	img {
		height: 3rem;
	}

	a {
		text-decoration: none;
	}

	h6 {
		font-size: 0.9rem;
	}

	.links-container {
		display: flex;
		gap: 4rem;
	}

	.link-column {
		display: flex;
		gap: 0.5rem;
		flex-direction: column;
	}
</style>

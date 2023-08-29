<script>
	export let project;

	let img = project.img_path;

	if (!img) img = 'placeholder.svg';
</script>

<section class="project">
	<a href={'/projects/' + project.id}>
		<h3>{project.title}</h3>
		<img src="/images/projects/{img}" alt="{project.title} cover picture" />

		<p class="summary">{project.summary}</p>

		<p class="case-study">
			Read the case study
			<svg>
				<defs>
					<marker id="m" markerWidth="4" markerHeight="5" refX="0" refY="1" viewBox="0 0 1 2">
						<polygon points="0,0 1,1 0,2" fill="#ff9900" />
					</marker>
				</defs>
				<line
					x1="0"
					y1="50%"
					x2="100%"
					y2="50%"
					stroke-width="1.5"
					marker-end="url(#m)"
					stroke="#ff9900"
				/>
			</svg>
		</p>
	</a>
</section>

<style>
	svg {
		width: 20px;
		height: 20px;
		overflow: visible;
	}

	.project {
		position: relative;
		transition: .7s;
	}

	.project:nth-child(1n) {
		grid-column: span 5;
	}
	
	.project:nth-child(2n) {
		grid-column: span 4;
		transform: translateY(13rem);
	}

	.project:nth-child(3n) {
		grid-column: span 7;
		transform: translateX(6rem) translateY(1rem);
	}

	.project:nth-child(4n) {
		grid-column: span 4;
		transform: translateY(8rem);
	}

	.project:nth-child(5n) {
		grid-column: span 5;
		transform: translateY(-4rem);
	}

	.project:hover svg {
		width: 2.2rem;
	}

	.project * {
		transition: 0.5s;
	}

	.project .case-study {
		display: flex;
		gap: var(--size-s);
		color: #ff9900;
	}

	.project:hover {
		scale: 1.02;
	}

	.project:hover :is(img, .summary) {
		border-radius: var(--radius-s);
		color: var(--c-global-text);
	}

	.project img {
		width: 100%;
		aspect-ratio: 2/1.5;
		object-fit: cover;

		border-radius: var(--radius-l);
	}

	@media (max-width: 580px) {
		.project {
			transform: translateX(0) translateY(0) !important;
		}
	}
</style>

<script>
	export let project;

	let img = project.img_path;

	if (!img) img = 'placeholder.svg';

	let m = { x: 0, y: 0 };

	function handleMousemove(event) {
		m.x = event.clientX;
		m.y = event.clientY;

		console.log(m.x, m.y);
	}
</script>

<section aria-hidden="true" on:mousemove={handleMousemove} class="project">
	<a href={'/projects/' + project.id}>
		<h3>{project.title}</h3>
		<img src="/images/projects/{img}" alt="{project.title} cover picture" />
		<div class="cursor" style="transform: translateX({m.x - 24}px) translateY({m.y - 28}px)">
			🔍
		</div>

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

	.project:hover svg {
		width: 100px;
	}

	.project * {
		transition: 0.5s;
	}

	.project .case-study {
		display: flex;
		gap: var(--size-s);
		color: #ff9900;
	}

	.project:hover :is(img, .summary) {
		border-radius: var(--radius-m);
		color: var(--c-global-text);
	}

	.project img {
		width: 100%;
		aspect-ratio: 2/1.5;
		object-fit: cover;

		border-radius: var(--radius-l);
		border: 1px solid var(--c-second-text);
	}

	.cursor {
		display: none;
		align-items: center;
		justify-content: center;
		position: fixed;
		top: 0;
		left: 0;
		font-size: 4rem;
		pointer-events: none;
		transition: 0s;
		z-index: 1;
	}

	.project :hover {
		cursor: none;
	}

	.project:hover .cursor {
		display: flex;
	}
</style>

<section id="faq">
	<h2>Frequently <span>asked <span class="highlight">questions</span></span></h2>
	<div>
		<details>
			<summary>What is your <span class="highlight">availability</span>?</summary>
			Lorem, ipsum dolor sit amet consectetur adipisicing elit. Illo adipisci modi sunt quibusdam sed
			atque voluptas saepe ducimus expedita doloribus cumque eaque consectetur sit laboriosam impedit
			culpa itaque, ea labore!
		</details>
		<details>
			<summary>What is your <span class="highlight">availability</span>?</summary>
			Lorem, ipsum dolor sit amet consectetur adipisicing elit. Illo adipisci modi sunt quibusdam sed
			atque voluptas saepe ducimus expedita doloribus cumque eaque consectetur sit laboriosam impedit
			culpa itaque, ea labore!
		</details>
		<details>
			<summary>What is your <span class="highlight">availability</span>?</summary>
			Lorem, ipsum dolor sit amet consectetur adipisicing elit. Illo adipisci modi sunt quibusdam sed
			atque voluptas saepe ducimus expedita doloribus cumque eaque consectetur sit laboriosam impedit
			culpa itaque, ea labore!
		</details>
	</div>
</section>

<style>
	#faq {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		gap: var(--size-xl);
		margin: 0 3vw;
	}
	h2 {
		all: unset;
		display: flex;
		flex-direction: column;
		text-align: right;
		font-size: 2.5rem;
		margin-top: 1.5rem;
	}
    h2::before {
        display: none;
    }
	.highlight {
		color: var(--c-contrast);
	}
	div {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		max-width: 27rem;
	}
	details {
		padding: 0.3rem 0;
		font-size: 1rem;
		width: 100%;
		border-bottom: 1px solid var(--c-global-text);
		opacity: .8;
		filter: contrast(0);
	}
	details[open] {
		opacity: 1;
		filter: contrast(1);
	}

	details[open] summary {
		padding-bottom: 0.6rem;
	}
	details summary {
		padding: 0.4rem 1rem;
		font-size: 1.3rem;
		transition: 0.3s;
		font-family: 'Fugaz One', cursive;

		cursor: pointer;
	}

	@media (max-width: 735px) {
		#faq {
			display: flex;
			flex-direction: column;
			align-items: center;
			gap: var(--size-l);
		}
		h2 {
			text-align: center;
		}
		div {
			width: 90%;
			max-width: none;
		}
	}
</style>

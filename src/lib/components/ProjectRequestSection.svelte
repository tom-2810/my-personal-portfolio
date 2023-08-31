<section id="project-request">
	<div>
		<h2>Got a project?</h2>
		<a class="action-btn" href="#contact">Reach out!</a>
		<img class="🥳" src="/images/animated/partying-face.png" alt="">
		<img class="🎊" src="/images/animated/party-popper.png" alt="">
        <img class="😁" src="/images/animated/grinning-face.png" alt="">
	</div>
</section>

<style>
	#project-request {
        position: relative;
		display: flex;
		justify-content: center;
		align-items: center;
        width: 100vw;
        aspect-ratio: 1/1;
        background-image: url("/images/svg/confetti-bg.svg");
        background-size: contain;
        background-repeat: no-repeat;
        background-position: center;
	}
	#project-request > div {
		position: absolute;
		display: flex;
		flex-direction: column;
        align-items: center;
        gap: .9rem;
	}
	div img {
		position: absolute;
		height: 3rem;
	}
	.🥳 {
        height: 4rem;
        left: -15%;
        top: -90%;
        rotate: 10deg;
	}

	.🎊 {
        left: 95%;
		top: -60%;
	}

    .😁 {
        top: 150%;
        left: 30%;
        rotate: -20deg;
    }

	h2 {
		all: unset;
        font-size: 2.4rem;
	}
	h2::before {
		all: unset;
	}
    .action-btn {
        font-size: 1.3rem;
        width: 100%;
        padding: .7rem 0;
    }
</style>

<section>
    <h1>
        <span>
        Good afternoon Traveler.
        </span>
        <span>
            I’m Tom, leuk je te ontmoeten!
        </span>
    </h1>
    
    <p>
        I am a second year student at the Frontend Design & Development HvA program.
    </p>
    
    <p>
        As my choice of education might suggest, design interests me. I like micro interactions/animations, an appealing, fun and clear User Interface design.
    </p>
    
    <div class="welcome-buttons">
        <a class="action-btn" href="#contact">Reach out!</a>
        <a class="second-btn" href="#projects">Explore projects</a>
    </div>
</section>


<style>
    section {
        position: relative;
        display: flex;
        gap: var(--size-l);
        flex-direction: column;
        align-items: center;
        text-align: center;
        padding-top: 8rem;
        height: 95dvh;
        max-height: 55rem;
        width: 100%;
        max-width: 55rem;
        margin: 0 auto;
    }

    .welcome-buttons {
        display: flex;
        flex-direction: column;
        gap: .7rem;
        margin-top: auto;
        
        font-size: 2rem;
    }

    .welcome-buttons a {
        padding: var(--size-m) var(--size-xl);
    }
</style>
<header>
    <nav>
        <a href="/">Home</a>

        <ol>
            <li><a href="/#projects">Projects</a></li>
            <li><a href="/#reviews">Reviews</a></li>
            <li><a href="/#faq">Faq</a></li>
            <li><a href="#github">GitHub</a></li>
        </ol>

        <a href="#contact" class="action-btn">Reach out!</a>
    </nav>
</header>

<style>
    header {
        display: flex;
        flex-direction: row;
        justify-content: center;
        width: 100%;
        background-color: white;
    }

    nav {
        display: flex;
        flex-direction: row;
        align-items: center;
        width: 100%;
        max-width: 68rem;
        margin: 0 2vw;
        padding: var(--size-m) 0;
        gap: var(--size-m);
        z-index: 1;
    }

    nav a {
        position: relative;
        z-index: 1;
    }

    nav a:not(.action-btn):hover::after {
        content: 'TOM';
        position: absolute;
        font-size: 2rem;
        font-weight: bold;
        color: orange;
        opacity: .4;
        top: 50%;
        left: 50%;
        transform: translateX(-50%) translateY(-50%);
        z-index: -1;
    }

    nav .action-btn {
        margin-left: auto;
    }

    nav ol {
        position: absolute;
        left: 50%;
        transform: translateX(-50%);
        list-style: none;
        display: flex;
        flex-direction: row;
        gap: var(--size-l);
    }

    @media only screen and (max-width: 600px) {
        nav ol {
            position: relative;
            left: 0;
            transform: none;
            gap: var(--size-m);
        }
    }

</style>
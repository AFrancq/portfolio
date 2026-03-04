<script>
    import svelteLogo from "./assets/svelte.svg";
    import pythonLogo from "./assets/python.svg";
    import rustLogo from "./assets/rust.svg";
    import Counter from "./lib/Counter.svelte";
</script>

<main>
    <aside class="sidebar">
        <nav>
            <ul>
                <li>
                    <a
                        href="https://svelte.dev"
                        target="_blank"
                        rel="noreferrer"
                    >
                        <img
                            src={svelteLogo}
                            class="logo svelte"
                            alt="Svelte Logo"
                        />
                    </a>
                </li>
                <li>
                    <a
                        href="https://python.org"
                        target="_blank"
                        rel="noreferrer"
                    >
                        <img
                            src={pythonLogo}
                            class="logo python"
                            alt="Python Logo"
                        />
                    </a>
                </li>
                <li>
                    <a
                        href="https://rust-lang.org"
                        target="_blank"
                        rel="noreferrer"
                    >
                        <img src={rustLogo} class="logo rust" alt="Rust Logo" />
                    </a>
                </li>
            </ul>
        </nav>
    </aside>
    <h1>Home</h1>

    <div class="card">
        <Counter />
    </div>

    <p>
        Check out <a
            href="https://github.com/sveltejs/kit#readme"
            target="_blank"
            rel="noreferrer">SvelteKit</a
        >, the official Svelte app framework powered by Vite!
    </p>

    <p class="read-the-docs">
        Click on the Vite and Svelte logos to learn more
    </p>
</main>

<style>
    .logo {
        width: 5vw;
        height: 5vw;
        min-width: 48px;
        min-height: 48px;
        padding: 0.8em;
        will-change: filter, transform;
        transition:
            filter 300ms,
            transform 300ms;
        object-fit: contain;
        border: 2px solid rgba(255, 255, 255, 0.15);
        border-radius: 12px;
    }

    .logo:hover {
        filter: drop-shadow(0 0 2em #646cffaa);
        transform: scale(1.15);
        border-color: #646cff;
    }
    .logo.python:hover {
        filter: drop-shadow(0 0 2em #ffe261);
        border-color: #ffe261;
    }
    .logo.rust:hover {
        filter: drop-shadow(0 0 2em #e8e6e3);
        border-color: #e8e6e3;
    }
    .logo.svelte:hover {
        filter: drop-shadow(0 0 2em #ff3e00aa);
        border-color: #ff3e00;
    }
    .read-the-docs {
        color: #888;
    }
</style>

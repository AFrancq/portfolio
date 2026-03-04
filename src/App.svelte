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
        height: 6em;
        padding: 1.5em;
        will-change: filter;
        transition: filter 300ms;
    }
    .logo:hover {
        filter: drop-shadow(0 0 2em #646cffaa);
    }
    .logo.python:hover {
        filter: drop-shadow(0 0 2em #ffe261);
    }
    .logo.rust:hover {
        filter: drop-shadow(0 0 2em #e8e6e3);
    }
    .logo.svelte:hover {
        filter: drop-shadow(0 0 2em #ff3e00aa);
    }
    .read-the-docs {
        color: #888;
    }
</style>

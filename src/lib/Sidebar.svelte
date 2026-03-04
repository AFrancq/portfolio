<script>
    import svelteLogo from "../assets/svelte.svg";
    import pythonLogo from "../assets/python.svg";
    import rustLogo from "../assets/rust.svg";

    let { activePage, onNavigate } = $props();

    const navItems = [
        { id: "svelte", logo: svelteLogo, alt: "Svelte Logo", class: "svelte" },
        { id: "python", logo: pythonLogo, alt: "Python Logo", class: "python" },
        { id: "rust", logo: rustLogo, alt: "Rust Logo", class: "rust" },
    ];
</script>

<aside class="sidebar">
    <nav>
        <ul>
            {#each navItems as item}
                <li>
                    <button
                        class="nav-btn"
                        class:active={activePage === item.id}
                        onclick={() => onNavigate(item.id)}
                    >
                        <img
                            src={item.logo}
                            class="logo {item.class}"
                            alt={item.alt}
                        />
                    </button>
                </li>
            {/each}
        </ul>
    </nav>
</aside>

<style>
    .nav-btn {
        background: none;
        border: none;
        padding: 0;
        cursor: pointer;
    }
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

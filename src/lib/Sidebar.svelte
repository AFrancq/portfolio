<script>
    import svelteLogo from "../assets/svelte.svg";
    import pythonLogo from "../assets/python.svg";
    import goLogo from "../assets/go.svg";
    import rustLogo from "../assets/rust.svg";

    let { activePage, onNavigate } = $props();

    const navItems = [
        { id: "svelte", logo: svelteLogo, alt: "Svelte Logo", variant: "svelte" },
        { id: "python", logo: pythonLogo, alt: "Python Logo", variant: "python" },
        { id: "go", logo: goLogo, alt: "Go Logo", variant: "go" },
        { id: "rust", logo: rustLogo, alt: "Rust Logo", variant: "rust" },
    ];

    let isHome = $derived(activePage === "home");
</script>

<aside class="sidebar">
    <!-- AF Home Button -->
    <button
        class="nav-btn af-btn"
        class:expanded={isHome}
        onclick={() => onNavigate("home")}
        aria-label="Go to home"
    >
        <span class="af-circle">AF</span>
    </button>

    <!-- Tech Nav Items -->
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
                            class="nav-icon {item.variant}"
                            alt={item.alt}
                        />
                    </button>
                </li>
            {/each}
        </ul>
    </nav>
</aside>

<style>
    /* ========================================
       CSS Custom Properties - Single source of truth
       ======================================== */
    .sidebar {
        --nav-size: clamp(48px, 5vw, 72px);
        --nav-padding: 0.8em;
        --nav-radius: 12px;
        --nav-border-idle: rgba(255, 255, 255, 0.15);
        --transition-fast: 200ms ease;
        --transition-smooth: 300ms cubic-bezier(0.4, 0, 0.2, 1);
        
        /* Brand colors */
        --color-cyan: #00ffff;
        --color-svelte: #ff3e00;
        --color-python: #ffe261;
        --color-go: #00ffff;
        --color-rust: #e8e6e3;
        --color-default: #646cff;
    }

    /* ========================================
       Sidebar Layout
       ======================================== */
    .sidebar {
        position: fixed;
        top: 0;
        left: 0;
        width: 15vw;
        height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding-top: 1rem;
        gap: 1rem;
    }

    nav ul {
        list-style: none;
        margin: 0;
        padding: 0;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 0.5rem;
    }

    /* ========================================
       Shared Button Styles
       ======================================== */
    .nav-btn {
        background: none;
        border: none;
        padding: 0;
        cursor: pointer;
    }

    /* ========================================
       Nav Icon (Tech logos)
       ======================================== */
    .nav-icon {
        width: var(--nav-size);
        height: var(--nav-size);
        padding: var(--nav-padding);
        object-fit: contain;
        border: 2px solid var(--nav-border-idle);
        border-radius: var(--nav-radius);
        background-color: transparent;
        will-change: filter, transform, background-color;
        transition:
            filter var(--transition-smooth),
            transform var(--transition-smooth),
            background-color var(--transition-smooth),
            border-color var(--transition-smooth);
    }

    /* Hover states */
    .nav-icon:hover {
        transform: scale(1.1);
    }

    .nav-icon.svelte:hover {
        filter: drop-shadow(0 0 1.5em var(--color-svelte));
        border-color: var(--color-svelte);
    }

    .nav-icon.python:hover {
        filter: drop-shadow(0 0 1.5em var(--color-python));
        border-color: var(--color-python);
    }

    .nav-icon.go:hover {
        filter: drop-shadow(0 0 1.5em var(--color-go));
        border-color: var(--color-go);
    }

    .nav-icon.rust:hover {
        filter: drop-shadow(0 0 1.5em var(--color-rust));
        border-color: var(--color-rust);
    }

    /* Active states */
    .nav-btn.active .nav-icon.svelte {
        background-color: rgba(255, 62, 0, 0.2);
        border-color: var(--color-svelte);
    }

    .nav-btn.active .nav-icon.python {
        background-color: rgba(255, 226, 97, 0.2);
        border-color: var(--color-python);
    }

    .nav-btn.active .nav-icon.go {
        background-color: rgba(0, 255, 255, 0.2);
        border-color: var(--color-go);
    }

    .nav-btn.active .nav-icon.rust {
        background-color: rgba(232, 230, 227, 0.2);
        border-color: var(--color-rust);
    }

    /* ========================================
       AF Circle (Home button)
       ======================================== */
    .af-btn {
        position: fixed;
        z-index: 100;
        /* Default position: in sidebar, aligned with nav items */
        top: 1rem;
        left: calc(7.5vw - calc(var(--nav-size) / 2));
        transition:
            top 0.4s cubic-bezier(0.4, 0, 0.2, 1),
            left 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .af-circle {
        display: flex;
        align-items: center;
        justify-content: center;
        width: var(--nav-size);
        height: var(--nav-size);
        border-radius: 50%;
        background: linear-gradient(135deg, #1a1a1a 0%, #2a2a2a 100%);
        border: 2px solid var(--nav-border-idle);
        color: #c0c0c0;
        font-size: clamp(0.9rem, 1.5vw, 1.2rem);
        font-weight: 600;
        letter-spacing: 0.05em;
        will-change: transform, box-shadow, border-color, width, height;
        transition:
            transform var(--transition-smooth),
            box-shadow var(--transition-fast),
            border-color var(--transition-smooth),
            width 0.4s cubic-bezier(0.4, 0, 0.2, 1),
            height 0.4s cubic-bezier(0.4, 0, 0.2, 1),
            font-size 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .af-btn:hover .af-circle {
        border-color: var(--color-cyan);
        box-shadow: 0 0 15px rgba(0, 255, 255, 0.3);
        transform: scale(1.1);
    }

    /* Expanded state (on home page) */
    .af-btn.expanded {
        top: 4rem;
        left: calc(15vw + 2rem);
    }

    .af-btn.expanded .af-circle {
        width: 120px;
        height: 120px;
        font-size: 2rem;
        border-color: var(--color-cyan);
    }

    .af-btn.expanded:hover .af-circle {
        box-shadow: 0 0 25px rgba(0, 255, 255, 0.4);
    }

    /* Adjust nav position to account for fixed AF button */
    nav {
        margin-top: calc(var(--nav-size) + 1.5rem);
    }
</style>

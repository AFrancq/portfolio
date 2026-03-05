<script>
    import Sidebar from "./lib/Sidebar.svelte";
    import Home from "./pages/Home.svelte";
    import SveltePage from "./pages/Svelte.svelte";
    import PythonPage from "./pages/Python.svelte";
    import GoPage from "./pages/Go.svelte";
    import RustPage from "./pages/Rust.svelte";

    let activePage = $state("home");

    const pages = {
        home: Home,
        svelte: SveltePage,
        python: PythonPage,
        go: GoPage,
        rust: RustPage,
    };
</script>

<main>
    <Sidebar {activePage} onNavigate={(page) => (activePage = activePage === page ? "home" : page)} />

    <!-- AF Circle - always fixed, uses transform for smooth transitions -->
    <button
        class="af-circle"
        class:expanded={activePage === "home"}
        onclick={() => (activePage = "home")}
        aria-label="Go to home"
    >
        <span>AF</span>
    </button>

    <div class="content">
        {#if pages[activePage]}
            {@const Component = pages[activePage]}
            <Component />
        {/if}
    </div>
</main>

<style>
    main {
        display: flex;
    }

    .content {
        margin-left: 15vw;
        flex: 1;
        padding: 0;
    }

    /* AF Circle - Base state (mini, in sidebar) */
    .af-circle {
        position: fixed;
        z-index: 100;
        
        /* Base position: centered in sidebar at top */
        top: 1rem;
        left: calc(7.5vw - 25px);
        
        /* Size for mini state */
        width: 50px;
        height: 50px;
        
        border-radius: 50%;
        background: linear-gradient(135deg, #1a1a1a 0%, #2a2a2a 100%);
        border: 2px solid rgba(255, 255, 255, 0.15);
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 1rem;
        font-weight: 600;
        color: #c0c0c0;
        letter-spacing: 0.05em;
        cursor: pointer;
        padding: 0;
        
        /* Smooth transitions for all properties */
        transition:
            top 0.5s cubic-bezier(0.4, 0, 0.2, 1),
            left 0.5s cubic-bezier(0.4, 0, 0.2, 1),
            width 0.5s cubic-bezier(0.4, 0, 0.2, 1),
            height 0.5s cubic-bezier(0.4, 0, 0.2, 1),
            font-size 0.5s cubic-bezier(0.4, 0, 0.2, 1),
            border-color 0.3s ease,
            box-shadow 0.3s ease;
    }

    .af-circle:hover {
        border-color: #00ffff;
        box-shadow: 0 0 15px rgba(0, 255, 255, 0.3);
    }

    /* Expanded state (on home page) */
    .af-circle.expanded {
        top: calc(2rem + 50px); /* Below some header space */
        left: calc(15vw + 3rem);
        width: 140px;
        height: 140px;
        font-size: 2.2rem;
        border-color: #00ffff;
    }

    .af-circle.expanded:hover {
        box-shadow: 0 0 25px rgba(0, 255, 255, 0.5);
    }
</style>

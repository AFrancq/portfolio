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
        padding: 2rem;
    }
</style>

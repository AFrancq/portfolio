<script>
    import Sidebar from "./lib/Sidebar.svelte";
    import Home from "./pages/Home.svelte";
    import SveltePage from "./pages/Svelte.svelte";
    import PythonPage from "./pages/Python.svelte";
    import RustPage from "./pages/Rust.svelte";

    let activePage = $state("home");

    const pages = {
        home: Home,
        svelte: SveltePage,
        python: PythonPage,
        rust: RustPage,
    };
</script>

<main>
    <Sidebar {activePage} onNavigate={(page) => (activePage = page)} />

    <div class="content">
        {#if pages[activePage]}
            <svelte:component this={pages[activePage]} />
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

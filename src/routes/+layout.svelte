<script>
    let { children } = $props();
    import { page } from "$app/stores";

    const currentPage = $derived($page.url.pathname);

    function changeTheme() {
        const theme = document
            .querySelector("html")
            ?.getAttribute("data-theme");
        document
            .querySelector("html")
            ?.setAttribute("data-theme", theme === "dark" ? "ligth" : "dark");
    }
</script>

<nav style="border-bottom: 1px solid var(--pico-form-element-border-color);">
    <ul>
        <li style="font-size: 1.4rem;"><a href="/">BHD</a> <strong>Personal</strong></li>
    </ul>
    <ul>
        <li class="hide-on-small">
            <a href="/" aria-current={currentPage === "/" ? "page" : false}
                >Mis productos</a
            >
        </li>
        <li class="hide-on-small">
            <a
                href="/transactions"
                aria-current={currentPage === "/transactions" ? "page" : false}
            >
                Pagos y transferencias
            </a>
        </li>
        <li class="hide-on-small">
            <a href="#" aria-current={currentPage === "/3" ? "page" : false}
                >Solicitudes y reclamaciones</a
            >
        </li>
        <li>
            <details class="dropdown">
                <summary
                    style="text-wrap: nowrap; display: flex; align-items: center; gap: .5rem"
                >
                    <ion-icon
                        name="person-circle-outline"
                        style="font-size: 2rem;"
                    ></ion-icon>
                    Richard Jimenez
                </summary>
                <ul style="z-index: 99999999;">
                    <li>
                        <a href="#" on:click={changeTheme}>🌓 Cambiar tema</a>
                    </li>
                    <li><a href="#">⚙ Configuraciones</a></li>
                    <li><a href="#">🙋‍♂️ Cerrar sesion</a></li>
                </ul>
            </details>
        </li>
    </ul>
</nav>

<!-- <nav aria-label="breadcrumb">
    <ul>
        <li><a href="/">Dashboard</a></li>
        {#if currentPage === "/"}
            <li>Inicio</li>
        {/if}
    </ul>
</nav> -->
<br />
<main>
    {@render children()}
</main>


<style>
    @media screen and (max-width: 768px) {
        .hide-on-small {
            display: none;
        }
    }
</style>
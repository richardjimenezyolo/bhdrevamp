<script lang="js">
    import Chart from "chart.js/auto";

    let quickOptions = [
        { text: "Transacciones entre mis productos", icon: "cash-outline" },
        { text: "Pago de servicios e impuestos", icon: "bulb-outline" },
        {
            text: "Transacciones entre productos BHD y otros bancos",
            icon: "trending-up-outline",
        },
        { text: "Inscripción de nuevo servico", icon: "book-outline" },
        { text: "Pagos múltiples", icon: "apps-outline" },
    ];

    const data = {
        labels: [
            "Junio",
            "Julio",
            "Agosto",
            "Septiembre",
            "Octubre",
            "Noviembre",
            "Diciembre",
        ],
        datasets: [
            {
                label: "My First Dataset",
                data: [65, 59, 80, 81, 56, 55, 40],
                fill: false,
                borderColor: "rgb(75, 192, 192)",
                tension: 0.1,
            },
        ],
    };

    /**
     *
     * @param {HTMLCanvasElement} canvas
     */
    const graph = (canvas) => {
        const ctx = canvas.getContext("2d");

        new Chart(ctx, {
            type: "line",
            data: {
                labels: [
                    "Junio",
                    "Julio",
                    "Agosto",
                    "Septiembre",
                    "Octubre",
                    "Noviembre",
                    "Diciembre",
                ],
                datasets: [
                    {
                        label: "Richard Jimenez",
                        data: [12, 19, 3, 5, 2, 3].map(el => el * 1000),
                        borderWidth: 1,
                        backgroundColor: '#398712',
                        borderColor: '#398712'
                    },
                    {
                        label: "Personal",
                        data: [12, 19, 3, 5, 2, 3].map(el => el * 5000),
                        borderWidth: 1,
                        backgroundColor: '#D24317',
                        borderColor: '#D24317'
                    },
                ],
            },
        });
    };
</script>

<svelte:head>
    <title>Inicio | BHD</title>
</svelte:head>

<section class="grid">
    <div class="col-1">
        <article>
            <header><h3>Resumen de Productos</h3></header>

            <details open>
                <summary>CUENTAS (2)</summary>
                <table>
                    <tbody>
                        <tr>
                            <td>
                                <p>Richard Jimenez</p>
                                <small>
                                    <a href="#">2970016459</a>
                                </small>
                            </td>
                            <td>Ahorros <br /> activa</td>
                            <td class="text-right">RD$ 0.0</td>
                        </tr>

                        <tr>
                            <td>
                                <p>Personal</p>
                                <small>
                                    <a href="#">2970016459</a>
                                </small>
                            </td>
                            <td>Ahorros <br /> activa</td>
                            <td class="text-right">USD$ 420.69</td>
                        </tr>
                    </tbody>
                </table>
            </details>
            <hr />
            <details open>
                <summary>TARJETAS DE CRÉDITO</summary>

                <table>
                    <tbody>
                        <tr>
                            <td style="width: 274px;">
                                <p style="width: 274px;">
                                    PORKHE ME LO MEREZCO 😜
                                </p>
                                <small>
                                    <a href="#">2970016459</a>
                                </small>
                            </td>
                            <td>Ahorros <br /> activa</td>
                            <td class="text-right">
                                <span>RD$ -30,000</span>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </details>
        </article>
    </div>
    <div class="col-2">
        <aside>
            <article>
                <header>
                    <h3>Accesos rápidos</h3>
                </header>
                <nav>
                    <ul>
                        {#each quickOptions as op}
                            <li>
                                <a
                                    href="#"
                                    style="display:flex; align-items: center;"
                                >
                                    <ion-icon
                                        name={op.icon}
                                        style="font-size: 1.5rem;"
                                    ></ion-icon>
                                    <span style="margin-left: .5rem;"
                                        >{op.text}</span
                                    >
                                </a>
                            </li>
                        {/each}
                    </ul>
                </nav>
            </article>

            <article>
                <canvas use:graph width="100%"></canvas>
            </article>
        </aside>
    </div>
</section>

<style>

    .col-1 {
        grid-column-start: 1;
        grid-column-end: 3;
    }

    .text-right {
        text-align: right;
    }
</style>

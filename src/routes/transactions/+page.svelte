<script>
    import Dropdown from "$lib/dropdown.svelte";

    let transactionTypes = [
        { text: "Transacciones entre mis productos", icon: "cash-outline" },
        { text: "Pago de servicios e impuestos", icon: "bulb-outline" },
        {
            text: "Transacciones entre productos BHD y otros bancos",
            icon: "trending-up-outline",
        },
        { text: "Inscripción de nuevo servico", icon: "book-outline" },
        { text: "Pagos múltiples", icon: "apps-outline" },
    ];

    let origins = [
        {text: 'Richard Jimenez - 2970016459'},
        {text: 'Cuenta personal - 2970016459'},
        {text: 'PORKHE ME LO MEREZCO 😜 - 2970016459'}
    ]

    let tran = $state();
</script>

<svelte:head>
    <title>Transacciones | BHD </title>
</svelte:head>

<form class="container">
    <h1>Transacciones bancarias</h1>
    <article>
        <!-- svelte-ignore a11y_label_has_associated_control -->
        <label>
            Tipo de transacción:
            <Dropdown items={transactionTypes}></Dropdown>
        </label>

        <div class="grid">
            <label>
                Producto origen
                <Dropdown items={origins}></Dropdown>
            </label>
            <label>
                Producto Destino
                <Dropdown items={[
                    {text: 'Nuevo destino', icon: 'add-circle-outline'},
                    {text: 'Banco BHD'},
                    {text: 'Banco Popular'},
                    {text: 'Mi hermano'},
                    {text: 'Mi madre'},
                    {text: 'UNAPEC'},
                    {text: 'ETC...'},
                ]}></Dropdown>
            </label>
        </div>

        <label>
            Monto:
            <input type="number" placeholder="RD$ 1,000">
        </label>

        <footer style="display: flex; justify-content: end; gap: .5rem;">
            <button class="secondary outline">Cancelar</button>
            <button>Aceptar</button>
        </footer>
    </article>
</form>

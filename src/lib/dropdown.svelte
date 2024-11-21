<script>
    let props = $props();

    const items = $derived(props.items || []);

    let selected = $state(props.value);

    function whenChange(v) {
        selected = v;
    }
</script>

<details class="dropdown">
    <summary
        style="display: flex; align-items: center; gap: .5rem; justify-content: space-between;"
    >
        <div style="display: flex; align-items: center; gap: 1rem;">
            {#if selected}
                {#if selected.icon}
                    <ion-icon name={selected?.icon} style="font-size: 1.5rem;"></ion-icon>
                {/if}
                {selected?.text}
            {/if}
            {#if !selected}
                Seleccione una opcion
            {/if}
        </div>
    </summary>

    <ul>
        {#each items as i}
            <li>
                <a on:click={() => whenChange(i)} style="display: flex; align-items: center; gap: 1rem; cursor: pointer;">
                    {#if i.icon}
                        <ion-icon name={i.icon} style="font-size: 1.5rem;"></ion-icon>
                    {/if}
                    {i.text}
                </a>
            </li>
        {/each}
    </ul>
</details>

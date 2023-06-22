<script>
    import { fly, scale } from "svelte/transition";
    import { quintOut } from "svelte/easing";
    import { onMount } from "svelte";

    let visible = false;

    onMount(() => {
        visible = true;
    });
</script>

<section id="hero" class="d-flex align-items-center">
    <div class="container">
        {#if visible}
            <div
                in:fly={{
                    x: -200,
                    y: 200,
                    delay: 250,
                    duration: 1000,
                    easing: quintOut,
                }}
                class="row"
            >
                <div in:scale={{ delay: 250, duration: 1000 }} class="col-xl-7">
                    <h1>Soluciones para hotshot</h1>
                    <h2>
                        Somos un grupo de jóvenes de especialidades eléctricas 
                        y mecánicas dedicados al alquiler, reparación, 
                        modificación y mantenimiento de remolques para hotshot.
                    </h2>
                </div>
            </div>
        {/if}
    </div>
</section>

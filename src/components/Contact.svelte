<script>
    import { fade, slide } from "svelte/transition";
    import { onMount } from "svelte";
    import Saos from "saos";

    let ready = false;
    onMount(() => (ready = true));

    // Section Id
    export let Id;
    // Section title
    export let contact_title;
    // Social media links
    export let social;
    // theme toggle
    export let state;

    let text_color = "dark";
    let bg_color = "light";

    if (state == "dark") {
        text_color = "light";
        bg_color = "dark";
    }
</script>

<!-- Contact component -->
<div
    class="bg-{bg_color} text-{text_color} d-flex justify-content-center align-items-center min-vh-100"
    id={Id}
    style="padding-top:58px;"
>
    <Saos animation={""}>
        {#if ready}
            <div class="container">
                <!-- Section title -->
                <div in:slide={{ duration: 1000 }} class="text-center mb-3">
                    <h1 class="fw-bold text-primary">
                        {contact_title}
                    </h1>
                    <h1 class="text-primary"><i class="far fa-envelope" /></h1>
                </div>
                <!-- Section title -->

                <hr />

                <!-- Section Data -->
                <div in:fade={{ delay: 500, duration: 1000 }}>
                    <h1 class="text-primary text-center">
                        <!-- Social Media -->
                        {#each social as item}
                            <a
                                class="btn shadow-sm mx-1"
                                href={item[2]}
                                role="button"
                            >
                                <i class="h3 {item[1]}" />
                            </a>
                        {/each}
                        <!-- Social Media -->
                    </h1>
                </div>
                <!-- Section Data -->

                <!-- Empty column to make things perfect -->
                <div class="col-md-12" />
                <!-- Empty column to make things perfect -->
            </div>
        {/if}
    </Saos>
</div>
<!-- Contact component -->

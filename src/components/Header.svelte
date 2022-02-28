<script>
    import { fade, slide } from "svelte/transition";
    import { onMount } from "svelte";
    import Saos from "saos";

    let ready = false;
    onMount(() => (ready = true));

    // Section Id
    export let Id;
    // First title
    export let header_title_1;
    // Second title
    export let header_title_2;
    // Third title
    export let header_title_3;
    // theme toggle
    export let state;

    let text_color = "dark";
    let bg_color = "light";

    if (state == "dark") {
        text_color = "light";
        bg_color = "dark";
    }
</script>

<!-- Header component -->
<div
    class="text-{text_color} d-flex justify-content-center align-items-center min-vh-100"
    id={Id}
    style="padding-top:58px;"
>
    <div class="row container">
        <!-- Left Section -->
        <Saos animation={""}>
            {#if ready}
                <div class="col-md-6 mb-3 text-uppercase">
                    <!-- Title 1 -->
                    <span
                        in:fade={{ duration: 1000 }}
                        class="fw-bold d-block display-1 text-primary"
                    >
                        {header_title_1}
                    </span>
                    <!-- Title 1 -->

                    <!-- Title 2 -->
                    <span
                        in:slide={{ delay: 500, duration: 1000 }}
                        class="fw-bold d-block display-1"
                    >
                        {header_title_2}
                    </span>
                    <!-- Title 2 -->

                    <!-- Title 3 -->
                    <span
                        in:fade={{ delay: 1200, duration: 1000 }}
                        class="fw-bold {text_color} display-5"
                        style="opacity:0.7;"
                    >
                        {header_title_3}
                    </span>
                    <!-- Title 3 -->
                </div>
            {/if}
        </Saos>
        <!-- Left Section -->

        <!-- Right Section -->
        <div class="col-md-6 mb-3" />
        <!-- Right Section -->
    </div>
</div>
<!-- Header component -->

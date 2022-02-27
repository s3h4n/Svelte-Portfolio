<script>
    import { slide, fade } from "svelte/transition";
    import { onMount } from "svelte";
    import Saos from "saos";

    let ready = false;
    onMount(() => (ready = true));

    // Section Id
    export let Id;
    // Section title
    export let projects_title;
    // Array of projects
    export let projects;
    // theme toggle
    export let state;

    let text_color = "dark";
    let bg_color = "light";

    if (state == "dark") {
        text_color = "light";
        bg_color = "dark";
    }
</script>

<!-- Projects component -->
<div
    class="text-{text_color} d-flex justify-content-center align-items-center min-vh-100"
    id={Id}
    style="padding-top:58px;"
>
    <Saos animation={""}>
        {#if ready}
            <div class="row container justify-content-center">
                <!-- Section title -->
                <div
                    in:slide={{ duration: 1000 }}
                    class="col-md-12 text-center mb-5"
                >
                    <h1 class="fw-bold text-primary">{projects_title}</h1>
                </div>
                <!-- Section title -->
                <hr class="mb-5" />
                <!-- Section Data -->
                {#each projects as project}
                    <div
                        in:fade={{ delay: 500, duration: 1500 }}
                        class="col-md-6 mb-3"
                    >
                        <a
                            class="text-{text_color}"
                            href={project[2]}
                            target="_blank"
                        >
                            <div class="card bg-{bg_color} hover-shadow">
                                <div class="card-body">
                                    <!-- Project name -->
                                    <h5 class="card-title text-primary fw-bold">
                                        {project[0]}
                                    </h5>
                                    <!-- Project description -->
                                    <p class="card-text">{project[1]}</p>
                                </div>
                            </div>
                        </a>
                    </div>
                {/each}
                <!-- Section title -->
            </div>
        {/if}
    </Saos>
</div>
<!-- Projects component -->

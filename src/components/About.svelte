<script>
    import { slide, fade } from "svelte/transition";
    import { onMount } from "svelte";
    import Saos from "saos";

    let ready = false;
    onMount(() => (ready = true));

    // Section Id
    export let Id;
    // Title of skills area
    export let skills_title;
    // Skills
    export let skills;
    // Title of bio area
    export let bio_title;
    // Bio description
    export let bio;
    // theme toggle
    export let state;

    let text_color = "dark";
    let bg_color = "light";

    if (state == "dark") {
        text_color = "light";
        bg_color = "dark";
    }
</script>

<!-- About component -->
<div
    class="bg-{bg_color} text-{text_color} d-flex justify-content-center align-items-center min-vh-100"
    id={Id}
    style="padding-top:58px;"
>
    <Saos animation={""}>
        {#if ready}
            <div class="row container">
                <!-- About Section -->
                <div in:fade={{ duration: 1000 }} class="col-md-6 mb-3">
                    <!-- Section title -->
                    <h1 class="fw-bold text-primary mb-5">{bio_title}</h1>
                    <!-- Section title -->

                    <hr class="mb-5" />

                    <!-- Section Data -->
                    <p in:fade={{ delay: 500, duration: 1000 }} class="">
                        {bio}
                    </p>
                    <!-- Section Data -->
                </div>
                <!-- About Section -->

                <!-- Skills Section -->

                <div in:fade={{ duration: 1000 }} class="col-md-6">
                    <!-- Section title -->
                    <h1 class="fw-bold text-primary mb-5">{skills_title}</h1>
                    <!-- Section title -->

                    <hr class="mb-5" />

                    <!-- Section Data -->
                    <div in:fade={{ delay: 1000, duration: 1000 }} class="row">
                        <!-- Known programming languages -->
                        <div class="col-md-6">
                            {#each skills["Languages"] as skill}
                                <p class="fw-bold">
                                    <i class={skill[1]} />
                                    {skill[0]}
                                </p>
                                <div
                                    class="progress progress-bar-striped progress-bar-animated bg-{bg_color} mb-3"
                                >
                                    <div
                                        class="progress-bar bg-primary animate"
                                        role="progressbar"
                                        style="--size:{skill[2]}%"
                                        aria-valuenow={skill[2]}
                                        aria-valuemin="0"
                                        aria-valuemax="100"
                                    />
                                </div>
                            {/each}
                        </div>
                        <!-- Known programming languages -->

                        <!-- Known frameworks -->
                        <div class="col-md-6">
                            {#each skills["Frameworks"] as skill}
                                <p class="fw-bold">
                                    <i class={skill[1]} />
                                    {skill[0]}
                                </p>
                                <div
                                    class="progress progress-bar-striped progress-bar-animated bg-{bg_color} mb-3"
                                >
                                    <div
                                        class="progress-bar bg-primary animate"
                                        role="progressbar"
                                        style="--size:{skill[2]}%"
                                        aria-valuenow={skill[2]}
                                        aria-valuemin="0"
                                        aria-valuemax="100"
                                    />
                                </div>
                            {/each}
                        </div>
                        <!-- Known frameworks -->
                    </div>
                    <!-- Section Data -->
                </div>
                <!-- Skills Section -->
            </div>
        {/if}
    </Saos>
</div>

<!-- About component -->
<style>
    .animate {
        animation: animate 4s both;
    }

    @keyframes animate {
        0% {
            width: 0;
        }
        100% {
            width: var(--size);
        }
    }
</style>

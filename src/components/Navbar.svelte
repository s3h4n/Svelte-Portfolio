<script>
    // Section Id
    export let Id;
    // Brand name
    export let brand;
    // Navigation bar items
    export let nav_items;
    // Github profile
    export let github;
    // theme toggle
    export let state;

    let text_color = "dark";
    let bg_color = "light";

    if (state == "dark") {
        text_color = "light";
        bg_color = "dark";
    }
</script>

<!-- Navigation component -->
<div class="container">
    <!-- Navbar -->
    <nav
        class="navbar navbar-expand-lg navbar-{bg_color} bg-{bg_color} shadow-0 fixed-top px-3 py-3"
        {Id}
    >
        <div class="container-fluid">
            <!-- Navbar brand -->
            <a class="navbar-brand text-primary" href="/">
                <strong>{brand}</strong>
            </a>
            <!-- Navbar brand -->

            <!-- Toggle button -->
            <button
                class="navbar-toggler"
                type="button"
                data-mdb-toggle="collapse"
                data-mdb-target="#navbarSupportedContent"
                aria-controls="navbarSupportedContent"
                aria-expanded="false"
                aria-label="Toggle navigation"
            >
                <i class="fas fa-bars" />
            </button>
            <!-- Toggle button -->

            <!-- Collapsible wrapper -->
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <!-- Navbar items -->
                <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
                    <!-- Links -->
                    {#each nav_items as item}
                        <li class="nav-item">
                            <a class="nav-link text-{text_color}" href={item[1]}
                                >{item[0]}</a
                            >
                        </li>
                    {/each}
                    <!-- Links -->

                    <!-- Github -->
                    <li>
                        <a class="nav-link text-{text_color}" href={github}>
                            <i class="fab fa-github" />
                        </a>
                    </li>
                    <!-- Github -->
                </ul>
                <!-- Navbar items -->
            </div>
        </div>
    </nav>
    <!-- Navbar -->
</div>
<!-- Navigation component -->

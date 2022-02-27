<script>
    // Section Id
    export let Id;
    // Brand name
    export let brand;
    // theme toggle
    export let state;

    let text_color = "dark";
    let bg_color = "light";

    if (state == "dark") {
        text_color = "light";
        bg_color = "dark";
    }
</script>

<!-- Footer component -->
<footer class="bg-{bg_color} text-center text-{text_color}" id={Id}>
    <!-- Copyright -->
    <div class="text-center p-3">
        &copy; {new Date().getFullYear()} Copyright:
        <a class="text-{text_color}" href="/">{brand}</a>
    </div>
    <!-- Copyright -->
</footer>
<!-- Footer component -->

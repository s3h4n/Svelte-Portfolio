<script>
	import Navbar from "./components/Navbar.svelte";
	import Footer from "./components/Footer.svelte";
	import Header from "./components/Header.svelte";
	import About from "./components/About.svelte";
	import Projects from "./components/Projects.svelte";
	import Contact from "./components/Contact.svelte";

	/**
	 * -------------------- Navigation Bar --------------------
	 */
	let brand = "Itz John";
	let nav_items = [
		["Home", "#"],
		["About", "#about"],
		["Projects", "#projects"],
		["Contact", "#contact"],
	];
	let github = "#";

	/**
	 * -------------------- Header Section --------------------
	 */
	let header_title_1 = "Hello,";
	let header_title_2 = "I'm Jhon.";
	let header_title_3 = "UI Designer.";

	/**
	 * -------------------- About Section --------------------
	 */
	let bio_title = "About Me";
	let skills_title = "My Skills";
	let skills = {
		Languages: [
			["Python", "fab fa-python", 80],
			["Shell Script", "fab fa-linux", 35],
			["HTML/CSS", "fab fa-html5", 90],
			["JavaScript", "fab fa-js-square", 55],
			["PHP", "fab fa-php", 65],
		],
		Frameworks: [
			["Bootsrap", "fab fa-bootstrap", 85],
			["Laravel", "fab fa-laravel", 45],
			["Svelte", "fas fa-code", 55],
		],
	};
	let bio =
		"Lorem ipsum, dolor sit amet consectetur adipisicing elit. Id repellat rerum, vel autem ullam aut architecto culpa quaerat cum. Dolore, porro sint velit tempore illum enim aspernatur dolorem reiciendis doloremque?";

	/**
	 * -------------------- Project Section --------------------
	 */
	let projects_title = "Project Showcase";
	let projects = [
		[
			"Project 1",
			"Lorem ipsum, dolor sit amet consectetur adipisicing elit. Id repellat rerum, vel autem ullam aut architecto culpa quaerat cum. Dolore, porro sint velit tempore illum enim aspernatur dolorem reiciendis doloremque?",
			"#",
		],
		[
			"Project 2",
			"Lorem ipsum, dolor sit amet consectetur adipisicing elit. Id repellat rerum, vel autem ullam aut architecto culpa quaerat cum. Dolore, porro sint velit tempore illum enim aspernatur dolorem reiciendis doloremque?",
			"#",
		],
		[
			"Project 3",
			"Lorem ipsum, dolor sit amet consectetur adipisicing elit. Id repellat rerum, vel autem ullam aut architecto culpa quaerat cum. Dolore, porro sint velit tempore illum enim aspernatur dolorem reiciendis doloremque?",
			"#",
		],
		[
			"Project 4",
			"Lorem ipsum, dolor sit amet consectetur adipisicing elit. Id repellat rerum, vel autem ullam aut architecto culpa quaerat cum. Dolore, porro sint velit tempore illum enim aspernatur dolorem reiciendis doloremque?",
			"#",
		],
	];
	/**
	 * -------------------- Contact Section --------------------
	 */
	let contact_title = "Contact Me";
	let social = [
		["LinkedIn", "fab fa-linkedin", "#"],
		["Email", "fas fa-envelope", "mailto:#"],
		["Twitter", "fab fa-twitter", "#"],
		["YouTube", "fab fa-youtube", "#"],
		["Github", "fab fa-github", github],
	];

	/**
	 * -------------------- Theme Toggle --------------------
	 */
	let state = "dark"; // Change this to "light" to use light theme.

	let text_color = "dark";
	let bg_color = "light";

	if (state === "dark") {
		text_color = "light";
		bg_color = "dark";
	}
</script>

<main class="bg-{bg_color} text-{text_color} min-vh-100">
	<div class="bg-pattern">
		<Navbar Id="navbar" {brand} {nav_items} {github} {state} />
		<Header
			Id="#"
			{header_title_1}
			{header_title_2}
			{header_title_3}
			{state}
		/>
		<About Id="about" {bio_title} {bio} {skills_title} {skills} {state} />
		<Projects Id="projects" {projects_title} {projects} {state} />
		<Contact Id="contact" {contact_title} {social} {state} />
		<Footer Id="footer" {brand} {state} />
	</div>
</main>

<style>
</style>

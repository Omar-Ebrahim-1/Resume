<script>
	import Header from './Header.svelte';
	import Education from './Education.svelte';
	import Experience from "./Experience.svelte";
	import Skills from './Skills.svelte';
	import Projects from './Projects.svelte';
</script>

<Header />
<main>
	<div style="width: 50%">
		<Projects />
	</div>

	<div style="width: 45%;">
		<div class="tiny-adjust"></div>
		<Experience />
		<Skills />
		<Education />
	</div>
</main>

<style>
	main {
		margin: 0;
		padding: 0;
		display: flex;
		justify-content: space-between
	}
</style>

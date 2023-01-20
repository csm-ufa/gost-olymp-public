<script>
	import Container from './Container.svelte';
	import Navbar from './Navbar.svelte';
</script>


<header class="w-full bg-[#f2faff] m-0 p-0">
	<Container>
		<div class="flex flex-wrap justify-between items-start">
			<div class="flex items-center w-1/5" id="header-logo">
				<img src="/logo.png" alt="изображение" class="h-16" loading="lazy">
			</div>
			<div class="w-4/5">
				<slot name="navbar">
					<Navbar />
				</slot>
			</div>
		</div>
	</Container>
</header>
<script>
	import Container from './Container.svelte';
	import Navbar from './Navbar.svelte';
</script>


<header class="w-full bg-gray-100 m-0 p-0">
	<Container>
		<div class="flex flex-wrap justify-between items-start">
			<div class="flex items-center w-1/5" id="header-logo">
				<img src="" alt="adasd">
			</div>
			<div class="w-4/5">
				<Navbar list={[
					{ href: "#", text: "О проекте"},
					{ href: "#", text: "Цели"},
					{ href: "#", text: "Условия"},
					{ href: "#", text: "2022"},
					{ href: "#", text: "Хочу участвовать"},
				]} />
			</div>
		</div>
	</Container>
</header>
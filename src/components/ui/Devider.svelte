<script>
    import Container from "../Container.svelte";
    export let url = "/img/waves.svg";
</script>

<section class="relative w-full h-0">
	<Container>
        <div class="absolute bottom-5 left-0 w-3/12">
            <img src={ url } alt="devider" >
        </div>
	</Container>
</section>
<script>
    import Container from "../Container.svelte";
    export let url = "/img/waves.svg";
    export let align = "right";

    const alignVariables = {
        left: " left-0 ",
        left: " right-0 ",
    }
</script>

<section class="hidden lg:inline-block relative w-full h-0">
	<Container>
        <div class="absolute bottom-5 {alignVariables[align] || alignVariables['right']} w-3/12">
            <img src={ url } alt="devider" loading="lazy"/>
        </div>
	</Container>
</section>
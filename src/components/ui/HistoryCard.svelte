<script>
    import Container from "../Container.svelte";
    export let reverse = false;
    export let styles = "w-full h-[500px] bg-gray-100";
</script>

<section class="{styles} h-auto ">
    <div class="w-full h-full flex-1 py-10">
        <Container>
            <div class="flex flex-wrap px-5 lg:px-0 {reverse ? 'flex-row-reverse' : 'flex-row'}">
                <section class="hidden lg:block lg:w-1/3 w-full relative px-4">
                    <slot name="images">
                        <img src="" alt="">
                    </slot>
                </section>
                <section class="lg:w-2/3 w-full">
                    <h2 class="text-xl leading-tight text-blue-700 font-bold text-justify relative">
                        <slot name="title">
                            Заголовок
                        </slot>
                    </h2>
                    <p class="text-lg leading-tight mt-10 text-gray-900 font-light text-justify relative">
                        <slot name="content">
                            Текст Компонента
                        </slot>
                    </p>
                </section>
            </div>
        </Container>
    </div>
</section>
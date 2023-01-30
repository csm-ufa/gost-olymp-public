<script>
    import Target from "./ui/Target.svelte";
</script>
<section class="max-w-8xl mx-auto container dark:bg-gray-900">
    <div>
        <section class="flex flex-wrap lg:flex-nowrap justify-between items-start mt-10">
            <div class="w-full lg:w-2/5">
                <img src="./gif/hello.webp" alt="Hello Friends" loading="lazy">
            </div>
            <div aria-label="group of cards" class="focus:outline-none flex flex-wrap justify-center px-4 w-full lg:w-3/5">
                <h1 class="focus:outline-none text-4xl lg:text-5xl xl:text-6xl font-extrabold text-center leading-10 text-gray-800 dark:text-white w-full mb-10">
                    О проекте
                </h1>
                <p class="text-lg font-regular text-gray-800 text-justify">
                    В 2022 году в рамках Всероссийского проекта «Метрологический образовательный кластер Росстандарта» 
                    впервые состоялась Молодежная олимпиада стандартов. Организатором выступило Федеральное агентство по техническому 
                    регулированию и метрологии (Росстандарт).
                </p>
                <p class="text-lg font-regular text-gray-800 text-justify mt-5">
                    В жюри Олимпиады входят специалисты Министерства промышленности и торговли Российской Федерации, 
                    эксперты технических комитетов по стандартизации, представители бизнес-сообществ и члены Общественного 
                    совета при Росстандарте. 
                </p>
            </div>
        </section>
    </div>
    <div class="py-10" id="targets">
        <h1 class="focus:outline-none mt-10 text-4xl lg:text-5xl xl:text-6xl font-extrabold text-center leading-10 text-gray-800 dark:text-white w-full mb-10">
            Цели
        </h1>
        <div class="lg:flex flex-wrap flex-row items-center">
            <div class="w-full lg:flex flex-row justify-start">
                <Target>
                    <span slot="bg">01</span>
                    <span slot="title">Осведомленность</span>
                    <span slot="text">Способствовать повышению осведомленности общественности о важности стандартизации для качественной, комфортной и безопасной жизни.</span>
                </Target>
            </div>
            <div class="w-full lg:flex flex-row justify-end mt-5">
                <Target>
                    <span slot="bg">02</span>
                    <span slot="title">Развитие</span>
                    <span slot="text">Выявление и развитие творческих способностей и интереса к научной (научно-исследовательской) деятельности, создавая возможность для школьников изучения новых способов в стандартизации.</span>
                </Target>
            </div>
            <div class="w-full lg:flex flex-row justify-start mt-5">
                <Target>
                    <span slot="bg">03</span>
                    <span slot="title">Продвижение</span>
                    <span slot="text">Отбор школьников, проявивших хорошие способности, в состав сборной команды Российской Федерации для участия в международных олимпиадах по стандартизации.</span>
                </Target>
            </div>
        </div>
    </div>
</section>

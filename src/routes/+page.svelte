<script>
	import Container from '../components/Container.svelte';
	import ScrollSlider from '../components/sliders/ScrollSlider.svelte';
    import HistoryCard from "../components/ui/HistoryCard.svelte";
	import HowIsWas from '../components/2022.svelte';
	import Header from '../components/Header.svelte';
	import Navbar from '../components/Navbar.svelte';
	import About from '../components/About.svelte';
	import Devider from '../components/ui/Devider.svelte';
	import SocialMedia from '../components/SocialMedia.svelte';
	import Footer from '../components/Footer.svelte';
	import { onMount } from 'svelte';
	import TermsModal from '../components/modal/Terms.modal.svelte';
	import ImageModal from '../components/modal/Image.modal.svelte';
	import Gallery from '../components/modal/Gallery.modal.svelte';
	import Reviews from '../components/Reviews.svelte';
	import Smi from '../components/Smi.svelte';

	$: modalComponent = TermsModal;
	$: modalShow = false;
	$: zoomImageUrl = null;
	$: modalTitle = "";

	const defaultTitle = "Молодежная Олимпиада Стандартов 2022, г.Уфа, УГАТУ.";

	function linkHandler({detail}){
		if (detail?.action){
			if (detail.action === 'terms') {
				modalShow = true;
				return modalComponent = TermsModal;
			} 

			if (detail.action === 'gallery') {
				modalComponent = Gallery;
				return modalShow = true;
			}
		}
		
	}


	onMount(()=>{
		window.addEventListener('click', ({target}) => {
			if (target.dataset?.zimg) {
				modalComponent = ImageModal;
				zoomImageUrl = target.src;
				modalTitle = target.alt;
				modalShow = true;
			}

			if (target.dataset?.gallery) {
				modalComponent = Gallery;
				modalShow = true;
				return;
			}
		})
	})
</script>


<svelte:component 
	this={ modalComponent }
	props={{ show: modalShow, url: zoomImageUrl, title: modalTitle }} 
	on:close={ ()=> modalShow = false }
/>

<Header>
	<div slot="navbar">
		<Navbar 
			on:link={ linkHandler }
			list={[
				{ href: "#about", text: "О проекте"},
				{ href: "#targets", text: "Цели"},
				{ href: "#history", text: "2022"},
				{ href: "#", text: "Медиатека", action: "gallery" },
				{ href: "#", text: "Хочу участвовать", action: "terms" }
			]} 
		/>
	</div>
</Header>

<section class="w-full bg-gray-100 p-0">
	<div class="w-full relative pb-10 px-6 xl:px-0">
		<img class="absolute w-full inset-0 dark:hidden h-full object-cover object-center" src="/img/hero2-bg.png.webp" alt="we care family" loading="lazy"/>
		<div class="relative z-10 container mx-auto">
			<Container>
				<div class="lg:flex items-center mt-10">
					<div class="w-full lg:w-1/2 h-full">
						<p class="text-[#199ad6] uppercase text-2xl ">
							Всероссийская
						</p>
						<h1  class="text-indigo-700 text-4xl lg:text-6xl font-black mb-8 leading-none">
							Молодежная Олимпиада Стандартов 2023
						</h1>
						<p class="text-[#A21980] dark:text-white font-regular mb-8 text-lg mt-5">
							Объявлен старт Всероссийской олимпиады в рамках проекта «Метрологический образовательный кластер Росстандарта». 
							Проект направлен на продвижение и развитие метрологии и стандартизации как в России, так и во всём мире. 
							Присоединяйся и получай новые знания, друзей 
							<span class="text-indigo-800"> и призы :) </span>
						</p>
					</div>
					<div class="w-full lg:w-1/2 h-full lg:pr-10 xl:pr-0">
						
						<img aria-label="2022" class="mx-auto" src="/img/heroes_image.png.webp"  alt="gost olymp 2022" />
					</div>
				</div>
			</Container>
		</div>
	</div>
</section>

<section class="relative" id="about">
	<Container>
		<Devider/>
		<About/>
	</Container>
</section>

<div class="w-full h-auto mb-40 lg:mb-0 lg:mt-20 relative" id="history">
	<ScrollSlider 
		height="600px" 
		data={[
			{
				component: HowIsWas,
    		},
			{
				component: HistoryCard,
        		styles: `bg-[#f2faff]`,
        		title: `
					На конкурс пришло более 230 заявок из 21 региона страны. Больше всего – из Саратовской области, 
					Республики Башкортостан, Томской и Нижегородской областей. В отборочный тур попали 75 школьников, 
					34 из которых участвовали в финале. 27 школьников приняли участие очно, 7 – онлайн.
				`,
        		content: `
					Финальный этап Молодежной олимпиады стандартов прошел в Уфе 1 июня, в Международный день защиты детей. 
					Организатором мероприятия выступило Федеральное агентство по техническому регулированию и метрологии (Росстандарт), 
					при поддержке Главы Республики Башкортостан и участии Министерства образования и науки Республики Башкортостан, 
					Министерства промышленности, энергетики и инноваций Республики Башкортостан, ФГБОУ ВО УГАТУ. Местом проведения стал 
					Уфимский государственный авиационный технический университет. 
				`,
				images: [
					{ url: '/img/slide_1.1.jpg.webp', alt: defaultTitle },
					{ url: '/img/slide_1.2.jpg.webp', alt: defaultTitle }
				]
    		},
			{
				component: HistoryCard,
        		styles: `bg-[#f2faff]`,
        		title: `
					Накануне мероприятия двухчасовой открытый урок для ребят провел Глава Росстандарта Антон Шалаев. 
                    Руководитель ведомства рассказал о том, как создаются стандарты, о роли России в международной стандартизации.
				`,
        		content: `
					Финальный тур прошел в два этапа: индивидуальное письменное задание и работа в команде. 
                    Первый этап заключался в дополнении и расширении темы отборочного тура «Для чего нужны стандарты?» 
                    с учетом новых знаний, полученных на открытом уроке. Участники в своем эссе должны были ответить на вопросы, 
                    в чем преимущества и недостатки применения стандартов.  По условиям второго этапа, ребятам необходимо было 
                    придумать описание нового международного стандарта, которым будет пользоваться весь мир. 
                    <blockquote class="text-gray-600 relative  text-le font-semibold mt-3 leading-none border-2 border-gray-600 border-dotted rounded-2xl text-left px-5 py-3">
                        Важное условие – стандарт должен быть актуальным, нужным, полезным и новым. 
                    </blockquote>
				`,
				images: [
					{ url: '/img/slide_2.1.jpg.webp', alt: defaultTitle },
					{ url: '/img/slide_2.2.jpg.webp', alt: defaultTitle }
				]
    		},
			{
				component: HistoryCard,
        		styles: `bg-[#f2faff]`,
        		title: `
					По единогласному решению жюри, все 34 участника состязаний объявлены победителями, а семеро ребят вошли в молодежную сборную России по стандартизации: 
                    Назар Бауэр (Благовещенск, Амурская область), Карина Севрюгина (Ковернино, Нижегородская область), Дарья Сурова (Нижний Новгород), Екатерина Сорина (Тольятти), 
					Карина Ищук (Севастополь), Аскар Арсланов (Уфа) и Анастасия Куликова (Саратов).
				`,
        		content: `
					<p>По видеосвязи школьников поздравила сенатор от Башкортостана, председатель комитета Совета Федерации по науке, образованию и культуре Лилия Гумерова. Поздравительный адрес от имени Главы республики Радия Хабирова зачитал министр образования и науки Республики Башкортостан Айбулат Хажин. </p>
				`,
				images: [
					{ url: '/img/slide_3.2.jpg.webp', alt: defaultTitle },
					{ url: '/img/slide_3.1.jpg.webp', alt: defaultTitle }
				]
    		},
			{
				component: HistoryCard,
        		styles: `bg-[#f2faff]`,
        		title: `Ректор УГАТУ Сергей Новиков объявил об учреждении стипендии для каждого участника олимпиады, при условии, что они поступят в этот вуз, в размере 50 тысяч рублей ежемесячно в течение первого семестра обучения. Ребята также получат дополнительные баллы к индивидуальным достижениям: 7 баллов 
                        — все участники, 10 баллов — обладатель приза зрительских симпатий УГАТУ (Даниил Козенко). 
                        Были также вручены призы зрительских симпатий от Роскачества и Ассоциации индустрии детских товаров.
                        Министр промышленности, энергетики и инноваций Республики Башкортостан Александр Шельдяев вручил каждому школьнику благодарность от своего ведомства.
				`,
				content: "",
				images: [
					{ url: '/img/slide_4.1.jpg.webp', alt: defaultTitle },
					{ url: '/img/slide_4.2.jpg.webp', alt: defaultTitle }
				]
    		},
			{
				component: HistoryCard,
        		styles: `bg-[#f2faff]`,
        		title: `
					Наша молодежная сборная в составе семи человек с 24 по 26 августа представляла Россию на 17-ой Международной молодежной олимпиаде стандартов.
				`,
        		content: `
					Это был дебют нашей страны в ежегодном соревновании, которое проводится с 2006 года по инициативе национального органа по стандартизации Южной Кореи 
					(KATS) и направлено на популяризацию среди подростков стандартов, позволяя им открыть для себя весь потенциал инструментов стандартизации. 
					Ребята выступали в старшей возрастной группе. Страну представляли две команды - «Constellation» и «Supernatural». 
					В связи с сохраняющимися в Южной Корее коронавирусными ограничениями мероприятие было проведено в онлайн-формате. 
					И хотя в этом году наша команда не вошла в число победителей, все ребята продемонстрировали хорошие знания, командный дух, испытали массу положительных эмоций и получили замечательный опыт. 
					В завершении мероприятия организаторы пригласили российских школьников участвовать в Олимпиаде и в следующем году. 
				`,
				images: [
					{ url: '/img/slide_5.1.jpg.webp', alt: defaultTitle },
					{ url: '/img/slide_5.2.jpg.webp', alt: defaultTitle }
				]
    		},
		]}
	/>
</div>


<section class="relative">
	<Reviews />
</section>

<section class="relative">
	<Smi />
</section>


<section class="relative">
	<SocialMedia />
</section>


<Footer>
	<div class="font-light text-xs text-gray-800 text-center">
		Федеральное Бюджетное Учреждение <br>
		«Государственный региональный центр стандартизации, метрологии и испытаний <br>им. А.М. Муратшина в Республике Башкортостан» <br><br>
		&copy; 2023
	</div>
</Footer>
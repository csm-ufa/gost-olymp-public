<script>
	import Container from '../components/Container.svelte';
	import ScrollSlider from '../components/sliders/ScrollSlider.svelte';
    import HistoryCard from "../components/ui/HistoryCard.svelte";
	import HowIsWas from '../components/HowIsWas.svelte';
	import Modal from '../components/modal/Modal.svelte';
	import Header from '../components/Header.svelte';
	import Navbar from '../components/Navbar.svelte';
	import About from '../components/About.svelte';
	import Devider from '../components/ui/Devider.svelte';
	import SocialMedia from '../components/SocialMedia.svelte';
	import Footer from '../components/Footer.svelte';

	$: modalShow = false;

	function linkHandler({detail}){
		if (detail?.action && detail.action === 'modal'){
			modalShow = true;
		}
	}
</script>

<Modal 
	on:close={ ()=> modalShow = false }
	show={ modalShow } 
>
	<div slot="title">
		<h2 class="text-gray-700 font-bold text-5xl">Условия участия</h2> 
	</div>
	<div slot="body" class="max-w-5xl">
		<p class="text-xl text-gray-800 py-2.5">
			Школьники оцениваются по различным критериям – понимание темы, творческий подход к решению задач, креативное мышление. 
			Обязательное условие - <b>знание английского языка</b>. <br>
			Принять участие может любой школьник в возрасте от 13 до 18 лет. 
		</p>
		<p class="text-xl text-gray-800 py-2.5">
			<b>Отборочный тур </b> начинается с 20 января и продлится по 1 марта. <br>
			<b>Финальный этап </b> состоится 27 апреля в Нижнем Новгороде. 
		</p>
		<p class="text-xl text-gray-800 py-2.5">
			Для участия необходимо: <br>
			<span class="pl-5">1. заполнить <a href="/docs/anketa.doc" class="text-blue-600 underline"> анкету</a> ;</span><br>
			<span class="pl-5">2. написать эссе на тему: «Для чего нужны стандарты».</span><br>
		</p>
		<p class="text-xl text-gray-800 py-2.5">
			Оба документа отправить на почту  <a href="mailto:olymp@rst.gov.ru" class="text-blue-600 underline">olymp@rst.gov.ru</a>
		</p>
	</div>
</Modal>

<Header>
	<div slot="navbar">
		<Navbar 
			on:link={ linkHandler }
			list={[
				{ href: "#about", text: "О проекте"},
				{ href: "#targets", text: "Цели"},
				{ href: "#history", text: "2022"},
				{ href: "#history", text: "СМИ о нас"},
				{ href: "#", text: "Хочу участвовать", action: "modal" },
			]} 
		/>
	</div>
</Header>

<section class="w-full bg-gray-100 p-0">
	<div class="w-full relative pb-10 px-6 xl:px-0">
		<img class="absolute w-full inset-0 dark:hidden h-full object-cover object-center" src="/img/hero2-bg.png" alt="we care family"/>
		<div class="relative z-10 container mx-auto">
			<Container>
				<div class="lg:flex items-center mt-10">
					<div class="w-full lg:w-1/2 h-full">
						<p tabindex="0" class="text-[#199ad6] uppercase text-2xl ">
							Всероссийская
						</p>
						<h1 tabindex="2" class="text-indigo-700 text-4xl lg:text-6xl font-black mb-8 leading-none">
							Молодежная Олимпиада Стандартов 2023
						</h1>
						<p tabindex="0" class="text-[#A21980] dark:text-white font-regular mb-8 text-lg mt-5">
							Объявлен старт Всероссийской олимпиады в рамках проекта «Метрологический образовательный кластер Росстандарта». Проект направлен на продвижение и развитие метрологии и стандартизации как в Росии так и во всём мире. Присоединяйся и получай новые знания, друзей 
							<span class="text-indigo-800">и призы :)</span>
						</p>
					</div>
					<div class="w-full lg:w-1/2 h-full lg:pr-10 xl:pr-0">
						
						<img tabindex="0" role="img" aria-label="people smiling" class="mx-auto" src="/img/heroes_image.png"  alt="people smiling"/>
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

<div class="w-full h-auto mt-20 relative" id="history">
	<ScrollSlider 
		height="600px" 
		data={[
			{
				component: HowIsWas,
    		},
			{
				component: HistoryCard,
        		styles: `bg-gray-50`,
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
    		},
			{
				component: HistoryCard,
        		styles: `bg-blue-50`,
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
    		},
			{
				component: HistoryCard,
        		styles: `bg-green-50`,
        		title: `
					По единогласному решению жюри, все 34 участника состязаний объявлены победителями, а семеро ребят вошли в молодежную сборную России по стандартизации: 
                    Назар Бауэр (Благовещенск, Амурская область), Карина Севрюгина (Ковернино, Нижегородская область), Дарья Сурова (Нижний Новгород), Екатерина Сорина (Тольятти), 
					Карина Ищук (Севастополь), Аскар Арсланов (Уфа) и Анастасия Куликова (Саратов).
				`,
        		content: `
					<p>По видеосвязи школьников поздравила сенатор от Башкортостана, председатель комитета Совета Федерации по науке, образованию и культуре Лилия Гумерова. Поздравительный адрес от имени Главы республики Радия Хабирова зачитал министр образования и науки Республики Башкортостан Айбулат Хажин. </p>
                    <p>Ректор УГАТУ Сергей Новиков объявил об учреждении стипендии для каждого участника олимпиады, при условии, что они поступят в этот вуз, в размере 50 тысяч рублей ежемесячно в течение первого семестра обучения. Ребята также получат дополнительные баллы к индивидуальным достижениям: 7 баллов 
                        — все участники, 10 баллов — обладатель приза зрительских симпатий УГАТУ (Даниил Козенко). 
                        Были также вручены призы зрительских симпатий от Роскачества и Ассоциации индустрии детских товаров.
                        Министр промышленности, энергетики и инноваций Республики Башкортостан Александр Шельдяев вручил каждому школьнику благодарность от своего ведомства.
                    </p>
				`,
    		},
			{
				component: HistoryCard,
        		styles: `bg-yellow-50`,
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
    		},
		]}
	/>
</div>

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
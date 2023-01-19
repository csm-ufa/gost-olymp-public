<script>
	import Container from "./Container.svelte";
	export let images = [
		'https://i.ibb.co/McW2r4N/Group-178.png',
		'https://i.ibb.co/McW2r4N/Group-1775.png',
		'https://i.ibb.co/McW2r4N/Group-1776.png',
		'https://i.ibb.co/McW2r4N/Group-1778.png',
		'https://i.ibb.co/McW2r4N/Group-182.png',
		'https://i.ibb.co/McW2r4N/Group-183.png',
		'https://i.ibb.co/McW2r4N/Group-184.png',
		'https://i.ibb.co/McW2r4N/Group-185.png',
		'https://i.ibb.co/McW2r4N/Group-186.png',
		'https://i.ibb.co/McW2r4N/Group-187.png',
		'https://i.ibb.co/McW2r4N/Group-1.png',
		'https://i.ibb.co/McW2r4N/Group-178.png',
	]
</script>
<div class="py-10">
	<Container>
		<div class="container mx-auto">
			<div class="flex flex-col lg:flex-row justify-between items-center py-10">
				<div class="lg:w-1/2 flex flex-col justify-between items-center lg:items-start">
					<h1 class="text-3xl lg:text-4xl xl:text-6xl font-bold text-gray-800 dark:text-white text-center lg:text-left">
						Как это было в 
						<span class="text-6xl text-yellow-500">2022</span>
					</h1>
					<p class="text-xl leading-normal text-indigo-600 dark:text-gray-200 mt-5 md:w-8/12 lg:w-11/12 text-center lg:text-left">
						Это было весело, внезапно и ... <br>
						хорошо организованно :) <br>
						Рассказываем как это было в прошлом году <br>
					</p>
					<span class="font-black mt-10 text-3xl flex flex-nowrap justify-center w-full">
						<span class="text-indigo-200">⟶ &nbsp; </span>
						<span class="text-indigo-500">⟶ &nbsp; </span>
						<span class="text-indigo-900">⟶ </span>
					</span>
					<!-- <div class="w-full flex justify-center lg:justify-start">
						<button
							class="bg-indigo-700 text-base font-medium text-white rounded-3xl text-center py-5 px-9 mt-8 lg:mt-12 hover:bg-indigo-600 leading-4 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-700 w-full sm:w-auto"
						>
							Смотреть Фотоотчет
						</button>
					</div> -->
				</div>
				<div role="list" class="lg:w-1/2">
					<img src="/gif/preview-animation.webp" alt="2022" class="rounded-2xl h-full w-full">
				</div>
			</div>
		</div>
    </Container>    
</div>

<div class="relative h-auto py-5">
    <div class="absolute top-0 left-0 font-bold text-5xl lg:text-[96px] xl:text-[172px] text-indigo-600 leading-none z-0 opacity-20 font-sans">
        <slot name="bg">00</slot>
    </div>
    <div class="relative z-20 top-10 left-12">
        <h3 class="text-gray-700 font-bold text-3xl mb-1">
            <slot name="title">Заголовок</slot>
        </h3>
        <p class="max-w-lg">
            <slot name="text">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio fugiat modi illo aspernatur, facere repellendus aliquam sit. Eos, voluptatum eum, veritatis, et saepe molestiae velit illum quos nemo repellendus itaque!
            </slot>
        </p>
    </div>
</div>
<script setup>
import { ref,reactive, onMounted } from "vue";
import { useUtils } from "@composables/useUtils";

const appUseUtils = reactive(useUtils());

const sections = ref([
    {
        itemImageSrc: '3-simple.png',
        alt: 'craftalia',
        title: 'Artículos de madera, Papeleria y accesorios',
        subtitle: 'Descubre nuestra colección de artículos de madera y papelería hechos a mano.'
    }, {
        itemImageSrc: 'cuadro-peonia.png',
        alt: 'cuadro-peonias',
        title: 'Cuadro Peonias de Madera',
        subtitle: 'Añade un toque rústico y elegante a tu hogar con nuestros cuadros únicos, hechos a mano perfectos para cualquier espacio y ocasión especial. ¡Descubre la belleza de la artesanía!'
    },{
        itemImageSrc: 'banner-cerezo.png',
        alt: 'pin-cerezo',
        title: 'Pin transparente de cerezo',
        subtitle: 'Exprésate con estilo con nuestro Pin Artesanal que da un toque único y colorido a cualquier atuendo. Añade un detalle divertido y único a tu look con estos pines artesanales. ¡Ideales para cualquier ocasión!'
    }
]);
const activeSection = ref(0)
const setActive = (index) => {
  let active = index;

  if (index === sections.value.length) active = 0;
  else if (index === -1) active = sections.value.length - 1;

  activeSection.value = active;
};

const myFn = () => {setActive(activeSection.value +1);}

let myTimer = setInterval(myFn, 5000);

const resetCarousel = () => {
    clearInterval(myTimer);
    myTimer = setInterval(myFn, 5000);
}



</script>

<template>
<div class="pattern bg-amber-50">
    <div class="container flex flex-col px-6 py-4 mx-auto space-y-6 lg:h-[32rem] lg:py-16 lg:flex-row lg:items-center lg:text-left text-center">
        <div :class="{'lg:w-1/2': activeSection}" class="flex flex-col justify-center w-full lg:flex-row lg:order-1  order-2 mt-5">
            <div v-if="activeSection" class="max-w-lg sm:mx-auto lg:mx-12">
                <h3 class=" text-amber-600 mb-2 text-matcha">Nuevos Artículos</h3>
                <h1 class="text-3xl font-semibold tracking-wide text-amber-900 dark:text-white lg:text-4xl">{{sections[activeSection].title}}</h1>
                <p class="mt-4 text-gray-600 dark:text-gray-300">{{ sections[activeSection].subtitle }}</p>
                <div class="mt-6">
                    <a href="#" class="px-6 py-2.5 mt-6 text-sm font-semibold leading-5 text-center text-white capitalize bg-amber-600 rounded-full hover:bg-amber-500 lg:mx-0 lg:w-auto focus:outline-none">Ver {{ sections[activeSection].title  }}</a>
                </div>
            </div>

            <div v-else class=" text-center lg:mx-12">
                <Image :src="appUseUtils.getImgUrl(sections[activeSection].itemImageSrc)" alt="Image" width="150" />
                <h1 class="text-3xl font-semibold tracking-wide text-amber-900 dark:text-white lg:text-4xl">{{sections[activeSection].title}}</h1>
                <p class="mt-4 text-gray-600 dark:text-gray-300">{{ sections[activeSection].subtitle }}</p>
                <div class="mt-6">
                    <a href="#" class="px-6 py-2.5 mt-6 text-sm font-semibold leading-5 text-center text-white capitalize bg-amber-950 rounded-full hover:bg-amber-900 lg:mx-0 lg:w-auto focus:outline-none">Ver todos los artículos</a>
                </div>
            </div>
        </div>

        <div v-if="activeSection" class="flex items-center justify-center w-full lg:h-96 md:96 h-44 lg:w-1/2 lg:order-2  order-1">
            <img class="object-cover h-full max-w-2xl" :src="appUseUtils.getImgUrl(sections[activeSection].itemImageSrc)" :alt="sections[activeSection].alt">
        </div>
    </div>
    <div class="flex justify-center mt-6 lg:mt-0 space-x-3">
        <button 
            v-for="(items, idx) in sections" :key="idx"  
            :class="[activeSection == idx ? 'bg-amber-500' : 'bg-gray-300 hover:bg-amber-500']"
            @click="setActive(idx),resetCarousel()"
            class="w-8 h-2 rounded-md mb-3 lg:mx-0 focus:outline-none" ></button>
    </div>
    <div class="bg-amber-900 py-4">
        <div class="flex flex-row justify-around space-x-10 text-white">
            <div class="text-center">
                <i class="pi pi-truck"></i>
                <p class="text-sm font-thin">Envios a todo México</p>
            </div>
            <div class="text-center">
                <i class="pi pi-hammer" style="font-size: 1.5rem"></i>
                <p class="text-matcha">Hecho a mano</p>
            </div>
            <div class="text-center">
                <i class="pi pi-gift" style="font-size: 1.5rem"></i>
                <p class="text-matcha">Personalizado</p>
            </div>
        </div>
    </div>
</div>

</template>

<style>
    .pattern {
        background-image: url(../assets/banner-craft.png);
        background-position: center center;
        background-repeat: no-repeat;
        background-size: cover;
        position: relative;
        padding: 0;
    }
</style>



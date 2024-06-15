
<template>
    <div class="py-20">
        <div class="mx-auto max-w-7xl px-6 lg:px-8">
        <div class="mx-auto max-w-2xl lg:text-center">
          <h2 class="text-center text-base leading-7 text-amber-600 text-matcha">¿No sabes por donde comenzar?</h2>
          <p class="text-center mt-2 text-3xl font-bold tracking-tight text-amber-900 sm:text-4xl">¡Explora nuestras Categorías!</p>
          <!-- <p class="mt-4 text-lg leading-8 text-gray-600">Al elegir productos hechos a mano .</p> -->
        </div>
        <div class="mx-auto mt-8">
            <Carousel :value="products" :numVisible="3" :numScroll="1" :showIndicators="false" :responsiveOptions="responsiveOptions" circular :autoplayInterval="3000">
                <template #item="slotProps">
                    <a href="">
                        <div class="bg-white border surface-border rounded-lg m-2 hover:opacity-75 ">
                            <div class="mb-3">
                                <div class="relative mx-auto">
                                    <img :src="appUseUtils.getImgUrl(slotProps.data.image)" :alt="slotProps.data.name" class="w-full  rounded-t-lg" />
                                    <Tag v-if="slotProps.data.new" value="NUEVOS ARTÍCULOS" severity="success" class="absolute" style="left:5px; top: 5px"/>
                                </div>
                            </div>
                            <div class="text-center">
                                <h4 class="mt-8 text-amber-600 text-matcha">{{ slotProps.data.description }}</h4>
                                <h2 class="mb-8 mt-1 text-xl font-bold uppercase text-amber-900">{{ slotProps.data.name }}</h2>
                            </div>
                        </div>
                    </a>
                </template>
            </Carousel>
        </div>
        <div class="mx-auto mt-6 text-center">
            <a href="#" class="px-6 py-2.5 text-sm font-semibold leading-5 text-center text-white capitalize bg-amber-950 rounded-full hover:bg-amber-900 lg:mx-0 lg:w-auto focus:outline-none">
                Ver todos los artículos
            </a>
        </div>
      </div>
    </div> 
</template>

<script setup>
import { ref, reactive } from "vue";
import { useUtils } from "@composables/useUtils";

const appUseUtils = reactive(useUtils());

const products = ref([
{
    id: '1',
    name: 'Colguijes',
    description: 'De madera, plastico o acrílico',
    image: 'productos/colguije-nutria.png',
    new: true,
},{
    id: '2',
    name: 'Letreros',
    description: 'De madera de videojuegos, negocios, evetos',
    image: 'productos/letrero-madera.png',
    new: true,
},{
    id: '3',
    name: 'Social',
    description: "Invitaciones, menus, etiquetas",
    image: 'productos/social.png',
    new: false,
},{
    id: '4',
    name: 'Etiquetas',
    description: 'Escolares, negocio, empaques, social',
    image: 'productos/stickers.jpg',
    new: false,
},{
    id: '5',
    name: 'Sellos',
    description: 'Para tarjetas, empaques o papeleria',
    image: 'productos/sellos.png',
    new: false,
},{
    id: '6',
    name: 'Todos los productos',
    description: 'Papeleria, accesorios y mas',
    image: 'productos/todos.png',
    new: false,
},
]);
const responsiveOptions = ref([
    {
        breakpoint: '1400px',
        numVisible: 3,
        numScroll: 1
    },
    {
        breakpoint: '1199px',
        numVisible: 3,
        numScroll: 1
    },
    {
        breakpoint: '767px',
        numVisible: 2,
        numScroll: 1
    },
    {
        breakpoint: '575px',
        numVisible: 1,
        numScroll: 1
    }
]);

</script>

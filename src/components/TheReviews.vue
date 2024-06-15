<script setup>
import { ref, reactive } from "vue";
import { useUtils } from "@composables/useUtils";

const appUseUtils = reactive(useUtils());

const products = ref([
{
    id: '1',
    image:'default',
    name: 'José de San Luis Rio Colorado',
    product: 'Llavero de acrilíco',
    review: "Siempre busco regalos únicos y craftalia nunca me decepciona. Sus productos personalizados son la elección perfecta para ocaciones especiales",
    rate:5,
},{
    id: '2',
    image:'default',
    name: 'Francisco de Hermosillo',
    product: 'Cuadro madera - PXNDA',
    review:"No puedo expresar lo feliz que estoy con mi cuadro de PXNDA. ¡Gracias por esto tan sifnigicativo!",
    rate:4,
},{
    id: '3',
    image:'default',
    name: 'Claudia de San Luis Rio Colorado',
    product: 'Stickers para negocio',
    review:"Muchas gracias a craftalia por su atención y servicio en las etiquetas, pronto pedire más",
    rate:5,
}
,{
    id: '4',
    image:'default',
    name: 'Alejandro de San Luis Rio Colorado',
    product: 'Placa Anime - One Piece',
    review: "El Equipo de Craftalia es increible. Me ayudaron a crear el regalo perfecto para el aniversario de mi pareja.",
    rate:5,
},
]);
const responsiveOptions = ref([
    {
        breakpoint: '1400px',
        numVisible: 1,
        numScroll: 1
    },
    {
        breakpoint: '1199px',
        numVisible: 1,
        numScroll: 1
    },
    {
        breakpoint: '767px',
        numVisible: 1,
        numScroll: 1
    },
    {
        breakpoint: '575px',
        numVisible: 1,
        numScroll: 1
    }
]);

</script>

<template>
    <div class="py-20">
        <div class="mx-auto max-w-7xl px-6 lg:px-8">
            <div class="mx-auto max-w-2xl lg:text-center">
            <h2 class="text-center text-base leading-7 text-amber-600 text-matcha">Comentarios de nuestros clientes:</h2>
            <p class="text-center mt-2 text-3xl font-bold tracking-tight text-amber-900 sm:text-4xl">Testimonios y Reseñas</p>
            <!-- <p class="mt-4 text-lg leading-8 text-gray-600">Al elegir productos hechos a mano .</p> -->
            </div>
            <div class="mx-auto">
                <Carousel :value="products" :numVisible="1" :numScroll="1" :showNavigators="false" :showIndicators="false" orientation="vertical" :autoplayInterval="5000" verticalViewPortHeight="330px" contentClass="flex align-items-center">
                    <template #item="slotProps">
                        <div class="max-w-screen-xl px-4 py-8 mx-auto text-center lg:py-16 lg:px-6">
                            <figure class="max-w-screen-md mx-auto">
                                <svg class="h-12 mx-auto mb-3 text-gray-300" viewBox="0 0 24 27" fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path d="M14.017 18L14.017 10.609C14.017 4.905 17.748 1.039 23 0L23.995 2.151C21.563 3.068 20 5.789 20 8H24V18H14.017ZM0 18V10.609C0 4.905 3.748 1.038 9 0L9.996 2.151C7.563 3.068 6 5.789 6 8H9.983L9.983 18L0 18Z" fill="currentColor"/>
                                </svg> 
                                <blockquote>
                                    <p class="text-2xl font-medium text-gray-900 dark:text-white">"{{ slotProps.data.review }}"</p>
                                </blockquote>
                                <figcaption class="flex items-center justify-center mt-6 space-x-3">
                                    <img class="w-6 h-6 rounded-full" src="../assets/logo-monita.png" alt="profile picture">
                                    <div class="flex items-center divide-x-2 divide-gray-500 dark:divide-gray-700">
                                        <div class="pr-3 font-medium text-gray-900 dark:text-white">{{ slotProps.data.product }}</div><br>
                                        <div class="pl-3 text-sm font-light text-gray-500 dark:text-gray-400">{{ slotProps.data.name }}</div>
                                    </div>
                                </figcaption>
                            </figure>
                        </div>
                    </template>
                </Carousel>
            </div>
        </div>
    </div>
</template>

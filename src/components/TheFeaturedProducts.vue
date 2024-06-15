
<template>  
    <div class="py-20">
        <div class="mx-auto max-w-7xl px-6 lg:px-8">
        <div class="mx-auto max-w-2xl lg:text-center">
          <h2 class="text-center text-base leading-7 text-amber-600 text-matcha">¡Los más populares!</h2>
          <p class="text-center mt-2 text-3xl font-bold tracking-tight text-amber-900 sm:text-4xl">Descubre la magia de lo hecho a mano</p>
          <!-- <p class="mt-4 text-lg leading-8 text-gray-600">Al elegir productos hechos a mano .</p> -->
        </div>
        <div class="mx-auto mt-8">
            <Carousel :value="products" :numVisible="3" :numScroll="1" :responsiveOptions="responsiveOptions">
                <template #item="slotProps">
                    <div class="bg-white border surface-border rounded-lg m-2 p-3">
                        <div class="mb-3">
                            <div class="relative mx-auto">
                                <img :src="appUseUtils.getImgUrl(slotProps.data.image)" :alt="slotProps.data.name" class="w-full border-round" />
                                <Tag v-if="slotProps.data.new" value="NUEVO" severity="success" class="absolute" style="left:5px; top: 5px"/>
                            </div>
                        </div>
                        <div class="mb-2 text-sm font-light text-gray-400">{{ slotProps.data.category }}</div>
                        <div class="mb-1 text-matcha font-medium text-amber-600">{{ slotProps.data.name }}</div>
                        <div class="mb-5 font-semibold text-xl">${{ slotProps.data.price }}</div>
                        <div class="flex">
                            <Button icon="pi pi-eye" severity="secondary" rounded outlined />
                            <a href="#" class="px-6 py-2.5 text-sm ml-2 w-full font-semibold leading-5 text-center text-white bg-amber-600 rounded-lg hover:bg-amber-500 focus:outline-none">
                                <i class="pi pi-cart-plus"></i> Agregar al carrito
                            </a>
                        </div>
                    </div>
                </template>
            </Carousel>
        </div>
        <div class="mx-auto mt-6 text-center">
            <a href="#" class="px-6 py-2.5 text-sm font-semibold leading-5 text-center text-white capitalize bg-amber-950 rounded-full hover:bg-amber-900 lg:mx-0 lg:w-auto focus:outline-none">
                Ver Los mas vendidos
            </a>
        </div>
      </div>
    </div> 
</template>

<script setup>
import { ref, reactive } from "vue";
import { useUtils } from "@composables/useUtils";

const appUseUtils = reactive(useUtils());

const value = ref(3);

const products = ref([
{
    id: '1',
    category:'Colguijes',
    name: 'Colguije duo - Nutrias',
    image: 'productos/colguije-nutria.png',
    price:"120.00",
    rate:5,
    new: true,
},{
    id: '2',
    category:'Letreros',
    name: 'Letrero Videojuegos - Animal Crossing',
    image: 'productos/letrero-madera.png',
    price:"400.00",
    rate:4,
    new: false,
},{
    id: '3',
    category:'Letreros',
    name: 'Letreros Negocio - Letrero con iman',
    image: 'productos/letrero-iman.png',
    rate:5,
    price:"300.00",
    new: true,
}
,{
    id: '4',
    category:'Letreros',
    name: 'Letreros QR mini - QR Instagram con iman',
    image: 'productos/letrero-qr-iman.png',
    rate:5,
    price:"150.00",
    new: true,
},
]);
const responsiveOptions = ref([
  {
    breakpoint: '1400px',
    numVisible: 3,
    numScroll: 1,
  },
  {
    breakpoint: '1199px',
    numVisible: 3,
    numScroll: 1,
  },
  {
    breakpoint: '767px',
    numVisible: 2,
    numScroll: 1,
  },
  {
    breakpoint: '575px',
    numVisible: 1,
    numScroll: 1,
  },
]);




</script>

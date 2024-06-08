
<template>
    <div class="py-20 bg-amber-50">
        <div class="mx-auto max-w-7xl px-6 lg:px-8">
        <div class="mx-auto max-w-2xl lg:text-center">
          <h2 class="text-center text-base leading-7 text-amber-600 text-matcha">¡Los más populares!</h2>
          <p class="text-center mt-2 text-3xl font-bold tracking-tight text-amber-900 sm:text-4xl">Descubre la magia de lo hecho a mano</p>
          <!-- <p class="mt-4 text-lg leading-8 text-gray-600">Al elegir productos hechos a mano .</p> -->
        </div>
        <div class="mx-auto mt-8">
            <Carousel :value="products" :numVisible="3" :numScroll="1" :responsiveOptions="responsiveOptions">
                <template #item="slotProps">
                    <div class="bg-white border surface-border rounded-lg hover:opacity-75 m-2 p-3">
                        <div class="mb-3">
                            <div class="relative mx-auto">
                                <img :src="appUseUtils.getImgUrl(slotProps.data.image)" :alt="slotProps.data.name" class="w-full border-round" />
                                <Tag :value="slotProps.data.inventoryStatus" :severity="getSeverity(slotProps.data.inventoryStatus)" class="absolute" style="left:5px; top: 5px"/>
                            </div>
                        </div>
                        <div class="mb-3 font-medium">{{ slotProps.data.name }}</div>
                        <Rating class="mb-3" v-model="value" readonly :cancel="false" />
                        <div class="mb-3 mt-0 font-semibold text-xl">${{ slotProps.data.price }}</div>
                        <div class="flex justify-between align-items-center">
                            <Button icon="pi pi-heart" severity="secondary" outlined />
                            <Button icon="pi pi-shopping-cart" class="ml-2"/>
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
    name: 'Llaveros y pins',
    description: 'Accesorios, llaveros, pines',
    image: 'productos/llavero-nutria.png',
    price:"200",
    inventoryStatus: "INSTOCK",
},{
    id: '2',
    name: 'Letreros',
    description: 'Letreros, cuadros, placas de madera',
    image: 'productos/letrero-madera.png',
    price:"200",
    inventoryStatus: "INSTOCK",
},{
    id: '3',
    name: 'Social',
    description: "Invitaciones, gafetes, menus",
    image: 'productos/social.png',
    price:"200",
    inventoryStatus: 'INSTOCK',
},{
    id: '4',
    name: 'Stickers',
    description: 'Escolares, negocio, empaques',
    image: 'productos/stickers.jpg',
    price:"200",
    inventoryStatus: 'INSTOCK',
},{
    id: '5',
    name: 'Sellos',
    description: 'Sellos para empaques o papeleria',
    image: 'productos/sellos.png',
    price:"200",
    inventoryStatus: 'INSTOCK',
},{
    id: '6',
    name: 'Todos los productos',
    description: 'Papeleria, accesorios y mas',
    image: 'productos/todos.png',
    price:"200",
    inventoryStatus: 'INSTOCK',
},
]);
const responsiveOptions = ref([
    {
        breakpoint: '1400px',
        numVisible: 2,
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

const getSeverity = (status) => {
    switch (status) {
        case 'INSTOCK':
            return 'success';

        case 'LOWSTOCK':
            return 'warning';

        case 'OUTOFSTOCK':
            return 'danger';

        default:
            return null;
    }
};



</script>

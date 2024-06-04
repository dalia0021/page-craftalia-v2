
<template>
    <div class="py-20 bg-amber-50">
        <div class="mx-auto max-w-7xl px-6 lg:px-8">
        <div class="mx-auto max-w-2xl lg:text-center">
          <h2 class="text-center text-base leading-7 text-amber-600 text-matcha">¡Bienvenido a craftalia!</h2>
          <p class="text-center mt-2 text-3xl font-bold tracking-tight text-amber-900 sm:text-4xl">¡Explora nuestras categorias!</p>
          <!-- <p class="mt-4 text-lg leading-8 text-gray-600">Al elegir productos hechos a mano .</p> -->
        </div>
        <div class="mx-auto mt-8">
            <Carousel :value="products" :numVisible="3" :numScroll="1" :responsiveOptions="responsiveOptions">
            <template #item="slotProps">
                <div class="bg-white border surface-border rounded-lg m-2  p-3">
                    <div class="mb-3">
                        <div class="relative mx-auto">
                            <img :src="appUseUtils.getImgUrl(slotProps.data.image)" :alt="slotProps.data.name" class="w-full border-round" />
                            <Tag :value="slotProps.data.inventoryStatus" :severity="getSeverity(slotProps.data.inventoryStatus)" class="absolute" style="left:5px; top: 5px"/>
                        </div>
                    </div>
                    <div class="text-center">
                        <h2 class="my-8 text-xl font-semibold uppercase text-amber-900">{{ slotProps.data.name }}</h2>
                    </div>
                </div>
            </template>
        </Carousel>
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
    id: '1000',
    name: 'Papeleria',
    description: 'Cuadernos, Stickers y mas',
    image: 'productos/cuaderno-chico.png',
    status: 'Nuevo',
},{
    id: '1002',
    code: 'f230fh0g3',
    name: 'Bamboo Watch',
    description: 'Product Description',
    image: 'productos/cuaderno-chico.png',
    price: 65,
    category: 'Accessories',
    quantity: 24,
    inventoryStatus: 'INSTOCK',
    rating: 5
},{
    id: '1003',
    code: 'f230fh0g3',
    name: 'Bamboo Watch',
    description: 'Product Description',
    image: 'productos/cuaderno-chico.png',
    price: 65,
    category: 'Accessories',
    quantity: 24,
    inventoryStatus: 'INSTOCK',
    rating: 5
},{
    id: '1004',
    code: 'f230fh0g3',
    name: 'Bamboo Watch',
    description: 'Product Description',
    image: 'productos/cuaderno-chico.png',
    price: 65,
    category: 'Accessories',
    quantity: 24,
    inventoryStatus: 'INSTOCK',
    rating: 5
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
        case 'Nuevo':
            return 'success';

        case 'LOWSTOCK':
            return 'warning';

        case 'OUTOFSTOCK':
            return 'danger';

        default:
            return "null";
    }
};
</script>

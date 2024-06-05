<template>
    <div class="bg-white py-20">
      <div class="mx-auto max-w-7xl px-6 lg:px-8">
        <div class="mx-auto max-w-2xl lg:text-center">
          <h2 class="text-center text-base leading-7 text-amber-600 text-matcha">¡Bienvenido a Craftalia!</h2>
          <p class="text-center mt-2 text-3xl font-bold tracking-tight text-amber-900 sm:text-4xl">¿Por Qué Elegir Artículos Hechos a Mano?</p>
          <!-- <p class="mt-4 text-lg leading-8 text-gray-600">Al elegir productos hechos a mano .</p> -->
        </div>
        <div class="mx-auto mt-8">
          <dl class="flex flex-col lg:flex-row lg:space-x-10"> 
            <div  v-for="(item, idx) in servicios" :key="idx"  
                class="text-center p-6 space-y-3">
                <span class="inline-block text-amber-500 dark:text-amber-400">
                   <component :is="item.icon" class="h-10 w-10" aria-hidden="true" />
                </span>

                <h1 class="text-xl font-semibold text-gray-700 dark:text-white">{{item.name}}</h1>

                <p class="text-gray-500 dark:text-gray-300">
                    {{item.desc}}
                </p>
            </div>
          </dl>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from "vue";
  import { GiftIcon, HeartIcon, SparklesIcon } from '@heroicons/vue/24/outline'

  const servicios = ref([
    {
        name:"Calidad y Cuidado",
        desc:"Elaborados cuidadosamente y con atencion a cada detalle. Para que asi puedas obtener un producto con calidad.",
        icon: SparklesIcon
    },{
        name:"Regalos Significativos",
        desc:"Cada pieza es creada con amor y cariño, mostrandoles a tus seres queridos cuánto te importan con un detalle especial.",
        icon:GiftIcon
    }, {
        name:"Apoyo a la Artesania",
        desc:"Al elegir productos hechos a mano, estás contribuyendo a crear y mantener a los pequeños negocios",
        icon:HeartIcon
    }
  ])
  
 
  </script>
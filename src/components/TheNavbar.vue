
<script setup>
import { ref, reactive } from 'vue'
import {
  Dialog,
  DialogPanel,
  Popover,
  PopoverButton,
  PopoverGroup,
  PopoverPanel,
  Tab,
  TabGroup,
  TabList,
  TabPanel,
  TabPanels,
  TransitionChild,
  TransitionRoot,
} from '@headlessui/vue'
import { Bars3Icon, MagnifyingGlassIcon, ShoppingBagIcon, XMarkIcon } from '@heroicons/vue/24/outline'
import { useUtils } from "@composables/useUtils";

const appUseUtils = reactive(useUtils());

const navigation = {
  categories: [
    {
      id: 'papeleria',
      name: 'Papeleria',
      featured: [
        {
          name: 'Nuevo Lanzamiento',
          href: '#',
          imageSrc: 'productos/social.png',
          imageAlt: 'Notepad de gran dannes',
        },
        {
          name: 'Notepad Grand danés',
          href: '#',
          imageSrc: 'productos/note-pad-gran-danes-01-2.png',
          imageAlt: 'stickers escolares grandes',
        },
      ],
      sections: [
        {
          id: 'Etiquetas',
          name: 'Etiquetas',
          items: [
            { name: 'Pack regreso a clases', href: '#' },
            { name: 'Etiquetas para negocio', href: '#' },
            { name: 'Etiquetas para escuela', href: '#' },
            { name: 'Etiquetas sociales', href: '#' },
            { name: 'Ver todo', href: '#' },
          ],
        },
        {
          id: 'cuadernos',
          name: 'Cuadernos y Notepads',
          items: [
            { name: 'Cuadernos', href: '#' },
            { name: 'Libretas', href: '#' },
            { name: 'Notepads', href: '#' },
            { name: 'Ver todo', href: '#' },
          ],
        },        
        {
          id: 'sellos',
          name: 'Sellos',
          items: [
            { name: 'Sellos para tarjetas', href: '#' },
            { name: 'Sellos para papeleria', href: '#' },
            { name: 'Sellos para empaques', href: '#' },
            { name: 'Ver todo', href: '#' },
          ],
        },
        {
          id: 'social',
          name: 'Social',
          items: [
            { name: 'Money Holders', href: '#' },
            { name: 'Candy Box', href: '#' },
            { name: 'Menus', href: '#' },
            { name: 'Invitaciones', href: '#' },
            { name: 'Etiquetas', href: '#' },
            { name: 'Ver todo', href: '#' },
          ],
        },
        {
          id: 'marcapaginas',
          name: 'Marca Paginas',
          items: [
            { name: 'Plastico', href: '#' },
            { name: 'Madera', href: '#' },
            { name: 'Ver todo', href: '#' },
          ],
        },
      ],
    },
    {
      id: 'accesorios',
      name: 'Accesorios',
      featured: [
        {
          name: 'Nuevos Lanzamientos',
          href: '#',
          imageSrc: 'productos/llavero-nutria.png',
          imageAlt: 'llaveros de madera',
        },
        {
          name: 'Llavero Zelda y Link',
          href: '#',
          imageSrc: 'productos/llavero-zelda-link-01.png',
          imageAlt: 'llavero de pastico zelda',
        },
      ],
      sections: [
        {
          id: 'llaveros',
          name: 'Llaveros y Colguijes',
          items: [
            { name: 'Llaveros de Plástico', href: '#' },
            { name: 'Llaveros de Madera', href: '#' },
            { name: 'Llaveros de Acrílico', href: '#' },
            { name: 'Ver todo', href: '#' },
          ],
        },
        {
          id: 'colguijes',
          name: 'Colguijes',
          items: [
            { name: 'Colguijes de Plástico', href: '#' },
            { name: 'Colguijes de Madera', href: '#' },
            { name: 'Colguijes de Acrílico', href: '#' },
            { name: 'Ver todo', href: '#' },
          ],
        },
        {
          id: 'pines',
          name: 'Pines',
          items: [
            { name: 'Pines de Plástico', href: '#' },
            { name: 'Pines de Madera', href: '#' },
            { name: 'Pines de Acrílico', href: '#' },
            { name: 'Ver todo', href: '#' },
          ],
        },
        {
          id: 'aretes',
          name: 'Aretes',
          items: [
            { name: 'Aretes de Plástico', href: '#' },
            { name: 'Aretes de Madera', href: '#' },
            { name: 'Ver todo', href: '#' },
          ],
        },
        {
          id: 'joyeros',
          name: 'Joyeros',
          items: [
            { name: 'Cajitas', href: '#' },
            { name: 'Stands', href: '#' },
            { name: 'Ver todo', href: '#' },
          ],
        },
      ],
    },
    {
      id: 'otros',
      name: 'Otros',
      featured: [
        {
          name: 'Nuevos Lanzamientos',
          href: '#',
          imageSrc: 'productos/letrero-madera.png',
          imageAlt: 'llaveros de madera',
        },
        {
          name: 'Cuadro de peonias',
          href: '#',
          imageSrc: 'productos/cuadro-peonias.png',
          imageAlt: 'llavero de pastico zelda',
        },
      ],
      sections: [
        {
          id: 'placas',
          name: 'Placas y Cuadros',
          items: [
            { name: 'Anime', href: '#' },
            { name: 'Musica', href: '#' },
            { name: 'Videojuegos', href: '#' },
            { name: 'Cine', href: '#' },
            { name: 'Casa', href: '#' },
            { name: 'Otros', href: '#' },
            { name: 'Ver todo', href: '#' },
          ],
        },
        {
          id: 'letreros',
          name: 'Letreros',
          items: [
            { name: 'Bebes y niños', href: '#' },
            { name: 'Negocio', href: '#' },
            { name: 'Eventos', href: '#' },
            { name: 'Otros', href: '#' },
            { name: 'Ver todo', href: '#' },
          ],
        },
        {
          id: 'portaretratos',
          name: 'Portaretratos',
          items: [
            { name: 'Graduación', href: '#' },
            { name: 'Papá', href: '#' },
            { name: 'Mamá', href: '#' },
            { name: 'Bebes y niños', href: '#' },
            { name: 'Otros', href: '#' },
            { name: 'Ver todo', href: '#' },
          ],
        },
        {
          id: 'lomitos',
          name: 'Para tus lomitos',
          items: [
            { name: 'Placas de identificación de madera', href: '#' },
            { name: 'Placas de identificación de acrílico', href: '#' },
            { name: 'Placas de identificación de metal', href: '#' },
            { name: 'Accesorios', href: '#' },
            { name: 'Ver todo', href: '#' },
          ],
        },
      ],
    },
  ],
  pages: [
    { name: 'Nosotros', href: '#' },
    { name: 'FAQ', href: '#' },
  ],
}

const open = ref(false)
</script>

<template>
  <div class="bg-white ">
    <!-- Mobile menu -->
    <TransitionRoot as="template" :show="open">
      <Dialog class="relative z-40 lg:hidden" @close="open = false">
        <TransitionChild as="template" enter="transition-opacity ease-linear duration-300" enter-from="opacity-0" enter-to="opacity-100" leave="transition-opacity ease-linear duration-300" leave-from="opacity-100" leave-to="opacity-0">
          <div class="fixed inset-0 bg-black bg-opacity-25" />
        </TransitionChild>

        <div class="fixed inset-0 z-40 flex">
          <TransitionChild as="template" enter="transition ease-in-out duration-300 transform" enter-from="-translate-x-full" enter-to="translate-x-0" leave="transition ease-in-out duration-300 transform" leave-from="translate-x-0" leave-to="-translate-x-full">
            <DialogPanel class="relative flex w-full max-w-xs flex-col overflow-y-auto bg-white pb-12 shadow-xl">
              <div class="flex px-4 pb-2 pt-5">
                <button type="button" class="relative -m-2 inline-flex items-center justify-center rounded-md p-2 text-gray-400" @click="open = false">
                  <span class="absolute -inset-0.5" />
                  <span class="sr-only">Close menu</span>
                  <XMarkIcon class="h-6 w-6" aria-hidden="true" />
                </button>
              </div>

              <!-- Links -->
              <TabGroup as="div" class="mt-2">
                <div class="border-b border-gray-200">
                  <TabList class="-mb-px flex space-x-8 px-4">
                    <Tab as="template" v-for="category in navigation.categories" :key="category.name" v-slot="{ selected }">
                      <button :class="[selected ? 'border-amber-600 text-amber-600' : 'border-transparent text-gray-900', 'flex-1 whitespace-nowrap border-b-2 px-1 py-4 text-base font-medium']">{{ category.name }}</button>
                    </Tab>
                  </TabList>
                </div>
                <TabPanels as="template">
                  <TabPanel v-for="category in navigation.categories" :key="category.name" class="space-y-10 px-4 pb-8 pt-10">
                    <div class="grid grid-cols-2 gap-x-4">
                      <div v-for="item in category.featured" :key="item.name" class="group relative text-sm">
                        <div class="aspect-h-1 aspect-w-1 overflow-hidden rounded-lg bg-gray-100 group-hover:opacity-75">
                          <img :src="appUseUtils.getImgUrl(item.imageSrc)" :alt="item.imageAlt" class="object-cover object-center" />
                        </div>
                        <a :href="item.href" class="mt-6 block font-medium text-gray-900">
                          <span class="absolute inset-0 z-10" aria-hidden="true" />
                          {{ item.name }}
                        </a>
                        <p aria-hidden="true" class="mt-1">Comprar ahora</p>
                      </div>
                    </div>
                    <div v-for="section in category.sections" :key="section.name">
                      <p :id="`${category.id}-${section.id}-heading-mobile`" class="font-medium text-gray-900">{{ section.name }}</p>
                      <ul role="list" :aria-labelledby="`${category.id}-${section.id}-heading-mobile`" class="mt-6 flex flex-col space-y-6">
                        <li v-for="item in section.items" :key="item.name" class="flow-root">
                          <a :href="item.href" class="-m-2 block p-2 text-gray-500">{{ item.name }}</a>
                        </li>
                      </ul>
                    </div>
                  </TabPanel>
                </TabPanels>
              </TabGroup>

              <div class="space-y-6 border-t border-gray-200 px-4 py-6">
                <div v-for="page in navigation.pages" :key="page.name" class="flow-root">
                  <a :href="page.href" class="-m-2 block p-2 font-medium text-gray-900">{{ page.name }}</a>
                </div>
              </div>

              <div class="space-y-6 border-t border-gray-200 px-4 py-6">
                <div class="flow-root">
                  <a href="#" class="-m-2 block p-2 font-medium text-gray-900">Síguenos</a>
                </div>
                <div class="flow-root">
                  <a href="#" class="-m-2 block p-2 font-medium text-amber-900"><i class="pi pi-tiktok "></i> TikTok</a>
                  <a href="#" class="-m-2 block p-2 font-medium text-amber-900"><i class="pi pi-instagram"></i> Instagram</a>
                </div>
              </div>
            </DialogPanel>
          </TransitionChild>
        </div>
      </Dialog>
    </TransitionRoot>

    <header class="relative bg-white">
      <p class="flex h-10 items-center justify-center bg-amber-900 px-4 text-sm font-medium text-white sm:px-6 lg:px-8"> 🇲🇽 ¡Envios a todo México!</p>

      <nav aria-label="Top" class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div class="border-b border-gray-200">
          <div class="flex h-16 items-center">
            <button type="button" class="relative rounded-md bg-white p-2 text-gray-400 lg:hidden" @click="open = true">
              <span class="absolute -inset-0.5" />
              <span class="sr-only">Open menu</span>
              <Bars3Icon class="h-6 w-6" aria-hidden="true" />
            </button>

            <!-- Logo -->
            <div class="ml-4 flex lg:ml-0">
              <a href="#">
                <span class="sr-only">Your Company</span>
                <img class="h-8 w-auto" src="../assets/logo.png" alt="" />
              </a>
            </div>

            <!-- Flyout menus -->
            <PopoverGroup class="hidden lg:ml-8 lg:block lg:self-stretch z-40">
              <div class="flex h-full space-x-8">
                <Popover v-for="category in navigation.categories" :key="category.name" class="flex" v-slot="{ open }">
                  <div class="relative flex">
                    <PopoverButton :class="[open ? 'border-amber-600 text-amber-600' : 'border-transparent text-gray-700 hover:text-gray-800', 'relative z-10 -mb-px flex items-center border-b-2 pt-px text-sm font-medium transition-colors duration-200 ease-out']">{{ category.name }}</PopoverButton>
                  </div>

                  <transition enter-active-class="transition ease-out duration-200" enter-from-class="opacity-0" enter-to-class="opacity-100" leave-active-class="transition ease-in duration-150" leave-from-class="opacity-100" leave-to-class="opacity-0">
                    <PopoverPanel class="absolute inset-x-0 top-full text-sm text-gray-500">
                      <!-- Presentational element used to render the bottom shadow, if we put the shadow on the actual panel it pokes out the top, so we use this shorter element to hide the top of the shadow -->
                      <div class="absolute inset-0 top-1/2 bg-white shadow" aria-hidden="true" />

                      <div class="relative bg-white">
                        <div class="mx-auto max-w-7xl px-8">
                          <div class="grid grid-cols-2 gap-x-8 gap-y-10 py-16">
                            <div class="col-start-2 grid grid-cols-2 gap-x-8">
                              <div v-for="item in category.featured" :key="item.name" class="group relative text-base sm:text-sm">
                                <div class="aspect-h-1 aspect-w-1 overflow-hidden rounded-lg bg-gray-100 group-hover:opacity-75">
                                  <img :src="appUseUtils.getImgUrl(item.imageSrc)" :alt="item.imageAlt" class="object-cover object-center" />
                                </div>
                                <a :href="item.href" class="mt-6 block font-medium text-gray-900">
                                  <span class="absolute inset-0 z-10" aria-hidden="true" />
                                  {{ item.name }}
                                </a>
                                <p aria-hidden="true" class="mt-1">Comprar ahora</p>
                              </div>
                            </div>
                            <div class="row-start-1 grid grid-cols-3 gap-x-8 gap-y-10 text-sm">
                              <div v-for="section in category.sections" :key="section.name">
                                <p :id="`${section.name}-heading`" class="font-medium text-gray-900">{{ section.name }}</p>
                                <ul role="list" :aria-labelledby="`${section.name}-heading`" class="mt-6 space-y-6 sm:mt-4 sm:space-y-4">
                                  <li v-for="item in section.items" :key="item.name" class="flex">
                                    <a :href="item.href" class="hover:text-gray-800">{{ item.name }}</a>
                                  </li>
                                </ul>
                              </div>
                            </div>
                          </div>
                        </div>
                      </div>
                    </PopoverPanel>
                  </transition>
                </Popover>

                <a v-for="page in navigation.pages" :key="page.name" :href="page.href" class="flex items-center text-sm font-medium text-gray-700 hover:text-gray-800">{{ page.name }}</a>
              </div>
            </PopoverGroup>

            <div class="ml-auto flex items-center">
              <div class="hidden lg:flex lg:flex-1 lg:items-center lg:justify-end lg:space-x-6">
                <span href="#" class="text-sm font-medium text-gray-700 hover:text-gray-800">Síguenos</span>
                <a href="#" class="text-sm font-medium text-amber-800 hover:text-amber-900"><i class="pi pi-tiktok "></i></a>
                <a href="#" class="text-sm font-medium text-amber-800 hover:text-amber-900"><i class="pi pi-instagram"></i></a>
                <span class="h-6 w-px bg-gray-200" aria-hidden="true" />
              </div>

              <div class="flex lg:ml-6">
                <a href="#" class="p-2 text-gray-400 hover:text-gray-500">
                  <span class="sr-only">Search</span>
                  <MagnifyingGlassIcon class="h-6 w-6" aria-hidden="true" />
                </a>
              </div>

              <!-- Cart -->
              <div class="ml-4 flow-root lg:ml-6">
                <a href="#" class="group -m-2 flex items-center p-2">
                  <ShoppingBagIcon class="h-6 w-6 flex-shrink-0 text-gray-400 group-hover:text-gray-500" aria-hidden="true" />
                  <span class="ml-2 text-sm font-medium text-gray-700 group-hover:text-gray-800">0</span>
                  <span class="sr-only">items in cart, view bag</span>
                </a>
              </div>
            </div>
          </div>
        </div>
      </nav>
    </header>
  </div>
</template>

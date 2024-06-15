<script setup>
import TheNavbar from './components/TheNavbar.vue';
import TheBanner from './components/TheBanner.vue';
import TheFeaturedProducts from './components/TheFeaturedProducts.vue';
import TheServices from './components/TheServices.vue';
import TheCategorys from './components/TheCategorys.vue';
import TheFAQ from './components/TheFAQ.vue';
import TheReviews from './components/TheReviews.vue';
import TheFooter from './components/TheFooter.vue';

</script>

<template>
    <TheNavbar/>
    <TheBanner/>
    <TheFeaturedProducts class="bg-amber-50"/>
    <TheServices/>
    <TheCategorys class="bg-amber-50"/>
    <TheReviews/>
    <TheFAQ class="bg-amber-50"/>
    <TheFooter/>
    <ScrollTop />
</template>


<template>
<ul>
    <li><a href="/">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/contact">Contact</a></li>
</ul>
 
<component :is="currentView" />

</template>


<script lang="ts" setup>

import {ref} from 'vue'

import Home from '......vue'
import About from '......vue'
import Contact from '.....vue'
import NotFound from '.....vue'

const routes = {
    '/': Home,
    '/about' : About,
    '/contact' : Contact
}


const currenPath = ref(window.location.hash)


window.addEventListener('hashchange', () => {
    currenPath.value = window.location.hash
})

const currentView = computed(() => {
    return routes[currenPath.value.slice(1) || '/'] || NotFound
})



</script>
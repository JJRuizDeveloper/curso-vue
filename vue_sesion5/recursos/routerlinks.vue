<template>
<router-link :to="XYZ"></router-link>
</template>

<script>
router.push({ path: '/mi/ruta' })
router.push({ name: 'about' })
router.push({ name: 'detail', params: {
    id: 52
}})

router.replace({})
</script>
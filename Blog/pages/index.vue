<script setup>

    const config = useRuntimeConfig()

    const { data } = await useFetch(`${config.public.apiUrl}/api/blogs`)

    console.log(useRuntimeConfig().public.apiUrl)
</script>

<template>
    <Navbar />

    <div>
        <h1>Browse Blogs: </h1>
    </div>

    <div v-if="data?.data" class="cards">
        <BlogCard
        v-for="post in data.data" :key="post.id" :post="post"/>

    </div>

</template>

<style scoped>

.cards {
    margin: 0 auto;
    width: 800px;
    
}

h1 {
    margin: 0 auto;
    font-family: 'Stack Sans Notch', sans-serif;

}

</style>
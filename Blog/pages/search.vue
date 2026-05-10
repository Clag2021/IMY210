<script setup>


const searchTerm = ref('')
const config = useRuntimeConfig()

const { data } = await useFetch(
  `${config.public.apiUrl}/api/blogs`
)

const filteredPosts = computed(() => {
    if (!data.value?.data) return []
    return data.value.data.filter((post) => {
        return (
            post.title.toLowerCase().includes(searchTerm.value.toLowerCase()) ||
            post.author.toLowerCase().includes(searchTerm.value.toLowerCase()) ||
            post.category.toLowerCase().includes(searchTerm.value.toLowerCase())
        )
    })
})


</script>

<template>

    <Navbar />

    <div class="search-page">

    </div>
    <h1>Search Blogs</h1>
    <SearchBar v-model="searchTerm"/>

    <div class="cards">
        <BlogCard v-for="post in filteredPosts" :key="post.id" :post="post" />
    </div>



</template>

<style scoped>
h1 {
    margin: 0 auto;
    font-family: 'Stack Sans Notch', sans-serif;

}

</style>

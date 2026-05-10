<script setup>


</script>

<template>

<div class="navbar">
    <h1>BBBloger.io</h1>
    <nav>
        <ul>
            <li><a href="/">Home</a></li>
            <li><a href="/search">Search</a></li>
        </ul>
    </nav>
</div>

</template>

<style scoped>
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    background-color: #9667E0;
    border-bottom: 1px solid #D4BBFC;
}

.navbar h1 {
    font-family: 'Uncial Antiqua', serif;
    color: white;
    margin: 0;
}

.navbar nav ul {
    display: flex;
    list-style: none;
    margin: 0;
    padding: 0;
}

.navbar nav li {
    margin-right: 1rem;
}

.navbar nav a {
    font-family: 'Stack Sans Notch', sans-serif;
    font-size: 1.3em;
    text-decoration: none;
    color: white;

}

.navbar nav a:hover {
    text-decoration: underline;
}

</style>

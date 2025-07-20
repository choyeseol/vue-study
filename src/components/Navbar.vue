<template>
    <div>
        <nav>
            <a href="#">Home</a>
            <a href="#">Movies</a>
            <a href="#">About</a>
        </nav>
    </div>
</template>

<script>
    export default {
        name: 'NavbarComponent'
    }
</script>

<style>
    .navbar {
        background-: #000;
        padding: 20px;
    }

    .navbar a {
        color: #fff;
        text-decoration: none;
        padding: 1em;
    }
</style>
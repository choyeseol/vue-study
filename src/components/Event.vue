<template>
    <div class="event">
        <p>{{ text }}</p>
    </div>
</template>
<script>
export default {
    name: 'EventComponent',
    props: {
        text: String
    }
}
</script>
<style>
    .event {
        background-color: grey;
        color: #fff;
        padding: 10px 20px;
        text-align: center;
    }

    .event p {
        margin: 0;
    }
</style>
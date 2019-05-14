<template>
    <div class="helloVue">
        <h1>{{ msg }}</h1>
    </div>
</template>

<script>
    export default {
        name: 'helloVue',
        data() {
            return {
                msg: 'Hello,Vue!'
            }
        }
    }
</script>

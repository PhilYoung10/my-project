<template>
    <div class="login">
        <h1>{{ msg }}</h1>
    </div>
</template>

<script>
    export default {
        name: 'login',
        data() {
            return {
                msg: '请登录！'
            }
        },
    method:{
          loginStatus:function () {
            return 1;
          }
    }
    }
</script>

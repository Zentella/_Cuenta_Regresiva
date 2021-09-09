<template>
    <div class="container">

            <div>
                cuenta regresiva
                <button @click="b1">1</button>
                <button @click="b2">2</button>
                <button @click="b3">3</button>
            </div>

            <div v-if="mostrar">{{ tiempo }}</div>
    </div>
</template>

<script>
    export default {
        name: 'HelloVue',
        data() {
            return {
                tiempo:'',
                mostrar: false              
            };
        },
        methods: {
            b1() {
                this.mostrar = "!this.mostrar" 
                this.tiempo = 1
                setTimeout(() => {
                this.tiempo--
                }, 1000);
            },
            b2() {
                this.mostrar = "!this.mostrar" 
                this.tiempo = 2
                setTimeout(() => {
                    setTimeout(() => {
                this.tiempo--
                }, 2000);
                this.tiempo--
                }, 1000);
            },
            b3() {
                this.mostrar = "!this.mostrar" 
                this.tiempo = 3
                setTimeout(() => {
                    setTimeout(() => {
                        setTimeout(() => {
                this.tiempo--
                }, 3000);
                this.tiempo--
                }, 2000);
                this.tiempo--
                }, 1000);
            },
        }

    };
</script>

<style scoped>
    .container {
        padding:40px 400px;
    }
</style>

<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <h1>Counter - Vue</h1>
    <h2>Direct access: {{ $store.state.count }}</h2>
    <h2>Computed: {{ countComputed }}</h2>

    <button @click="increment">+1</button>
    <button @click="incrementBy">+5</button>
    <button @click="incrementRandomInt">Random</button>

    <h1>mapState</h1>
    <h2>mapState: {{ count }}</h2>
</template>


<script>

    import { mapState } from 'vuex'
    export default{

        computed:{
            countComputed(){
                return this.$store.state.count
            },
           /// ... mapState(['count'])
           ... mapState({
            count: state =>state.count
           })
        },
        methods:{
            increment(){
                this.$store.commit('increment')
            },
            incrementBy(){
                this.$store.commit('incrementBy', 5)
            },
            incrementRandomInt(){
                this.$store.dispatch('incrementRandomInt')
            }
        }
    }
</script>

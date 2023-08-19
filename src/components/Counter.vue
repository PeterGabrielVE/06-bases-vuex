<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <h1>Counter - Vue</h1>
    <h2>Direct access: {{ $store.state.count }}</h2>
    <h2>Computed: {{ countComputed }}</h2>
</template>


<script>
    export default{
        
        computed:{
            countComputed(){
                return this.$store.state.count
            }
        }
    }
</script>

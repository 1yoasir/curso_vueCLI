<template>
    <div>
        <h1>Galery of photos</h1>

        <router-link :to="{name: 'photos', params: {id: item}}" 
        v-for="(item, index) of photosArray" :key="index">
            <button>Photo {{item}}</button>
        </router-link>

        <Photo/>

        <button @click="home">Home</button>
        <button @click="anterior">Anterior</button>
        <button @click="siguiente">Siguiente</button>
    </div>
</template>

<script>
import  Photo  from "@/components/Photo.vue"

export default {
    components:{
        Photo
    },
    data() {
        return {
            photosArray: [1, 2, 3]
        }
    },
    methods: {
        home(){
            this.$router.push('/')
        },
        anterior(){
            this.$router.go(-1)
        },
        siguiente(){
            this.$router.go(1)
        }
    },
}
</script>
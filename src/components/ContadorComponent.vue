<template lang="">
    <div>
        {{title}}
    </div>
    <div>
        {{malas ? "Malas" : "Buenas"}}: {{point}}
    </div>
    <button 
        v-on:click="addPoint"
        :disabled="point == 15 && malas == false"
    >
        +
    </button>
    <button 
        v-on:click="substractPoint"
        :disabled="point == 0 && malas"
    >
        -
    </button>
</template>

<script>
export default {
    name: 'ContadorComponent',
    props: {
        title: String
    },
    data() {
        return {
            point:0,
            malas:true
        }
    },
    methods:{
        addPoint() {
            this.point +=1

            // pasar a buenas
            if (this.point == 16 && this.malas){
                this.malas = false;
                this.point = 0;
            }
        },
        substractPoint() {
            this.point -=1
            // volver a malas
            if (this.point == -1 && !this.malas){
                this.malas = true;
                this.point = 15;
            }
        }
    }
}
</script>
<style lang="">
    
</style>
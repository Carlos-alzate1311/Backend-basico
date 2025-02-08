<template>
    <div class="barbero" >
        <h1>bienvenidos barberos </h1>
        <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Totam, hic vitae, quam fugiat odit, officia sit aperiam
            expedita ad repudiandae quaerat nemo nulla eveniet! Suscipit ad molestiae magnam at totam.</p>
            <FormularioBarberos @refresh="refrescar"/>
            <TablaBarberos :barberos="barberos"/>

    </div>
</template>

<script>
import axios from 'axios';
import FormularioBarberos from '@/components/FormularioBarberos.vue'
import TablaBarberos from '@/components/TablaBarberos.vue'
export default{
    name: "Barberos-views",

    components:{
         FormularioBarberos,
         TablaBarberos, },
    data: () => ({
  Barberos: [],
}),
mounted(){
    this.getBarbero();
},
methods: {
    refrescar(){
        this.getBarbero();
    },
    getBarbero(){
        axios
            .get("http://localhost:9090/api/barbero/listar")
            .then((responde) =>{
                this.Barberos = responde.data;
            });
    },
},

}



</script> 
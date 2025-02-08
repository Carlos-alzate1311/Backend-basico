<template>
    <div class="cliente">
        <h1>Bienvenidos Usuarios </h1>
        <p>hola a todsos</p>
        <FormularioClientes @refresh="refrescar"/>
        <TablaCliente :clientes="clientes"/>
        

        


    </div>
</template>

<script>
import FormularioClientes from '@/components/FormularioClientes.vue';
import TablaCliente from '@/components/TablaCliente.vue';

import axios from 'axios';


export default {
    name: "Clientes-view",
    components: { FormularioClientes, TablaCliente, },
   
    data: () => ({
  Clientes: [],
}),
mounted(){
    this.getClientes();
},
methods: {
    refrescar(){
        this.getClientes();
    },
    getClientes(){
        axios
            .get("http://localhost:9090/api/cliente/listar")
            .then((responde) =>{
                this.Clientes = responde.data;
            });
    },
},
};



</script>

<style></style>
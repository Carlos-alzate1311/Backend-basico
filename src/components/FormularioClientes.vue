<template>
    <div class="formCliente">
        <fieldset>
            <legend>Formulario Registro Clientes</legend>

            <form @submit.prevent="guardar">

                <label for="idCliente">  Id  cliente    </label>
                <input 
                    type="number" 
                    name="idcliente" 
                    id="idCliente"
                    v-model="cliente.Id_Cliente"
                    /><br  />

                <label for="nombre">Nombre cliente</label>
                <input 
                type="text"
                name="nombre"
                 id="nombre"
                 v-model="cliente.Nombre_Cli"
                 ><br  />

                <label for="numero">Numero cliente</label>
                <input
                 type="text"
                 name="numero" 
                 id="numero"
                 v-model="cliente.Numero_Cli"
                 ><br>

                
                <button type="submit">Guardar</button>
                  <button type="button" @click="eliminar(cliente.idCliente)">Eliminar</button>

            </form>


        </fieldset>

    </div>
</template>

<script>
import axios from 'axios';

export default{
    name:"FormularioClientes",
    data: function () {
        return {
            cliente: {
                idCliente: "",
                nombre: "",
                numero: "",
            },
        };
    },
    methods: {
        guardar() {
            axios
                .post("http://localhost:9090/api/cliente", this.cliente)
                .then((data) => {
                    console.log("responde", data);
                    this.$emit("refresh");
                });
        },


        eliminar(id) {
            axios
                .delete("http://localhost:9090/api/cliente/" + id)
                .then((data) => {
                    console.log("responde", data);
                    this.cliente.idCliente = null;
                    this.$emit("refresh");
                })
                .catch(() => {
                    alert("El cliente seleccionado no existe");
                });

            console.log(id);

        },
    }

};


</script>

<style>

.formCliente{

    text-align: center;
    padding: 3%;
    
}


</style>
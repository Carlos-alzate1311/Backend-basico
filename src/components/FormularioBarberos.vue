<template>
    <div class="formBarbero">
        <fieldset>
            <legend>Formulario Registro Barberos</legend>

            <form @submit.prevent="guardar">

                <label for="idBarbero"> Id Barbero </label>
                <input type="number" 
                name="idBarbero"
                 id="idBarbero"
                 v-model="barbero.Id_Barbero"
                 ><br />

                <label for="Nombre_Bar">Nombre Barbero</label>
                <input type="text"
                 name="NombreBar" 
                 id="nombreBar"
                 v-model="barbero.Nombre_Barr"
                
                 ><br />

                <label for="Numero_Bar">Numero Barbero</label>
                <input type="text"
                 name="Numero_Bar" 
                 id="numero_Bar"
                 v-model="barbero.Numero_Cel"
                 ><br>

                 <label for="EmailBar">Email Barbero</label>
                <input type="text"
                 name="EmailBar" 
                 id="EmailBar"
                 v-model="barbero.Email_Bar"
                 ><br>


                 <button type="submit">Guardar</button>
                 <button type="button" @click="eliminar(barbero.idBarbero)">Eliminar</button>

            </form>


        </fieldset>

    </div>
</template>

<script>
import axios from "axios";

export default {
    name: "FormularioBarberos",
    data: function () {
        return {
            barbero: {
                idBarbero: "",
                nombreBar: "",
                numeroBar: "",
            },
        };
    },
    methods: {
        guardar() {
            axios
                .post("http://localhost:9090/api/barbero", this.barbero)
                .then((data) => {
                    console.log("responde", data);
                    this.$emit("refresh");
                });
        },


        eliminar(id) {
            axios
                .delete("http://localhost:9090/api/barbero/" + id)
                .then((data) => {
                    console.log("responde", data);
                    this.barbero.idBarbero = null;
                    this.$emit("refresh");
                })
                .catch(() => {
                    alert("El Barbero seleccionado no existe");
                });

            console.log(id);

        },
    }

};


</script>

<style>
.formBarbero {

    text-align: center;
    padding: 3%;

}
</style>
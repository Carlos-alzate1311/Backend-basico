<template>
    <div class="tbBarbero">
        <fieldset>
            <legend>Tabla Barberos</legend>
            <table>
                <tr>
                    <th>Id</th>
                    <th>Nombre</th>
                    <th>Numero</th>


                </tr>

                <tr v-for="barbero in barberos" :key="barbero.idBarbero">
                    <td>{{ barbero.idBarbero }}</td>
                    <td>{{ barbero.nombreBar }}</td>
                    <td>{{ barbero.numeroBar }}</td>


                </tr>
                

            </table>
        </fieldset>


    </div>

</template>

<script>
export default{
    name: "TablaBarbero",
    props:{
        barberos: {
            type: Array,
        }
    },
    methods: {},
};


</script>

<style>
.tbBarbero{
    padding: 3%;
    text-align: center;

}

table{
    
    border: 1px solid #000;
    margin: auto;
    padding: 1px;
}

th{
    border: 1px solid #000;
    
    
    
}

td{
    border: 1px solid #000;
    text-align: left;
    width: 10%;
    vertical-align: top;
}
</style>
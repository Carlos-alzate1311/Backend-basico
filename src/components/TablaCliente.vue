<template>
    <div class="tbClientes">
        <fieldset>
            <legend>Tabla Clientes</legend>
            <table>
                <tr>
                    <th>Id</th>
                    <th>Nombre</th>
                    <th>Numero</th>


                </tr>

                <tr v-for="cliente in clientes" :key="cliente.idCliente">
                    <td>{{ cliente.idCliente }}</td>
                    <td>{{ cliente.nombreCliemte }}</td>
                    <td>{{ cliente.numeroCliente }}</td>


                </tr>
                

            </table>
        </fieldset>


    </div>

</template>

<script>
export default{
    name: "TablaCliente",
    props:{
        clientes: {
            type: Array,
        }
    },
    methods: {},
};


</script>

<style>
.tbCliente{
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
<template>
    <tr>
        <td>
            <img src="https://via.placeholder.com/250x125/d2d2d2/?text=no%20image%20yet" onerror="this.src='https://via.placeholder.com/250x125/d2d2d2/?text=no%20image%20yet';" :alt="this.car.brand+' '+this.car.brand" :title="this.car.brand+' '+this.car.brand" class="carImg" />
        </td>

        <td>{{car._id}}</td>
        <td>{{car.brand | capitalize }}</td>
        <td>{{car.model}}</td>

        <td>{{car.engine | twoNums(1)}}</td>
        <td>{{car.price | twoNums}}</td>

        <td><button class="btn btn-danger" @click="removeCar()"><font-awesome-icon icon="trash" /></button></td>
    </tr>
</template>

<script>
    export default {
        props:['car'],
        name: 'car',
        filters: {
            capitalize: function (value) {
                return value.toUpperCase()
            },
            twoNums: function (val, num = 2) {
                return val.toFixed(num);
            }
        },
        methods: {
            removeCar(){
                console.log(this.car._id);
            }
        },
    }
</script>
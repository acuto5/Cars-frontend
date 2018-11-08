<template>
    <tr>
        <td>
            <img src="https://via.placeholder.com/250x125/d2d2d2/?text=no%20image%20yet" onerror="this.src='https://via.placeholder.com/250x125/d2d2d2/?text=no%20image%20yet';" :alt="this.car.brand+' '+this.car.model" :title="this.car.brand+' '+this.car.model" class="carImg" />
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
        props:['car', 'cars'],
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
                fetch('http://localhost:5001/api/cars/' + this.car._id, {
                    method: 'DELETE',
                    headers: {'Content-Type': 'application/json'},
                }).then(response => response.json()).then(json=>{
                    if(json.status === 'ok'){
                        let targetCar = this.cars.find(x => x._id === this.car._id);
                        this.cars.splice(this.cars.indexOf(targetCar), 1);
                    }
                });
            }
        },
    }
</script>
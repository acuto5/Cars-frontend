<template>
    <tr>
        <td>
            <img src="https://via.placeholder.com/250x125/d2d2d2/?text=no%20image%20yet" onerror="this.src='https://via.placeholder.com/250x125/d2d2d2/?text=no%20image%20yet';" :alt="this.car.brand+' '+this.car.brand" :title="this.car.brand+' '+this.car.brand" class="carImg" />
        </td>

        <td>{{car._id}}</td>
        <td>{{car.brand}}</td>
        <td>{{car.model}}</td>

        <td>{{car.engine}}</td>
        <td>{{car.price}}</td>

        <td></td>
    </tr>
</template>

<script>
    export default {
        props:['car'],
        name: 'car',
    }
</script>
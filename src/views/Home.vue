<template>
  <div class="home">
    <section id="intro">
      <div class="overVideo">
      </div>



    </section>

    <section id="results" class="pt-5">
      <div class="container">
        <h1>Search car</h1>
        <div class="row">
          <div class="col-12">
            <table class="table">
              <thead>
              <tr>
                <th scope="col"></th>
                <th scope="col">Id</th>
                <th scope="col">Brand</th>
                <th scope="col">Model</th>
                <th scope="col">Engine</th>
                <th scope="col">Price</th>
                <th scope="col">Action</th>
              </tr>
              </thead>
              <tbody id="tbody_cars">
              <car v-for="c in cars" :car="c" :key="c._id"></car>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </section>

  </div>
</template>

<script>
// @ is an alias to /src
import car from '@/components/Car.vue'

export default {
    components: {
        car
    },
    data() {
        return {
            test: "testas",
            cars: [],

        }
    },created(){
        fetch("http://localhost:5001/api/cars").then(response => response.json()).then(json=>{
            console.log(json);
            this.cars = json;
        })
    },

}
</script>

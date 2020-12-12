<template>
  <div id="app">

    <section-services></section-services>
    
    <div class="container-fluid">
      <api-peliculas></api-peliculas>
    </div>

    <section class="container-fluid" id="miembros">
      <div class="row justify-content-center mb-5">
        <div class="col mt-5" v-for="(item, index) of team" :key="index">

        <team-card v-bind:member = "item"></team-card>
        
        </div>   
      </div>
    </section>

  </div>
</template>

<script>
import SectionServices from "./components/SectionServices.vue";
import TeamCard from "./components/TeamCard.vue";
import ApiPeliculas from "./components/ApiPeliculas.vue";



export default {
  name: "App",
  components: {
    SectionServices,
    TeamCard,
    ApiPeliculas,
  },

  data() {
    return {
      title: "Vivo dentro de vue",
      team: [
        {
          codigo: 1,
          nombre: 'William Garcés Gómez',
          descripcion: 'Edad: 29, Técnico en sistemas, Tolú(Sucre), ',
          rol: 'Desarrollador Backend',
          image: require('@/img/williamgarces.jpeg'),
        },
        {
          codigo: 2,
          nombre: 'Diego Alejandro Sánchez',
          descripcion: 'Edad: 31, Instructor SENA, Popayán(Cauca)',
          rol: 'Desarrollador Backend',
          image: require('@/img/diegosanchez.jpg'),
        },
        {
          codigo: 3,
          nombre: 'William Vargas Acero',
          descripcion: 'Edad: 26, Estudiante, Sogamoso(Boyacá)',
          rol: 'Desarrollador Frontend',
          image: require('@/img/williamvargas.jpeg'),
        },
        {
          codigo: 4,
          nombre: 'Víctor Vargas Macias',
          descripcion: 'Edad: 35, Docente, Barbosa(Antioquia)',
          rol: 'Desarrollador Frontend',
          image: require('@/img/victorvargas.jpg'),
        }
      ]
    };
  },
};
</script>

<style scoped>

</style>
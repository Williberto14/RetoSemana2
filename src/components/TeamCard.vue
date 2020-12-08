<template>  
      <div class="card text-white bg-dark">
        <div class="d-flex justify-content-center p-2">
          <img v-bind:src="member.image" alt="Fofografia de los miembros" width="150" />
        </div>
        <div class="card-body">
          <h4 class="card-title">Miembro #{{ member.codigo }}</h4>
          <h5 class="card-subtitle mb-2 text-muted"> {{ member.rol }}</h5>
          <p class="card-text"> {{ member.nombre }}</p>
          <p class="card-text"> {{ member.descripcion }}</p>
        </div>
        <div class="card-footer">
          <small class="text-muted">Informacion actualizada recientemente</small>
        </div>
      </div>
</template>

<script>
export default {
  name: "TeamCard",
  props: ["member"]
};
</script>

<style scoped>
</style>

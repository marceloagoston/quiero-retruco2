<template>
  <div class="two-column-layout">
    <div class="column left-column">
      <ContadorComponent title="Nosotros"/>
    </div>
    <div class="column right-column">
      <ContadorComponent title="Ellos"/>
    </div>
  </div>
</template>

<script>
import ContadorComponent from './components/ContadorComponent.vue';

export default {
  name: 'App',
  components: {
    ContadorComponent
  }
}
</script>

<style scoped>
.two-column-layout {
  display: flex;
  flex-wrap: wrap;
}

.column {
  flex: 1;
  padding: 10px;
  box-sizing: border-box;
}

.left-column {
  background-color: #f0f0f0;
}

.right-column {
  background-color: #e0e0e0;
}

@media (max-width: 768px) {
  .column {
    flex: 100%;
  }
}
</style>

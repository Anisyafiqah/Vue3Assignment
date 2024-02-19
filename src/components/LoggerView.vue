<template>
  <div v-if="logs.length > 0">
    <h2>Log:</h2>
    <div class="logger">
      <ul>
        <li v-for="log in logs" :key="log.id">{{ log.message }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: ['logs'],
  data() {
    return {
      // logger: []
    };
  }
};
</script>

<style scoped>
.logger {
  margin-top: 20px;
}

.logger ul {
  list-style-type: none;
  padding: 0;
}

.logger li {
  padding: 5px 0;
  border-bottom: 1px solid #7b191f;
}

.logger li:last-child {
  border-bottom: none;
}

/* td:hover {
  background-color: #7b191f;
  color:white;
} */
</style>

<script setup lang="ts">
interface NameProps {
  name: string;
  index: number;
}
const props = defineProps<NameProps>();

const emit = defineEmits(["remove"]);

const removeName = () => {
  emit("remove", props.index);
};
</script>

<template>
  <div class="card">
    {{ name }}
    <p @click="removeName">x</p>
  </div>
</template>

<style scoped>
.card {
  background-color: rgb(27, 60, 138);
  min-width: 28%;
  max-width: 300px;
  color: white;
  border-radius: 1rem;
  padding: 1rem;
  margin-right: 0.5rem;
  margin-bottom: 1rem;
  position: relative;
}

.card p {
  position: absolute;
  top: -30%;
  left: 92.5%;
  cursor: pointer;
  color: rgba(255, 255, 255, 0.178);
}
</style>

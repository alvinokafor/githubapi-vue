<script setup>
import { toRefs } from 'vue'

const props = defineProps({
  pageNumbers: Array
})

const { pageNumbers } = toRefs(props)

const emit = defineEmits(['nextPage', 'prevPage', 'pageJump'])
const handleNext = () => {
  emit('nextPage')
}

const handlePrev = () => {
  emit('prevPage')
}

const handlePageJump = (btnNum) => {
  emit('pageJump', btnNum)
}
</script>

<template>
  <div class="pagination">
    <button @click="handlePrev()">Prev</button>

    <button @click="handlePageJump(btnNum)" v-for="btnNum in pageNumbers" :key="btnNum">
      {{ btnNum }}
    </button>

    <button @click="handleNext()">Next</button>
  </div>
</template>

<style scoped>
.pagination {
  text-align: center;
  margin-bottom: 20px;
}

#control {
  width: 126px;
  /* margin-right: 20px; */
}

.pagination button {
  font-family: inherit;
  color: var(--white);
  font-weight: 500;
  background-color: var(--secondary);
  outline: none;
  border: 1px solid var(--secondary);
  margin-right: 10px;
  padding-block: 10px;
  padding-inline: 15px;
  border-radius: 6px;
  transition: all 200ms ease-in;
  cursor: pointer;
}

.pagination button:hover {
  border: 1px solid var(--white);
}

#btn-active {
  border: 1px solid var(--white);
}

.button {
  border: 1px solid black;
}

#btn-disabled {
  width: 126px;
  /* margin-right: 20px; */
  background-color: var(--grey);
}

@media (max-width: 420px) {
  #control {
    width: 50px;
    /* margin-right: 30px; */
    font-size: 0.825rem;
  }

  .pagination button {
    padding-block: 5px;
    padding-inline: 10px;
    border-radius: 6px;
    font-size: 0.825rem;
  }

  .pagination {
    margin-bottom: 20px;
  }

  #btn-disabled {
    width: 50px;
    /* margin-right: 20px; */
    background-color: var(--grey);
  }
}
</style>

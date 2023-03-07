<script setup>
import { toRefs, ref } from 'vue'

const props = defineProps({
  reposPerPage: Number,
  totalRepos: Number,
  currentPage: Number
})

const { reposPerPage, totalRepos } = toRefs(props)
const pageNumbers = ref([])

//gets the maximum amount of buttons to be displayed
const buttonLimit = Math.ceil(totalRepos.value / reposPerPage.value)

//pushes a number sequntially to the pageNumbers array for each instance i is less the btn limit
for (let i = 1; i <= buttonLimit; i++) {
  pageNumbers.value.push(i)
}
</script>
>

<template>
  <div class="pagination">
    <button>Prev</button>

    <button v-for="btnNum in pageNumbers" :key="btnNum">{{ btnNum }}</button>
    <!-- 
    <button>2</button>
    <button>3</button>
    <button>4</button>
    <button>5</button> -->

    <button>Next</button>
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

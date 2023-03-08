<script setup>
import { onMounted, ref } from 'vue'

import RepoItem from '../components/RepoItem.vue'
import RepoPagination from '../components/RepoPagination.vue'

const repositories = ref([])
const currentPage = ref(1)
const reposPerPage = ref(5)
const currentSlice = ref([])
const pageNumbers = ref([])
const buttonLimit = ref(0)

//gets the index of the last page
const indexOfLastPage = currentPage.value * reposPerPage.value
//gets the index of the second page
const indexOfFirstPage = indexOfLastPage - reposPerPage.value

onMounted(async () => {
  try {
    const res = await fetch('https://api.github.com/users/alvinokafor/repos')
    const result = await res.json()
    repositories.value = result
    currentSlice.value = repositories.value.slice(indexOfFirstPage, indexOfLastPage)
    buttonLimit.value = Math.ceil(repositories.value.length / reposPerPage.value)

    for (let i = 1; i <= buttonLimit.value; i++) {
      pageNumbers.value.push(i)
    }
  } catch (err) {
    console.log(err)
  }
})

function nextPage() {
  currentPage.value++
  console.log(currentPage.value)
}

function prevPage() {
  currentPage.value--
  console.log(currentPage.value)
}

const goToPage = (btnNum) => {
  currentPage.value = btnNum
  console.log(currentPage.value)
}
</script>

<template>
  <section class="repo-list">
    <div class="repo-header">
      <div class="back-btn flex">
        <i class="fa-solid fa-arrow-left"></i>
        <p>Back</p>
      </div>
      <h3>Respositories</h3>
    </div>

    <RepoItem
      v-for="(repo, index) in currentSlice"
      :key="repo.id"
      :repo="repo"
      :index="index"
      :currentPage="currentPage"
    />

    <RepoPagination
      @page-jump="goToPage"
      @next-page="nextPage()"
      @prev-page="prevPage()"
      :pageNumbers="pageNumbers"
    />
  </section>
</template>

<style scoped>
.repo-list {
  max-width: 1024px;
  margin-inline: auto;
  margin-top: 40px;
}

.back-btn {
  align-items: center;
  margin-bottom: 12px;
}

.back-btn i {
  margin-right: 10px;
}

.back-btn p {
  font-size: 1.125rem;
}

.repo-header {
  margin-bottom: 30px;
}

.repo-header h3 {
  font-size: 2rem;
}

@media (max-width: 420px) {
  .repo-list {
    width: 90%;
  }
}
</style>

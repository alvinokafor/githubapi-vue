<script setup>
import RepoItem from '../components/RepoItem.vue'
import RepoPagination from '../components/RepoPagination.vue'
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

    <RepoItem />
    <RepoItem />
    <RepoItem />
    <RepoItem />

    <RepoPagination />
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

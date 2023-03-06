<script setup>
import RepoDescription from '../components/RepoDescription.vue'
import RepoMetrics from '../components/RepoMetrics.vue'
import RepoInfo from '../components/RepoInfo.vue'
</script>

<template>
  <section className="single-repo">
    <div className="repo-header">
      <div className="back-btn flex">
        <i className="fa-solid fa-arrow-left"></i>
        <p>Back</p>
      </div>
      <h3>Repo Name</h3>
    </div>

    <div className="single-repo-info">
      <RepoDescription />
      <RepoMetrics />
      <RepoInfo />
    </div>
  </section>
</template>

<style scoped>
.single-repo {
  max-width: 1024px;
  margin-inline: auto;
  margin-top: 40px;
}

.single-repo-info {
  background-color: var(--secondary);
  padding-inline: 40px;
  padding-block: 35px;
  border-radius: 8px;
}

.repo-header h3 {
  margin-block: 10px;
}

@media (max-width: 420px) {
  .single-repo {
    width: 90%;
  }

  .single-repo-info {
    background-color: var(--secondary);
    padding-inline: 20px;
    padding-block: 35px;
    border-radius: 8px;
  }
}
</style>

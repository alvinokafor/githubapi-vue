<template>
  <div className="repo-card flex">
    <h5>1</h5>
    <p id="repoTitle">Repo Title</p>
    <div className="repo-link flex" id="repoURL">
      <i className="fa-solid fa-link"></i>
      <p>Repo Link</p>
    </div>
  </div>
</template>

<style scoped>
.repo-card {
  align-items: center;
  background-color: var(--secondary);
  padding: 20px;
  border-radius: 8px;
  margin-bottom: 18px;
}

/* .repo-card:last-of-type {
    margin-bottom: 0;
} */

.repo-card h5 {
  margin-right: 20px;
  font-size: 1.125rem;
  flex: 0;
}

.repo-card p {
  margin-right: 30px;
}

#repoTitle {
  flex: 2;
}

#repoURL {
  flex: 5;
}

.repo-link i {
  margin-right: 10px;
}

@media (max-width: 420px) {
  .repo-card h5,
  .repo-card p {
    font-size: 0.825rem;
    margin-bottom: 12px;
  }

  #repoURL p {
    word-break: break-all;
  }

  .repo-card {
    flex-direction: column;
    align-items: flex-start;
  }
}
</style>

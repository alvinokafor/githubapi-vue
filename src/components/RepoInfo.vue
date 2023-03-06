<template>
  <section class="repo-info">
    <p>
      <a href="#"> <span>Owner:</span>Alvin Okafor </a>
    </p>
    <p><span>Language:</span>Javascript</p>
    <p class="not-available"><span>Licence:</span> No Licence</p>
    <div class="repo-link flex repo-info-div">
      <i class="fa-solid fa-link"></i>
      <a id="infoURL" href="#">{repoURL}</a>
    </div>
  </section>
</template>

<style scoped>
.repo-info {
  margin-top: 50px;
}

.repo-info p {
  margin-bottom: 20px;
}

.repo-info p:nth-of-type(4) {
  margin-bottom: 0;
}

.repo-info span {
  font-weight: 500;
}

.not-available {
  color: var(--grey);
}

@media (max-width: 420px) {
  .repo-info p {
    font-size: 0.825rem;
  }

  #infoURL {
    word-break: break-all;
  }
}
</style>

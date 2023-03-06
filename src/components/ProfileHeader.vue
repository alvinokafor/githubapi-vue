<template>
  <header>
    <div className="user-bio">
      <h2>Alvin Okafor</h2>
      <p>@retro</p>
      <p>Frontend Engineer, UX Engineer</p>
    </div>

    <div>
      <button className="view-repo">View Repositories</button>
    </div>
  </header>
</template>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
}

.user-bio h2 {
  font-size: 2rem;
  font-weight: 500;
  margin-bottom: 12px;
}

.user-bio p:first-of-type {
  color: var(--blue);
  margin-bottom: 20px;
}

.user-bio p:nth-of-type(2) {
  color: var(--grey);
}

.view-repo {
  padding-inline: 32px;
  padding-block: 11px;
  color: var(--primary);
  background-color: var(--white);
  font-family: inherit;
  font-weight: 600;
  border-radius: 6px;
  outline: none;
  border: none;
  cursor: pointer;
}

@media (max-width: 420px) {
  header {
    flex-direction: column;
  }

  .view-repo {
    margin-top: 12px;
    font-size: 0.825rem;
  }
}
</style>

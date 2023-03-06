<script setup>
import UserImage from '../components/UserImage.vue'
import ProfileHeader from '../components/ProfileHeader.vue'
import UserInfo from '../components/UserInfo.vue'
import AccountInfo from '../components/AccountInfo.vue'
</script>

<template>
  <main>
    <section class="homeContainer flex">
      <div>
        <UserImage />
      </div>

      <div class="content">
        <ProfileHeader />
        <AccountInfo />
        <UserInfo />
      </div>
    </section>
  </main>
</template>

<style scoped>
.homeContainer {
  background-color: var(--secondary);
  max-width: 1024px;
  margin-inline: auto;
  margin-block: 20px;
  padding-inline: 40px;
  padding-block: 60px;
  border-radius: 8px;
}

.content {
  width: 100%;
}

@media (max-width: 420px) {
  .homeContainer {
    max-width: 90%;
    flex-direction: column;
    padding-inline: 20px;
  }
}
</style>

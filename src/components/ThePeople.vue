<link rel="stylesheet" href="../theme.css">
<template>
  <li class="person__item"
      v-for="manager in regactive"
      :key = manager.id>
    <div :class=" isCardOpen ? 'card__title2' : '' ">
    </div>
    <div class="card__title"
         v-text="manager.title"
         @click="isCardOpen = !isCardOpen"
    >
    </div>
    <div class="person" v-if="isCardOpen">
      <div class="person__about">
        <span class="person__name"
          v-text="manager.name">
        </span>
        <div class="person__img">
          <img :src="manager.avatar"
           alt="Мужчина"
           class="person__pic">
        </div>
        <span
          class="person__position"
          v-html="manager.position">
        </span>
        <span class="person__answers"
          v-text="manager.answers">
        </span>
      </div>
      <div class="card__email"
           v-text="manager.email">
      </div>
    </div>
  </li>
</template>

<script>
export default {
  props: ['regactive', 'isCardOpen'],
  emits: ['openCard'],
  data() {
    return {
      // isCardOpen: false
    }
  },
  methods: {

  }
}
</script>

<style scoped>

.person__item {
  display: flex;
  flex-direction: column;
  border-radius: 5px;
  width: 24%;
  height: auto;
  margin-bottom: 40px;
  font-family: 'Open Sans';
  margin-right: 1%;
  min-width: 240px;
  position: relative;
}

.card__title {
  padding: 14px 19px 11px;
  background-color: #00ace4;
  border: 1px solid #d4d6d6;
  text-transform: uppercase;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  font-size: 14px;
  line-height: 19px;
  text-align: center;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 67px;
  max-width: 285px;

  position: relative;
}

.card__title2 {
  display: flex;
  width: 16px;
  height: 16px;
  border-bottom: 2px solid white;
  position: absolute;
  top: 0;
  right: 8px;
  z-index: 1;
}

.person {
  display: flex;

  background-color: #f5f9fa;
  border: 1px solid #d4d6d6;
  padding: 10px 15px 20px;
  border-bottom-left-radius: 5px;
  border-bottom-right-radius: 5px;
  flex-direction: column;
  justify-content: space-between;
  min-height: 380px;
  max-width: 285px;
}

.person__about {
  display: flex;
  flex-direction: column;
  align-items: center;
  color: #666666;
}

.person__img {
  width: 65px;
  height: 65px;
  overflow: hidden;
  border-radius: 50%;
  align-self: center;
  border: 1px solid #00AEEF;
  margin-bottom: 12px;
  margin-top: 7px;
}

.person__pic {
  width: 100%;
  height: 100%;
  object-position: top;
  object-fit: cover;
}

.person__name {
  font-size: 18px;
  line-height: 24px;
  font-weight: 600;
}

.person__position {
  font-size: 12px;
  line-height: 16px;
  font-weight: 700;
}


.person__answers {
  font-size: 12px;
  line-height: 17px;
  font-weight: 400;
}

.card__email {
  font-size: 16px;
  font-weight: 400;
  line-height: 21px;
  color: #00AEEF;
  align-self: flex-start;
}
</style>
<template>
  <header class="header">
    <div class="container header__container">
      <div class="logo">
        <img src="../svg/logo_RRC.svg" alt="Логотип" class="logo__pic">
      </div>
      <div class="header__title">
        Географическая структура направления Fujitsu в RRC
      </div>
    </div>
  </header>
</template>

<script>
export default {
name: "TheHeader"
}
</script>

<style scoped>
.header {
  height: 65px;
  margin: 40px 0 15px;
}

.header__container {
  display: flex;
  align-items: center;
}

.logo {
  width: 180px;
  height: 65px;
  margin-right: 45px;
}

.logo__pic {
  display: block;
  width: 100%;
  height: 100%;
}

.header__title {
  font-family: 'Montserrat', sans-serif;
  font-weight: 600;
  font-size: 27px;
  line-height: 33px;
  color: #00AEEF;
}

</style>
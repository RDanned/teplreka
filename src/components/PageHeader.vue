<template>
  <header class="header">
    <div class="header-top">
      <img class="header__logo" :src="require('@/assets/img/logo-v1.svg')" alt="logo" >
      <img class="header-m-menu-btn" :src="require('@/assets/img/icon-menu.svg')" alt="logo">
    </div>
    <div class="header-mid">
      <div class="header__title">
        теплицы <br>
        регионов
      </div>
      <div class="header__description">
        Тепличные комплексы
        современного поколения
      </div>
    </div>
    <div class="header-bot">
      <div class="header-about">
        <img class="header-about__img" :src="require('@/assets/img/quality-sign.svg')" alt="quality sign">
        <a href="#" class="header-about__btn">
          О компании
        </a>
      </div>
      <a href="#about" class="header-anchor">
        <img :src="require('@/assets/img/anchor.svg')" alt="">
      </a>
    </div>
  </header>
</template>
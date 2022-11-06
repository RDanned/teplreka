<template>
  <section class="section about">
    <div class="section-top">
      <div class="section-title">
        о&nbsp;Компании
      </div>
      <div class="about-video">
        <img :src="require('@/assets/img/about-filler.png')" alt="about video">
      </div>
      <play-btn />
    </div>
    <div class="section-bot">
      <div class="section-description about-description">
        «Теплицы Регионов» - группа компаний, создающая и управляющая высокотехнологичными тепличными комплексами для
        круглогодичного выращивания овощной продукции.
        Самые передовые и инновационные разработки отрасли круглогодичного выращивания овощной продукции в защищенном
        (закрытом) грунте апробируются и применяются на производствах компании.
      </div>

      <table class="about-table">
        <tbody>
          <tr v-for="item in aboutTableItems" :key="item.left">
            <td class="about-table__left">{{item.left}}</td>
            <td class="about-table__right">{{item.right}}</td>
          </tr>
        </tbody>
      </table>

      <a href="#" class="section-more-btn">Подробнее</a>
    </div>
  </section>
</template>
<script setup>
import PlayBtn from '@/components/PlayBtn'

const aboutTableItems = [
  {
    left: '4',
    right: 'региона выращивания'
  },
  {
    left: '60 га',
    right: 'общая площадь теплиц'
  },
  {
    left: '1 300',
    right: 'сотрудников'
  },
  {
    left: '55 000',
    right: 'тонн продукции в год'
  },
]
</script>
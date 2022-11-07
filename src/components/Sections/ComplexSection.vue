<template>
  <section class="section complex">
    <div class="section-top">
      <div class="section-title section-title_black">
        тепличные
        комплексы
      </div>

      <div class="complexes-list">
        <div class="complex-item" v-for="item in mapItems" :key="item.title">
          <div class="complex-item__title">
            {{ item.title }}
          </div>
          <div class="complex-item__description">
            {{ item.description }}
          </div>
          <div class="complex-item__columns">
            <div class="complex-item-column" v-for="column in item.columns" :key="column.value">
              <div class="complex-item-column__top">
                <div class="complex-item-column__value">{{ column.value }}</div>
                <div class="complex-item-column__measure">{{ column.measure }}</div>
              </div>
              <div class="complex-item-column__bot">
                {{ column.description }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="section-bot">
      <complex-card :complex="complexCard" @close="closeCard"/>

      <div class="complex-map">
        <img :src="require('@/assets/img/complex/map.svg')" alt="">
      </div>

      <div class="brands-bg">
        <img :src="require('@/assets/img/brands/bg-flowers.svg')" alt="">
      </div>

      <a href="#" class="section-more-btn">Подробнее</a>
    </div>
  </section>
</template>
<script>
import ComplexCard from '@/components/Sections/ComplexCard'

export default {
  components: {ComplexCard},
  data(){
    return {
      complexCard: {},
      mapItems: [
        {
          title: 'ТК Сосногорский',
          description: 'Тепличный комплекс «Новочебоксарский» — это первая производственная площадка холдинга, запущенная в работу в 2019 году.',
          img: require('@/assets/img/complex/complex.png'),
          columns: [
            {
              value: '23,5',
              measure: 'га',
              description: 'площадь теплиц'
            },
            {
              value: '6',
              measure: 'сортов',
              description: 'помидоров и огурцов'
            },
            {
              value: '22 000',
              measure: 'тонн',
              description: 'продукции в год'
            }
          ]
        },
        {
          title: 'Lorem ipsum dolor.',
          description: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Enim esse eveniet id laboriosam perferendis! Ab at commodi dolores ipsum nostrum quae?',
          img: require('@/assets/img/complex/complex.png'),
          columns: [
            {
              value: '23,5',
              measure: 'га',
              description: 'площадь теплиц'
            },
            {
              value: '6',
              measure: 'сортов',
              description: 'помидоров и огурцов'
            },
            {
              value: '22 000',
              measure: 'тонн',
              description: 'продукции в год'
            }
          ]
        }
      ]
    }
  },
  mounted() {
    //this.complexCard = this.mapItems[0]
  },
  methods: {
    closeCard(){
      this.complexCard = {}
    }
  }
}
</script>
<template>
  <div class="complex-item__wrapper" v-if="Object.keys(complex).length">
    <div class="complex-item" @touchstart="handleTouchStart"  @touchend="handleTouchEnd">
      <div class="complex-item__top">
        <div class="complex-item__title">
          {{ complex.title }}
        </div>
        <div class="complex-item__description">
          {{ complex.description }}
        </div>
        <div class="complex-item__columns">
          <div class="complex-item-column" v-for="column in complex.columns" :key="column.value">
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
      <div class="complex-item__bot">
        <a href="#" class="complex-item__more-btn">Подробнее</a>
        <img class="complex-item__img" :src="complex.img" alt="">
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    complex: {
      type: Object
    }
  },
  data() {
    return {
      xDown: null,
      yDown: null
    }
  },
  methods: {
    getTouches(evt) {
      return evt.touches ||             // browser API
          evt.originalEvent.touches; // jQuery
    },
    handleTouchStart(evt) {
      const firstTouch = this.getTouches(evt)[0];
      this.xDown = firstTouch.clientX;
      this.yDown = firstTouch.clientY;
    },
    handleTouchMove(evt) {
      if (!this.xDown || !this.yDown) {
        return;
      }

      var xUp = evt.touches[0].clientX;
      var yUp = evt.touches[0].clientY;

      var xDiff = this.xDown - xUp;
      var yDiff = this.yDown - yUp;

      console.log(yUp)

      if (Math.abs(xDiff) > Math.abs(yDiff)) {/*most significant*/
        if (xDiff > 0) {
          /* right swipe */
        } else {
          /* left swipe */
        }
      } else {
        if (yDiff > 0) {
          /* down swipe */
        } else {
          /* up swipe */
          //alert('down swipe')
          this.$emit('close', true)
        }
      }
      /* reset values */
      this.xDown = null;
      this.yDown = null;
    },
    handleTouchEnd(e){
      this.$emit('close', true)
    }
  }
}
</script>
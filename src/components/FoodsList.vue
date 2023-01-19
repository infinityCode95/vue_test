<template>
  <template v-if="foods.length">
    <div class="foods__list">
        <div class="food__item" v-for="(food, index) in foods" :key="index">
          <FoodItem :food="food"/>
        </div>      
    </div>
  </template>
  <template v-else>
        <p class="empty">Нямушки больше нет :(</p>
  </template>
</template>

<script>
import FoodItem from "@/components/FoodItem";

export default {
  name: "FoodsList",
  components: {
    FoodItem
  },
  data: () => ({
    foods: [
      {
        label: 'Сказочное заморское явство',
        title: "Нямушка",
        flavor: "c фуа-гра",
        portion: "10 порций",
        gift: 'мышь в подарок',
        weight: 0.5,
        actionText: 'Чего сидишь? Порадуй котэ,',
        actionBtn: 'купи.',
        selectedText: 'Печень утки разварная с артишоками',
        disabledText: 'Печалька, c фуа-гра закончился.'
      },
      {
        label: 'Сказочное заморское явство',
        title: "Нямушка",
        flavor: "c рыбой",
        portion: "40 порций",
        gift: '2 мыши в подарок',
        weight: 2,
        actionText: 'Чего сидишь? Порадуй котэ, купи.',
        actionBtn: 'купи.',
        selectedText: 'Головы щучьи с чесноком да свежайшая сёмгушка',
        disabledText: 'Печалька, c рыбой закончился.'
      },
      {
        label: 'Сказочное заморское явство',
        title: "Нямушка",
        flavor: "c курой",
        portion: "100 порций",
        gift: '5 мышей в подарок заказчик доволен',
        weight: 5,
        actionText: 'Чего сидишь? Порадуй котэ, купи.',
        actionBtn: 'купи.',
        selectedText: 'Филе из цыплят с трюфелями в бульоне',
        disabledText: 'Печалька, c курой закончился.'
      },
    ],
  }),
};
</script>

<style lang="scss" >
.foods__list {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 20px 80px;
}

.empty {
  margin: 50px 0px 0px 0px;
  text-align: center;
  font-size: 30px;
  color: #1698D9;
}
</style>
<template>
    <div class="card__wrap">
        <div class="card__border" :class="[backgroundColorsClass]" @click="onClickSelect" @dblclick="onClickDisable">
            <div class="card" :class="opacityClass" @mouseleave="onMouseLeave">
                <span class="card__label" :class="[pinkClass]">{{ food.label }}</span>
                <h4 class="card__title">{{ food.title }}</h4>
                <span class="card__flavor">{{ food.flavor }}</span>
                <div class="card__description">
                    <span>{{ food.portion }}</span>
                    <span>{{ food.gift }}</span>
                </div>
                <div class="card__weight" :class="[backgroundColorsClass]" @click="onClickSelect">
                    {{ food.weight }}
                    <span>кг</span>
                </div>
            </div>
        </div>
        <p class="action" :class="[yellowClass]">
            {{ food.actionText }} <span @click="onClickSelect">{{ food.actionBtn }}</span>  
        </p>      
    </div>
</template>

<script>
export default {
    name: 'FoodItem',
    props: {
        food: {
            type: Object,
            required: true
        }
    },
    data: () => ({
        isSelected: false,
        isDisabled: false,
        isMouseLeave: false,
    }),
    computed: {
        backgroundColorsClass() {
            return {
                'bg-selected' : this.isSelected,
                'bg-disabled' : this.isDisabled,
            }
        },
        opacityClass() {
            return {
                'opacity' : this.isDisabled,
            }   
        },
        yellowClass() {
            return {
                'yellow' : this.isDisabled,
            }   
        },
        pinkClass() {
            return {
                'pink' : this.isMouseLeave,
            }   
        }
    },
    methods: {
        onClickSelect() {
            if (!this.isSelected) {
                this.food.actionText = this.food.selectedText
                this.food.actionBtn = ''
            } else {
                this.food.actionText = 'Чего сидишь? Порадуй котэ,'
                this.food.actionBtn = 'купи.'
            }

            this.isSelected = !this.isSelected    
        },
        onClickDisable() {
            if (!this.isDisabled) {
                this.food.actionText = this.food.disabledText
                this.food.actionBtn = ''
            } else {
                this.food.actionText = 'Чего сидишь? Порадуй котэ,'
                this.food.actionBtn = 'купи.'
            }

            this.isDisabled = !this.isDisabled    
        },
        onMouseLeave() { 
            if (this.isSelected) {
                this.food.label = 'Котэ не одобряет?';
                this.isMouseLeave = true;
            } else {
                this.isMouseLeave = false;
                this.food.label = 'Сказочное заморское явство';
            }
        } 
    }    
}
</script>

<style lang="scss">
.card__wrap {
    font-family: 'Trebuchet MS';
    cursor: pointer;
}

.card__border {
    margin: 14px 0px;
    position: relative;
    width: 328px;
    height: 488px;
    background-color: #2ea8e6;
    border-radius: 14px;
    clip-path: polygon(15% 0, 100% 0, 100% 100%, 0 100%, 0 10%);
}

.card {
    position: absolute;
    top: 4px; 
    left: 4px; 
    width: 320px; 
    height: 480px; 
    border-radius: 11px;
    clip-path: polygon(14.7% 0, 100% 0, 100% 100%, 0 100%, 0 9.7%);
    background-image: url('../assets/img/cat.png');
    color: #000;
    background-color: #f2f2f2;
    padding: 21px 0px 0px 51px;
}

.card__label {
    margin: 0px 0px 5px 0px;
    color: #666666;
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 19px;
    display: block;
}

.card__title {
    font-style: normal;
    font-weight: 700;
    font-size: 48px;
    line-height: 56px;
}

.card__flavor {
    display: block;
    margin: 0px 0px 15px 0px;
    font-style: normal;
    font-weight: 700;
    font-size: 24px;
    line-height: 28px;
}

.card__description {
    font-style: normal;
    font-weight: 700;
    font-size: 14px;
    line-height: 16px;
    color: #666666;
    max-width: 135px;

    span {
        display: block;
    }
}

.card__weight {
    font-style: normal;
    font-weight: 400;
    font-size: 42px;
    line-height: 22px;

    padding: 20px 30px 8px 30px;
    background: #1698D9;
    color: #fff;
    text-align: center;
    border-radius: 50%;
    width: 80px;
    height: 80px;
    position: absolute;
    bottom: 16px;
    right: 16px;

    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: 10px;

    span {
        font-size: 25px;
    }

}

.action {
    font-style: normal;
    font-weight: 400;
    font-size: 13px;
    line-height: 15px;
    color: #fff;
    text-align: center;
    cursor: pointer;

    span {
        color: #1698D9;
        border-bottom: 1px dashed #1698D9;
    }
}

.bg-selected {
    background-color: #D91667;
}

.bg-disabled {
    background-color: #B3B3B3;
}

.opacity {  
    opacity: 0.4;
}

.yellow {
    color: #FFFF66;
}

.pink {
    color: #D91667;
}
</style>
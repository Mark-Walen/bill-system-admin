<template>
    <el-card :shadow="cardShadow" :body-style="cardBodyStyle">
        <slot></slot>
    </el-card>
</template>
<script lang="ts">
import { defineComponent } from 'vue'
export default defineComponent({
    name: 'BmCard',
    props: {
        shadow: {
            type: String,
            default: 'never',
            validator(value) {
                return ['always', 'hover', 'never'].includes(value)
            }
        },
        bodyStyle: {
            type: Object,
            default () {
                return { padding: '0px'}
            }
        }
    },
    data() {
        return {
            cardShadow: this.shadow,
            cardBodyStyle: this.bodyStyle
        }
    }
})
</script>

<style lang="styl" scoped>
.el-card
    border none
</style>

<template>
    <div class="cell-wrapper">
        <div class="cell"></div>
        <div class="stone" :class="stoneClass"></div>
    </div>
</template>

<script lang="ts">
import { Vue, Component, Prop} from  'vue-property-decorator';
import { Cell } from '../../models/reversi'

@Component
export default class VCell extends Vue {

    @Prop({ required: true })
    public cell!: Cell;

    public get stoneClass() {
        return {
            'white-stone': this.cell.isWhite,
            'black-stone': this.cell.isBlack,
        }
    }
}
</script>

<style scoped>
.cell-wrapper {
    position: relative;
}
.cell {
    height: 64px;
    width: 64px;
    background-color: darkcyan;
    border: 2px solid gray;
}
.stone {
    position: absolute;
    top: 2px;
    left: 2px;
    height: 60px;
    width: 60px;
    border-radius: 50%; 
}
.white-stone {
    background-color: white;
}
.black-stone {
    background-color: black;
}

</style>
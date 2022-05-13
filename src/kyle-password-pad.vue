<template>
    <div>
        <input v-model="inputValue"/>
        <template>
            <div class="pin-input">
                <div
                    :class="['key', key.class]"
                    @click="key.action(key.label)"
                    v-for="key in keys"
                    :key="key.id"
                >
                    {{key.label}}</div>
            </div>
        </template>
    </div>
</template>

<script>
export default /*#__PURE__*/{
    name: "pin-input",
    data(){
        return {
            inputValue: '',
            keys: [
                {id: 1, value: '1', class: '', label: '1', action: this.pressAction },
                {id: 2, value: '2', class: '', label: '2', action: this.pressAction },
                {id: 3, value: '3', class: '', label: '3', action: this.pressAction },
                {id: 4, value: '4', class: '', label: '4', action: this.pressAction },
                {id: 5, value: '5', class: '', label: '5', action: this.pressAction },
                {id: 6, value: '6', class: '', label: '6', action: this.pressAction },
                {id: 7, value: '7', class: '', label: '7', action: this.pressAction },
                {id: 8, value: '8', class: '', label: '8', action: this.pressAction },
                {id: 9, value: '9', class: '', label: '9', action: this.pressAction },
                {id: 12, value: 'clear', class: '', label: 'C', action: ()=>{ this.inputValue = ''}},
                {id: 0, value: '0', class: '', label: '0', action: this.pressAction },
                {id: 11, value: 'enter', class: 'enter', label: 'Enter', action: this.actionEnter},
            ]
        }
    },
    methods: {
        pressAction(label){
            this.inputValue += label
        },
        actionEnter(){

        }
    }
};
</script>


<style scoped lang="scss">
@import "./scss/_reset.css";
@import "./scss/utility";
@import "./scss/variables";

$height: 80px;
$width: 100px;
$border: #ddd;

.pin-input{
    @include border-radius(8px);
    overflow: hidden;
    box-sizing: content-box;
    border: 2px solid $border;
    width: $width * 3;
    display: flex;
    justify-content: flex-start;
    flex-flow: row wrap;
}
.key{
    cursor: pointer;
    user-select: none;
    border: 1px solid $border;
    line-height: $height;
    font-size: 2rem;
    text-align: center;
    font-weight: bold;
    width: $width;
    height: $height;
    &:nth-child(1){@include border-radius(5px 0 0 0 )}
    &:nth-child(3){@include border-radius(0 5px 0 0 )}
    &:nth-child(10){@include border-radius(0 0 0 5px )}
    &:nth-child(12){@include border-radius(0 0 5px 0 )}
    &.enter{
        font-size: 1.3rem;
    }
    &:hover{
        background-color: #eeeeee;
    }
    &:active{
        transform: translateY(2px);
    }
}

input{
    border: 1px solid $color-border;
    padding: 5px 8px;
    line-height: 20px;
    display: block;
    margin-bottom: 10px;
    @include border-radius(5px)
}

</style>

<script setup lang="ts">
    import { ref } from 'vue'
    const sliderValue = ref(10)
</script>

<template>
  <form class="password-generator">
    <div class="input-wrapper">
        <input type="text" id="password" name="password" placeholder="P4$5W0rD!" disabled>
        <label class="ir" for="password">password</label>
        <button class="button-copy">
            <svg xmlns="http://www.w3.org/2000/svg" version="1.1" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:svgjs="http://svgjs.com/svgjs" width="512" height="512" x="0" y="0" viewBox="0 0 488.3 488.3" style="enable-background:new 0 0 512 512" xml:space="preserve" class="">
                <g>
                    <path d="M314.25 85.4h-227c-21.3 0-38.6 17.3-38.6 38.6v325.7c0 21.3 17.3 38.6 38.6 38.6h227c21.3 0 38.6-17.3 38.6-38.6V124c-.1-21.3-17.4-38.6-38.6-38.6zm11.5 364.2c0 6.4-5.2 11.6-11.6 11.6h-227c-6.4 0-11.6-5.2-11.6-11.6V124c0-6.4 5.2-11.6 11.6-11.6h227c6.4 0 11.6 5.2 11.6 11.6v325.6z" fill="#A9FDB3" data-original="#000000" class=""></path>
                    <path d="M401.05 0h-227c-21.3 0-38.6 17.3-38.6 38.6 0 7.5 6 13.5 13.5 13.5s13.5-6 13.5-13.5c0-6.4 5.2-11.6 11.6-11.6h227c6.4 0 11.6 5.2 11.6 11.6v325.7c0 6.4-5.2 11.6-11.6 11.6-7.5 0-13.5 6-13.5 13.5s6 13.5 13.5 13.5c21.3 0 38.6-17.3 38.6-38.6V38.6c0-21.3-17.3-38.6-38.6-38.6z" fill="#A9FDB3" data-original="#000000" class=""></path>
                </g>
            </svg>
        </button>
    </div>
    <div class="generator-settings">
        <div class="lenght-range-header">
            <div>Character Length</div>
            <input v-model="sliderValue" class="length-value" type="text" id="length-value" name="length-value">
        </div>
        <div class="range-wrapper">
            <div class="range-fill"></div>
            <input v-model="sliderValue" class="range" type="range" name="length" min="0" max="20">
            <label class="ir" for="length">Character Length</label>
        </div>
    </div>
  </form>
</template>

<style scoped> 
/* Head style */
.input-wrapper{
    display: flex;
    justify-content: center;
    padding: 15px 20px;
    background-color: #24232B;
    margin-bottom: 20px;
}
#password{
    border: none;
    background: none;
    font-size: 25px;
    font-weight: 500;
}
#password:focus{
    border: none;
    outline: none;
}
.button-copy{
    width: 30px;
    height: 30px;
}
.button-copy svg{
    width: 100%;
    height: 100%;
}

.button-copy svg path{
    fill: #A9FDB3;
    transition: fill .2s ease;
}
.button-copy:hover svg path{
    fill: #fff;
}
/* Settings style */
.generator-settings{
    padding: 15px 20px;
    background-color: #24232B;
}
.lenght-range-header{
    display: flex;
    justify-content: space-between;
    margin-bottom: 20px;
}

.range-wrapper{
    position: relative;
    display: flex;
    align-items: center;
}

.range-fill{
    position: absolute;
    top: calc(50% - 3px);
    background-color: #A9FDB3;
    height: 6px;
    width: v-bind(sliderValue/20 * 100 + '%');
    z-index: 0;
}

/* Hide div .range-fill for firefox */
@-moz-document url-prefix() {
    .range-fill{
        display: none;
    }
}

/* --- Range style --- */

/* Chrome */

input[type=range] {
    height: 22px;
    -webkit-appearance: none;
    margin: 0px 0;
    width: 100%;
    background: none;
}
input[type=range]:focus {
    outline: none;
}
input[type=range].range::-webkit-slider-runnable-track {
    width: 100%;
    height: 6px;
    cursor: pointer;
    animate: 0.2s;
    background: #14131B;
    border-radius: 0;
    border: none;
}
input[type=range].range::-webkit-slider-thumb {
    position: relative;
    box-shadow: 0px 0px 0px 0px #A9FDB3;
    border: none;
    height: 20px;
    width: 20px;
    border-radius: 50%;
    background: #E7E5EC;
    cursor: pointer;
    -webkit-appearance: none;
    margin-top: -8px;
    transition: box-shadow .1s, background .1s;
    z-index: 1;
}

input[type=range].range:focus::-webkit-slider-thumb {
    position: relative;
    box-shadow: 0px 0px 0px 2px #A9FDB3;
    border: none;
    height: 20px;
    width: 20px;
    border-radius: 50%;
    background: #14131B;
    cursor: pointer;
    -webkit-appearance: none;
    margin-top: -8px;
    transition: box-shadow .3s,background .3s;
    z-index: 1;
}

/* Firefox */

input[type=range].range::-moz-range-track{
    width: 100%;
    height: 6px;
    cursor: pointer;
    animate: 0.2s;
    background: #14131B;
    border-radius: 0;
    border: none;
}

input[type=range].range::-moz-range-thumb{
    position: relative;
    box-shadow: 0px 0px 0px 0px #A9FDB3;
    border: none;
    height: 20px;
    width: 20px;
    border-radius: 50%;
    background: #E7E5EC;
    cursor: pointer;
    -webkit-appearance: none;
    margin-top: -8px;
    transition: box-shadow .1s, background .1s;
    z-index: 1;
}

input[type=range].range:focus::-moz-range-thumb{
    position: relative;
    box-shadow: 0px 0px 0px 2px #A9FDB3;
    border: none;
    height: 20px;
    width: 20px;
    border-radius: 50%;
    background: #14131B;
    cursor: pointer;
    -webkit-appearance: none;
    margin-top: -8px;
    z-index: 1;
}

input[type=range].range::-moz-range-progress {
  height: 4px;
  background: #A9FDB3;
}

</style>
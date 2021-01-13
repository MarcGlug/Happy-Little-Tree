<template>
    <div class="pannel">
        <ul>
            <li @click="select($event)" v-for="color in colors" :key=color :style="{backgroundColor: color}"></li>
        </ul>
        <div>
          <label for="pixel">Épaisseur du trait </label>
          <input type="range" name="pixel" id="pixel" min="1" max="50" value="10">
        </div>
        <save-erase-btn></save-erase-btn>
    </div>
</template>

<script>
import SaveEraseBtn from './SaveEraseBtn.vue'
export default {
  name: 'Pannel',
  props: {
    colors: {
      type: Array
    }
  },
  components: {
    SaveEraseBtn
  },
  methods: {
    select (event) {
      const el = event.target
      const siblings = el.parentNode.childNodes
      // on retire la précédente sélection
      siblings.forEach(element => {
        if (element.classList.contains('selected')) { element.classList.remove('selected') }
      })
      // assigne une nouvelle selection
      el.classList.add('selected')
    }
  }
}
</script>

<style lang="scss" scoped>

.pannel {
    width: 500px;
    border: 2px solid #d3d3d3;
    margin-left: auto;
    margin-right: auto;
}

ul {
    display: flex;
    flex-wrap: wrap;
    li {
        list-style: none;
        width:20px;
        height:20px;
        background-color: rgb(228, 228, 228);
        border-radius: 3px;
        margin: 5px;
        padding: 3px;
        border: 3px solid #d3d3d3;
        box-sizing: content-box;

        span {
            display: inline-block;
            background-color: rgb(216, 50, 50);
            width: 100%;
            height: 100%;
        }
    }
}

input{
  vertical-align: middle;
}

.selected {
    border-color: rgb(73, 73, 73);
}

</style>

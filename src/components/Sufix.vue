<template>
  <div class="col-md">
    <h5>Sufixo <span class="badge badge-info">{{ sufixes.length }}</span></h5>
    <div class="card">
      <div class="card-body">
        <ul class="list-group">
          <li class="list-group-item" v-for="sufix in sufixes" v-bind:key="sufix">
            {{ sufix }}
          </li>
        </ul>
        <div class="input-group mt-4">
          <input class="form-control" v-model="sufix" type="text" placeholder="Digite o sufixo" />
          <div class="input-group-append">
            <button class="btn btn-info" @click="addItem(sufix)">
              <span class="fa fa-plus"></span>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Sufix',
  data() {
    return {
      sufix: ''
    }
  },
  props: {
    sufixes: {
      type: Array,
      required: true
    }
  },
  methods: {
    addItem(item) {
      this.$emit("addItem", item);
      this.sufix = "";
    },
  }
}
</script>

<style scoped>

</style>

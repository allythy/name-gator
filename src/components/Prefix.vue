<template>
  <div class="col-md">
    <h5>Prefixo <span class="badge badge-info">{{ prefixes.length }}</span></h5>
    <div class="card">
      <div class="card-body">
        <ul class="list-group">
          <li class="list-group-item" v-for="prefix in prefixes" v-bind:key="prefix">
            {{ prefix }}
          </li>
        </ul>
        <div class="input-group mt-4">
          <input class="form-control" v-model="prefix" type="text" placeholder="Digite o prefixo" />
          <div class="input-group-append">
            <button class="btn btn-info" @click="addItem(prefix)">
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
  name: 'Prefix',
  data() {
    return {
      prefix: ''
    }
  },
  props: {
    prefixes: {
      type: Array,
      required: true
    }
  },
  methods: {
    addItem(item) {
      this.$emit("addItem", item);
      this.prefix = "";
    },
  }
}
</script>

<style scoped>

</style>

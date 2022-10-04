<template>
  <div class="col-12 mt-3">
    <h5>Domains <span class="badge badge-info">{{ domains.length }}</span></h5>
    <div class="card">
      <div class="card-boy">
        <ul class="list-group">
          <li class="list-group-item" v-for="domain in domains" :key="domain">
            {{ domain }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Domain',
  data() {
    return {}
  },
  props: {
    domains: {
      type: Array,
      required: true
    }
  }
}
</script>

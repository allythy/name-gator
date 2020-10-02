<template>
  <div>
      <div id="slogan" class="text-center">
          <h1>NameGator</h1>
          <br>
          <h6 class="text-secondary">Gerador de nomes</h6>
      </div>
      <div id="main">
          <div class="container">
              <div class="row">
                  <prefix :prefixes="prefixes" @addItem="addPrefixes"/>
                  <sufix :sufixes="sufixes" @addItem="addSufixes"/>
                  <domain :domains="domains" />
              </div>
          </div>
      </div>
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css"
import "font-awesome/css/font-awesome.css"
import Prefix from "./components/Prefix";
import Sufix from "./components/Sufix";
import Domain from "./components/Domain";

export default {
  name: 'app',
  components: {
    Domain,
    Sufix,
    Prefix
  },
  data: function () {
    return {
      prefixes:['Air', 'Jet', 'Flight'],
      sufixes:['Hub','Station','Mart'],
      domains:['AirHub','AirStation','AirMart','JetHub']
    };
  },
  methods: {
    addPrefixes(prefix) {
      this.prefixes.push(prefix);
    },
    addSufixes(sufix) {
      this.sufixes.push(sufix);
    }
  },
}
</script>

<style>
#slogan{
  margin-top: 30px;
  margin-bottom:30px;
}
#main{
  background-color: #F1F1F1;
  padding-top:30px;
  padding-bottom:30px;

}

</style>

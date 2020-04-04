<template>

 <div class="container mt-16">
   <br>
<br>
<br>
  <div class="row">
    <div class="alert alert-info" role="alert">
      Útilma atualização: {{ datas['updated_at'] | moment }}
    </div>
  </div>
  <br>
  <br>
  <div class="row">
    <div class="col-sm">
      Recuperados: {{ datas['recovered'] }}
    </div>
    <div class="col-sm">
      Mortos: {{ datas['deaths'] }}
    </div>
    <div class="col-sm">
      Confirmados: {{ datas['confirmed'] }}
    </div>
    <div class="col-sm">
      Casos Suspeitos: {{ datas['suspects'] }}  ssss
    </div>
  </div>
</div>
</template>

<script>
import moment from 'moment'
export default {
  name: 'HelloWorld',
  props: {
    datas: []
  },
  filters: {
    moment: function (date) {
    return moment(date).format('llll');
  }
}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  
</style>

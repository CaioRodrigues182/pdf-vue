<template>
  <div id="home" class="container mt-5">
    <div class="row justify-content-center">
        <div class="col-md-6">
          <div class="card card-body">
            <div class="form-group">
            <input type="text" id="name" v-model="name" class="form-control" placeholder="Digite alguma coisa">
            </div>
          <button class="btn btn-primary pl-5 pr-5" @click="download">Download PDF</button>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
import JsPDF from 'jspdf'

export default {
  name: 'HelloWorld',
  data () {
    return {
      name: null,
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    download () {
      let pdfName = 'test'
      var doc = new JsPDF()
      doc.text(this.name, 10, 10)
      doc.save(pdfName + '.pdf')
    }
  }
}
</script>

<style scoped>
</style>

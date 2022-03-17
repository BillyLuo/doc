# this is list

<div id="hi">
  <input v-model="name" />
  <div>{{name}}</div>
  <span @click="say">{{msg}}</span>
</div>


<script>
  var vm = new Vue({
    el: '#main',
    data() {
      return {
        name: 'will',
        msg: 'hello,world'
      }
    },
    mounted() {
      console.log(this)
    },
    methods: {
      say() {
        console.log('hihih, msgi]')
      }
    }
  })
</script>

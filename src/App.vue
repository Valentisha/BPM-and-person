 <template>
<div>
<table class="table table table-bordered border-primary">
  <thead>
    <tr>
      <th scope="col" :class="active ? 'table-warning' : 'table-success'">#</th>
      <th scope="col" class="table-success">Имя</th>
      <th scope="col" class="table-danger">Возраст</th>
      <th scope="col" class="table-info">Доход</th>
    </tr>
  </thead>
 
<th scope="col" class="table-warning">
  <div v-for="person in tableData" :key='person.number'>
    {{ person.number }}
    </div> </th>
<th scope="col" class="table-success">
  <div v-for="person in tableData" :key='person.name'>
    {{ person.name }}
</div> </th>
<th scope="col" class="table-danger">
  <div v-for="person in tableData" :key='person.age'>
    {{ person.age }}
</div> </th>
<th scope="col" class="table-info">
  <div v-for="person in tableData" :key='person.profit'>
    {{ person.profit }}
</div> </th>
</table>

<div class="container mt-4">
  Заблокировать кнопки: 
  <input type='checkbox'  @click="active = !active" :checked="active"/>
  {{active}}
<h2 :style=" active ?'opacity: 0.5;' : 'opacity: 1;'" >{{counter}}</h2>
<button class='btn btn-success' @click='plus' :disabled='active === true'>Увеличить</button>
<button class="btn btn-success" @click='minus' :disabled='active === true'>Уменьшить</button>
<div>Прогресс:</div>
<div class="progress">
    <div class="progress-bar" role="progressbar" :height='counter' :style="'width:' + counter + 'px'" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100"></div>
</div>
<div v-if="active">Кнопки заблокированы</div>
<div v-else>Кнопки разблокированы</div>
</div>

</div>
</template>

<script>

export default {
 data() {
        return {
          counter: 120,
          active: false,
          

          tableData: [
                {
                    number: 1,
                    name: 'Горшкова Ясмина',
                    age: 15,
                    profit: 1000
                },
                {
                    number: 2,
                    name: 'Морозова Ольга',
                    age: 23,
                    profit: 35000
                },
                {
                    number: 3,
                    name: 'Фадеев Руслан',
                    age: 67,
                    profit: 100000
                },
                {
                    number: 4,
                    name: 'Исакова Дарья',
                    age: 55,
                    profit: 43500
                },
                {
                    number: 5,
                    name: 'Беляшик Дарья',
                    age: 32,
                    profit: 74300
                },
                {
                    number: 6,
                    name: 'Сидорова Арина',
                    age: 27,
                    profit: 86000
                },
          ]}
        
},
          methods: {
            plus(){
              this.counter++
            },

            minus(){
              this.counter--
            },
            change(){
              
            },



           
}}
</script>
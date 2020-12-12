<template>
  <div>
 <el-container>
  <el-header>
    </br>数据列表
  <el-button type="success" style=" float: right; margin-top: 10px;" size="small" @click = 'daochu' plain>显示后台数据</el-button></el-header>
  <el-container>

    <el-main>{{person1.id}}&nbsp&nbsp{{person1.age}}&nbsp&nbsp{{person1.canal}}&nbsp&nbsp{{person1.isQuestion}}&nbsp&nbsp{{person1.type}}&nbsp&nbsp{{person1.sex}}
             &nbsp&nbsp{{person1.isPregnant}}&nbsp&nbsp{{person1.time}}&nbsp&nbsp{{person1.babyAge}}&nbsp&nbsp{{person1.clue}}&nbsp&nbsp{{person1.clueType}}
             &nbsp&nbsp{{person1.plaOrigin}}&nbsp&nbsp{{person1.plaArea}}&nbsp&nbsp{{person1.plaAge}}&nbsp&nbsp{{person1.plaMonth}}&nbsp&nbsp{{person1.plaTotal}}<br/>
             {{person2.id}}&nbsp&nbsp{{person2.age}}&nbsp&nbsp{{person1.canal}}&nbsp&nbsp{{person2.isQuestion}}&nbsp&nbsp{{person2.type}}&nbsp&nbsp{{person2.sex}}
             &nbsp&nbsp{{person2.isPregnant}}&nbsp&nbsp{{person2.time}}&nbsp&nbsp{{person2.babyAge}}&nbsp&nbsp{{person2.clue}}&nbsp&nbsp{{person2.clueType}}
             &nbsp&nbsp{{person2.plaOrigin}}&nbsp&nbsp{{person1.plaArea}}&nbsp&nbsp{{person2.plaAge}}&nbsp&nbsp{{person2.plaMonth}}&nbsp&nbsp{{person2.plaTotal}}<br/>
             {{person3.id}}&nbsp&nbsp{{person1.age}}&nbsp&nbsp{{person3.canal}}&nbsp&nbsp{{person3.isQuestion}}&nbsp&nbsp{{person3.type}}&nbsp&nbsp{{person3.sex}}
             &nbsp&nbsp{{person3.isPregnant}}&nbsp&nbsp{{person3.time}}&nbsp&nbsp{{person3.babyAge}}&nbsp&nbsp{{person3.clue}}&nbsp&nbsp{{person3.clueType}}
             &nbsp&nbsp{{person3.plaOrigin}}&nbsp&nbsp{{person3.plaArea}}&nbsp&nbsp{{person3.plaAge}}&nbsp&nbsp{{person3.plaMonth}}&nbsp&nbsp{{person3.plaTotal}}</el-main>
  </el-container>
</el-container>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      person1:[],
      person2:[],
      person3:[]
    }
  },
  methods: {
    daochu () {
      this.$axios.get('/data.json').then(response => {
        //const result = response.data[0].name
        //console.log(result)
        const result = response.data;
        this.person1 = result[0];
        this.person2 = result[1];
        this.person3 = result[2];

      })
    }
  }

}
</script>

<style>
.el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    float: left;
    line-height: 60px;
  }
  .el-aside {
      background-color: #D3DCE6;
      color: #333;
      text-align: center;
      line-height: 200px;
    }

</style>

<template>
    <div class="livetable">
          <el-table
            :data="list"
            :tableData="tableData"
            :height="tableHeight"
            :header-cell-style="{backgroundColor:'rgba(206, 206, 255, 1)',color:'#000',fontSize:'13px', padding:'7px 0 5px 0'}"
            border>
            <el-table-column
                :render-header="addrender"
                align="center"
                width="50">
                 <template slot-scope="scope">
                     <div class="iconbox" @click="deletItem(scope.$index)">
                     </div>
                </template>
            </el-table-column>
             <el-table-column
                type="index"
                label="序号"
                align="center"
                width="80">
            </el-table-column>
            <el-table-column
                v-for="(item, index) in columns"
                :key="index"
                :prop="item.prop"
                :label="item.label"
                :show-overflow-tooltip="true"
                align="center"
                :width="item.width || ''">
                   <template slot-scope="scope">
                        <el-input 
                           v-if="item.type == 'input'" 
                           v-model="scope.row[item.prop]" 
                           size="mini" ></el-input>
                        <el-input-number 
                           v-if="item.type == 'number'" 
                           size="mini"
                           v-model="scope.row[item.prop]" 
                           controls-position="right" 
                           :min="-1000" 
                           :max="1000"></el-input-number>
                   </template>
            </el-table-column>
           
        </el-table>
    </div>
</template>

<script>
export default {
    name:'liveTable',
    props:{
        //表格数据
        tableData:{
            type: Array,
            default: function (){
                return []
            }
        },
        // 高度
        tableHeight:{
            type: Number,
            default: 0
        },
        // 列设置
        columns:{
            type: Array,
            default: function (){
                return []
            }
        }
    },
    mounted(){
        this.list = this.tableData
    },
    watch:{
        // 监控list
        list:{
            handler(val){
               this.$emit('ondatachange',val)

            },
            deep:true
        }
    },
    data(){
       return{
           list:[],
       }
    },
    computed: {
      
    },
    methods:{
        addrender(h, { column, $index }){
                return h('div', {
                    class:'icon_add',
                    on:{
                        click: this.addclick
                    }
                });
        },
        //add
        addclick(){
            this.list.push({})
        },
        //delete
        deletItem(index){
            this.list.splice(index, 1)
        }
    }

}
</script>

<style>
  .icon_add{
      width: 15px;
      height: 15px;
      background: url('./img/u138.png') no-repeat center;
      cursor: pointer;
  }
  .iconbox{
      width: 100%;
      height: 15px;
     cursor: pointer;
     background: url('./img/u163.png') no-repeat center;

  }
 .livetable .el-table td, .el-table th{
     padding: 8px 0;
 }
</style>

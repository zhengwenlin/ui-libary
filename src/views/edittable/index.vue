<template>
  <div class="edit-table">
      <p>可动态添加行，编辑，删除</p>
       <EditTable 
         :columns="columns"
         :tableHeight="300"
         @ondatachange="datachanged"
         :tableData="list"></EditTable>
  </div>
</template>

<script>
import EditTable from '@/views/components/eidttable'
export default {
  components:{
      EditTable
  },
  data() {
    return {
         list: [
            { 'id': '1', 'name': '小红', 'age': '12', 'height': '112', 'sex': '女', 'score': '100' },
            { 'id': '2', 'name': '小丽', 'age': '12', 'height': '116', 'sex': '女', 'score': '99' },
            { 'id': '3', 'name': '小芳', 'age': '12', 'height': '113', 'sex': '女', 'score': '98' },
            { 'id': '4', 'name': '小华', 'age': '12', 'height': '130', 'sex': '男', 'score': '96' }
        ],
        columns:[
            {
                prop: 'id',
                label: '编号',
                width: 180,
                columnAlign: 'center',
                type:'input'
            },
            {
                prop: 'name',
                label: '名字',
                width: 180,
                type:'input',
                columnAlign: 'center'
            },
            {
                prop: 'age',
                label: '年龄',
                width: 180,
                type:'number',
                columnAlign: 'center'
            },
            {
                prop: 'height',
                label: '身高',
                width: 180,
                type:'number',
                columnAlign: 'center'
            },
        ],
    };
  },
};
</script>
<style lang="scss">
.edit-table{
    padding-left: 30px;
}
</style>

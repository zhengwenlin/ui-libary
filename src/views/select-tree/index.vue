<template>
  <div class="select-tree">
      <p>多选：</p>
      <treeselect v-model="value"
                  :flat="true" 
                  multiple="multiple" 
                  placeholder="请选择"
                  :options="options" />

      <p class="p">单选：</p>
       <treeselect v-model="value1" 
                  :multiple="false" 
                  placeholder="请选择"
                  :options="options" />
  </div>
</template>

<script>
// import the component
  import Treeselect from '@riophae/vue-treeselect'
  // import the styles
  import '@riophae/vue-treeselect/dist/vue-treeselect.css'

export default {
 components: { Treeselect },
  data() {
      return {
        // define the default value
        value: null,
        value1:null,
        // define options
        options: [ {
          id: 'a',
          label: 'a',
          children: [ {
            id: 'aa',
            label: 'aa',
          }, {
            id: 'ab',
            label: 'ab',
          } ],
        }, {
          id: 'b',
          label: 'b',
        }, {
          id: 'c',
          label: 'c',
        } ],
      }
    },
};
</script>
<style lang="scss">
 .select-tree{
     padding: 15px;
     margin-top: 15px;
     .p{
         border-top: 1px solid #eef;
         padding-top: 20px;
         margin-top: 60px;
     }
 }
</style>
<!--
 * @Author: canlong.shen
 * @Date: 2023-06-20 09:20:51
 * @LastEditors: canlong.shen
 * @LastEditTime: 2023-06-20 19:33:11
 * @FilePath: \common\src\components\bsgoal-base-tree-table\demo.vue
 * @Description:  树 + 列表 + 演示
 * 
-->
<script setup>
/* setup模板
---------------------------------------------------------------- */
import { ref ,unref } from 'vue'
import BsgoalBaseTreeTable from './index.vue'
import ComponentTypeEnums from '../../enums/componentTypeEnums.js'


defineOptions({
  name: 'BsgoalBaseTreeTableDemo'
})

const props = defineProps({})

// ---> S 树 <---

const triggerTreeClick = (value, node, treeNode, event) => {
  console.log('value', value)
  console.log('node', node)
  console.log('treeNode', treeNode)
  console.log('event', event)
}

const treeLazyLoad = (node) => {
  console.log('treeLazyLoad', node)
  return new Promise((resove, reject) => {
    setTimeout(() => {
      resove([
        {
          label: 'label2-1',
          isLeaf: true
        },
        {
          label: 'label2-2',
          children: [
            {
              label: 'label2-2-1'
            }
          ]
        },
        {
          label: 'label2-3'
        }
      ])
    }, 1000)
  })
}

const treeInitNode = (node) => {
  console.log('treeInitNode', node)

  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve([
        {
          value: 'value1',
          label: 'label1'
        }
      ])
    }, 1000)
  })
}

// ---> E 树 <---

// ---> S 列表 <---


const configOptions = ref([
  {
    label: 'prop1',
    // value: '111',
    prop: 'prop1',
    type: ComponentTypeEnums.INPUT,
    width: '100px'
  },
  {
    label: 'prop2',
    value: 'select2',
    type: ComponentTypeEnums.SELECT,
    prop: 'prop2',
    range: [
      {
        label: 'select1',
        value: 'select1'
      },
      {
        label: 'select2',
        value: 'select2'
      },
      {
        label: 'select3',
        value: 'select3'
      },
      {
        label: 'select4',
        value: 'select5'
      }
    ]
  },
  {
    label: 'prop3',
    // value: '111',
    type: ComponentTypeEnums.SLIDER,
    prop: 'prop3'
  },
  {
    label: 'prop4',
    // value: '111',
    type: ComponentTypeEnums.SWITCH,
    prop: 'prop4'
  },
  {
    label: 'prop5',
    // value: '111',
    type: ComponentTypeEnums.RADIO,
    prop: 'prop5',
    range: [
      {
        label: 'radio1',
        value: 'radio1'
      },
      {
        label: 'radio2',
        value: 'radio2'
      }
    ]
  },
  {
    label: 'prop6',
    value: [],
    type: ComponentTypeEnums.CHECKBOX,
    prop: 'prop6',
    range: [
      {
        label: 'checkbox1',
        value: 'checkbox1'
      },
      {
        label: 'checkbox2',
        value: 'checkbox2'
      }
    ]
  },
  {
    label: 'prop7',
    // value: '111',
    type: ComponentTypeEnums.DATE,
    prop: 'prop7',
    format: 'YYYY-MM-DD'
  },
  {
    label: 'prop9',
    // value: '111',
    type: ComponentTypeEnums.MONTH,
    prop: 'prop9'
  },
  {
    label: 'prop10',
    // value: '111',
    type: ComponentTypeEnums.YEAR,
    prop: 'prop10'
  },
  {
    label: 'prop11',
    // value: '111',
    type: ComponentTypeEnums.DATE_RANGE,
    prop: 'prop11',
    range: ['startDate', 'endDate']
  },
  {
    label: 'prop12',
    // value: '111',
    type: ComponentTypeEnums.MONTH_RANGE,
    prop: 'prop12'
  },
  {
    label: 'prop13',
    // value: '111',
    type: ComponentTypeEnums.TIME,
    prop: 'prop13'
  },
  {
    label: 'prop14',
    // value: '111',
    type: ComponentTypeEnums.TIME_RANGE,
    prop: 'prop14'
  },
  {
    label: 'prop15',
    // value: '111',
    type: ComponentTypeEnums.DATE_TIME,
    prop: 'prop15'
  },
  {
    label: 'prop16',
    // value: '111',
    type: ComponentTypeEnums.DATE_TIME_RANGE,
    prop: 'prop16'
  },
  {
    label: 'prop17',
    // value: '111',
    type: ComponentTypeEnums.CASCADER,
    prop: 'prop17',
    single: true,
    range: [
      {
        id: 354,
        institutionName: '深圳市博思高科技有限公司',
        parentInstitutionId: 354,
        parentId: 2,
        userName: '卢阳万',
        phone: '13249398733',
        province: null,
        city: '深圳市',
        district: '光明区',
        detailsAddress: '百艺盛大厦9楼',
        provinceCode: null,
        cityCode: '430200',
        districtCode: null,
        systemAccount: null,
        children: [
          {
            id: 2831,
            institutionName: '子机构',
            parentInstitutionId: 354,
            parentId: 3,
            userName: '成都',
            phone: '14548454545',
            province: null,
            city: '',
            district: '',
            detailsAddress: '',
            provinceCode: '',
            cityCode: '',
            districtCode: '',
            systemAccount: '479502',
            children: [],
            label: '子机构',
            value: 2831
          },
          {
            id: 3302,
            institutionName: '新权限机构',
            parentInstitutionId: 354,
            parentId: 3,
            userName: '孙先生',
            phone: '18851450010',
            province: null,
            city: '',
            district: '',
            detailsAddress: '',
            provinceCode: '',
            cityCode: '',
            districtCode: '',
            systemAccount: '479608',
            children: [],
            label: '新权限机构',
            value: 3302
          },
          {
            id: 3307,
            institutionName: '测试机构-shencanlong',
            parentInstitutionId: 354,
            parentId: 3,
            userName: '沈灿龙',
            phone: '15099836861',
            province: null,
            city: '深圳市',
            district: '光明区',
            detailsAddress: 'xxx',
            provinceCode: '440000',
            cityCode: '440300',
            districtCode: '440311',
            systemAccount: '370259',
            children: [],
            label: '测试机构-shencanlong',
            value: 3307
          }
        ],
        label: '深圳市博思高科技有限公司',
        value: 354
      }
    ]
  }
])

const tableData = ref([
  {
    prop1: 'row1value',
    prop2: 'row1value',
    prop3: 'row1value',
    prop4: 'row1value',
    prop5: 'row1value',
    prop6: 'row1value',
    prop7: 'row1value',
    prop8: 'row1value',
    prop9: 'row1value',
    prop10: 'row1value',
    prop11: 'row1value',
    prop12: 'row1value',
    prop13: 'row1value',
    prop14: 'row1value',
    prop15: 'row1value',
    prop16: 'row1value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  },
  {
    prop1: 'row2value',
    prop2: 'row2value',
    prop3: 'row2value',
    prop4: 'row2value',
    prop5: 'row2value',
    prop6: 'row2value',
    prop7: 'row2value',
    prop8: 'row2value',
    prop9: 'row2value',
    prop10: 'row2value',
    prop11: 'row2value',
    prop12: 'row2value',
    prop13: 'row2value',
    prop14: 'row2value',
    prop15: 'row2value',
    prop16: 'row2value'
  }
])


const tableDataVal = unref(tableData)

const fetch = (params) => {
  console.log('params >>>', params)
  return new Promise((resolve) => {
    setTimeout(() => {
      // 存在分页
      resolve({
        data: {
          rows: tableDataVal,
          total: tableDataVal.length
        },
        message: '获取数据成功'
      })
    }, 3000)
  })
}


// ---> E 列表 <---
</script>
<template>
  <div class="bsgoal-base-tree-table-demo">
    <div class="base_tree_table_demo">
      <BsgoalBaseTreeTable
        selection
        operation
        :page-size="40"
        :lazy-load="treeLazyLoad"
        :init-node="treeInitNode"
        :fetch="fetch"
        :config-options="configOptions"
        :expression="77"
        @on-click="triggerTreeClick"
      ></BsgoalBaseTreeTable>
    </div>
  </div>
</template>
<style lang="scss" scoped>
/* 自定义样式
---------------------------------------------------------------- */
</style>
<style lang="scss">
/* 覆盖样式
---------------------------------------------------------------- */
</style>

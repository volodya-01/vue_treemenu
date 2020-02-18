<template>
  <div class="treenode0">
    <div class="mytree">
      <el-tree :data="data" :indent="0" :props="defaultProps" @node-click="handleNodeClick"></el-tree>
    </div>
  </div>
</template>

<script>
export default {
  name: "treenode0",
  data() {
    return {
      data: [
        {
          label: "一级 1",
          children: [
            {
              label: "二级 1-1",
              children: [
                {
                  label: "三级 1-1-1"
                }
              ]
            }
          ]
        },
        {
          label: "一级 2",
          children: [
            {
              label: "二级 2-1",
              children: [
                {
                  label: "三级 2-1-1"
                }
              ]
            },
            {
              label: "二级 2-2",
              children: [
                {
                  label: "三级 2-2-1"
                }
              ]
            }
          ]
        },
        {
          label: "一级 3",
          children: [
            {
              label: "二级 3-1",
              children: [
                {
                  label: "三级 3-1-1"
                }
              ]
            },
            {
              label: "二级 3-2",
              children: [
                {
                  label: "三级 3-2-1"
                }
              ]
            }
          ]
        }
      ],
      defaultProps: {
        children: "children",
        label: "label"
      }
    };
  },
  methods: {
    handleNodeClick(data) {
      console.log(data);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "@/styles/global.scss";
.treenode0 {
  display: flex;
  flex-flow: column;
  justify-content: flex-start;
  align-items: flex-start;
  width: vw(1920);
  //height: vh(80);
  // background-color: #42b983;
  .mytree /deep/ {
    .el-tree > .el-tree-node:after {
      border-top: none;
    }
    .el-tree-node {
      position: relative;
      padding-left: 16px;
    }
    //节点有间隙，隐藏掉展开按钮就好了,如果觉得空隙没事可以删掉
    .el-tree-node__expand-icon.is-leaf {
      display: none;
    }
    .el-tree-node__children {
      padding-left: 16px;
    }

    .el-tree-node :last-child:before {
      height: 38px;
    }

    .el-tree > .el-tree-node:before {
      border-left: none;
    }

    .el-tree > .el-tree-node:after {
      border-top: none;
    }

    .el-tree-node:before {
      content: "";
      left: -4px;
      position: absolute;
      right: auto;
      border-width: 1px;
    }

    .el-tree-node:after {
      content: "";
      left: -4px;
      position: absolute;
      right: auto;
      border-width: 1px;
    }

    .el-tree-node:before {
      border-left: 1px dashed #4386c6;
      bottom: 0px;
      height: 100%;
      top: -26px;
      width: 1px;
    }

    .el-tree-node:after {
      border-top: 1px dashed #4386c6;
      height: 20px;
      top: 12px;
      width: 24px;
    }
  }
}
a {
  color: #42b983;
}
</style>

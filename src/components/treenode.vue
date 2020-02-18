<template>
  <div class="treenode">
    <div class="mytree">
      <el-tree
        :data="data"
        :props="defaultProps"
        @node-click="handleNodeClick"
        :render-content="renderContent"
      ></el-tree>
    </div>
  </div>
</template>

<script>
export default {
  name: "treenode",
  data() {
    return {
      data: [
        {
          id: 1,
          label: "group",
          className: "el-icon-s-shop",
          children: [
            {
              id: 11,
              label: "child",
              className: "el-icon-s-home"
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
    },
    renderContent(h, { node, data, store }) {
      return (
        <span>
          <i class={data.className}></i>
          <span>{node.label}</span>
        </span>
      );
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "@/styles/global.scss";
.treenode {
  display: flex;
  flex-flow: column;
  justify-content: flex-start;
  align-items: flex-start;
  width: vw(1920);
  height: vh(1080);
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
    .tree-icon {
      display: inline-block;
    }
    .child-class {
      //图标设置
      padding-right: 15px !important;
    }

    .group-class {
      //图标设置
    }

    .el-icon-s-shop:before {
      //content: "-";
      content: url("../assets/tree__division.png");
      padding-right: 8px !important;
    }
    .el-icon-s-home:before {
      content: url("../assets/tree__residential.png");
    }
    .el-tree-node__expand-icon {
      cursor: pointer;
      color: rgba($color: #000000, $alpha: 1);
      font-size: 12;
    }
    .el-icon-caret-right:before {
      //content: "-";
      content: url("../assets/1.png");
      padding-right: 8px !important;
    }
    .el-tree-node__expand-icon.expanded {
      -webkit-transform: rotate(0deg);
      transform: rotate(0deg);
    }
  }
}
a {
  color: #42b983;
}
</style>

<template>
  <div class="treenode">
    <div class="mytree">
      <el-tree
        :data="data"
        :props="defaultProps"
        @node-click="handleNodeClick"
        :render-content="renderContent"
        default-expand-all
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
          label: "PMA分区列表",
          className: "el-icon-s-shop",
          num: "",
          titlestyle: "titlestyle",
          children: [
            {
              id: 11,
              label: "静安区",
              className: "el-icon-s-home",
              numtype: "numtype0",
              num: "123",
              titlestyle: ""
            },
            {
              id: 12,
              label: "浦东区",
              className: "el-icon-s-home",
              numtype: "numtype",
              num: "231",
              titlestyle: ""
            },
            {
              id: 13,
              label: "徐汇区",
              className: "el-icon-s-home",
              numtype: "numtype",
              num: "156",
              titlestyle: ""
            },
            {
              id: 14,
              label: "虹口区",
              className: "el-icon-s-home",
              numtype: "numtype0",
              num: "456",
              titlestyle: ""
            },
            {
              id: 15,
              label: "宝山区",
              className: "el-icon-s-home",
              numtype: "numtype",
              num: "123",
              titlestyle: ""
            },
            {
              id: 16,
              label: "松江区",
              className: "el-icon-s-home",
              numtype: "numtype",
              num: "456",
              titlestyle: ""
            },
            {
              id: 17,
              label: "崇明区",
              className: "el-icon-s-home",
              numtype: "numtype",
              num: "756",
              titlestyle: ""
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
          <span class={data.titlestyle}>{node.label}</span>
          <span class={data.numtype}>{data.num}</span>
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
  align-items: center;
  width: vw(1920);
  height: vh(260);
  // background-color: #42b983;
  .mytree /deep/ {
    .el-tree {
      position: relative;
      cursor: default;
      background: #fff;
      color: #606266;
      width: 260px;
    }
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
      border-left: 1px solid #e4e7ed;
      bottom: 0px;
      height: 100%;
      top: -26px;
      width: 1px;
    }

    .el-tree-node:after {
      border-top: 1px solid #e4e7ed;
      height: 20px;
      top: 12px;
      width: 20px;
    }
    .tree-icon {
      display: inline-block;
    }
    .el-icon-s-shop {
      //width: 20px;
      position: relative;
      left: -20px;
    }
    .el-icon-s-home {
    }
    .el-icon-s-shop:before {
      //content: "-";
      content: url("../assets/tree__division.png");
      padding-right: 8px !important;
    }
    .el-icon-s-home:before {
      content: url("../assets/tree__residential.png");
      position: relative;
      top: 2px;
      margin-left: -13px;
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
    .numtype {
      display: inline-block;
      width: 40px;
      height: 20px;
      text-align: center;
      line-height: 20px;
      background-color: rgba($color: rgb(103, 138, 165), $alpha: 1);
      color: #fff;
      border-radius: 20px;
      // margin-left: 100px;
      position: relative;
      left: 100px;
    }
    .numtype0 {
      display: inline-block;
      width: 40px;
      height: 20px;
      text-align: center;
      line-height: 20px;
      background-color: rgba($color: #e73e3e, $alpha: 1);
      color: #fff;
      border-radius: 20px;
      //margin-left: 100px;
      position: relative;
      left: 100px;
    }
    .el-tree-node__content:hover {
      background-color: #e4e7ed;
      // margin-left: 25px;
    }
    .el-tree-node:focus > .el-tree-node__content {
      background-color: #e4e7ed;
      // margin-left: 25px;
    }
    .el-tree-node__content {
      padding-left: 16px !important;
      //width: 260px;
    }

    .el-tree-node__content > .el-tree-node__expand-icon {
      position: relative;
      left: -16px !important;
    }
    .titlestyle {
      position: relative;
      left: -25px !important;
    }
  }
}
a {
  color: #42b983;
}
</style>

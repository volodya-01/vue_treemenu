<template>
  <div class="hello">
    <!--      <div class="mytree">
      <el-tree :data="data" :indent="0" :props="defaultProps" @node-click="handleNodeClick"></el-tree>
    </div>
    <treenode0 />
    <div class="fline">分界线</div>
    <treenode />-->
    <div class="fline">
      <!-- 分界线 -->
    </div>
    <treenode1 />
    <div class="fline">
      <!-- 分界线 -->
    </div>
    <treenodecommon />
    <div class="fline">
      <!-- 分界线 -->
    </div>
    <treenodecommon2 />
    <div class="fline">
      <!-- 分界线 -->
    </div>
  </div>
</template>

<script>
import treenodecommon from "./treenodecommon";
import treenodecommon2 from "./treenodecommon2";
import treenode0 from "./treenode0";
import treenode from "./treenode";
import treenode1 from "./treenode1";
export default {
  name: "HelloWorld",
  components: {
    treenode0,
    treenode,
    treenode1,
    treenodecommon,
    treenodecommon2
  },
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
.hello {
  display: flex;
  flex-flow: column;
  justify-content: flex-start;
  align-items: flex-start;
  width: vw(1920);
  height: vh(1080);
  // background-color: #42b983;
  .fline {
    margin: 60px 0;
  }
}
a {
  color: #42b983;
}
</style>

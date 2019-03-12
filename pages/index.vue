<template>
  <el-table
      :data="tableData"
      style="width: 100%">
      <el-table-column
        prop="zh"
        label="账号">
      </el-table-column>
      <el-table-column
        prop="xm"
        label="姓名">
      </el-table-column>
      <el-table-column
        prop="bmmc"
        label="部门名称">
      </el-table-column>
    </el-table>
</template>

<script>
import Logo from '~/components/Logo.vue'
// var options = {};
// options.baseURL = "http://127.0.0.1:3000/"
// var instance = axios.create(options);


export default {
  async asyncData({ $axios }) {
    var {data} = await $axios.request({
      url: '/rest/JcYhglManage/select',
      method: 'POST',
      data: {
        dwbh: 1018
      }
    });
    console.log(111111, data);
    
    return {
      tableData: data
    }
  },
  components: {
    Logo
  },
  created() {
    
    
    // var url = 'http://www.yinyuetai.com/mv/get-first-video'  //网站的jsonp地址
  //   axios.defaults.headers['Content-Type']
  //   axios.request({
  //     url,
  //     header: {  //即将被发送的自定义请求头
  //         referer: 'http://m.yinyuetai.com/', //这两项在网站的NetWork中的Request Header中获得
  //         host: 'www.yinyuetai.com',
  //         'Access-Control-Allow-Origin': '*'   
  //     }
  //     // params: req.query  // 即将与请求被发送的URL参数
  // }).then((response) => {
  //     // res.json(response.data)  // 作为一个json返回
  //     console.log(response.data)
  // }).catch((e) => {
  //     console.log(e)  // 如果没有拿到数据，输出错误信息
  // })
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>

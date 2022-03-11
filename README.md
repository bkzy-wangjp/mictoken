# mictoken

 计算服务API接口TOKEN计算js包

 此包为`Java script`程序包，用于前台页面计算Token使用。

## 使用方法

在 `Java script` 程序中引入包：

```js
<script type="text/javascript" src="mictoken.js"></script>
```

在ajax请求中加入token:

```js
function getconfig(avm){
    const sql = "select(*).from(sys_unit).where(id<10).as(json)";
    const tstamp = new Date().getTime();
    axios({
        method:'get',
        baseURL:'http://127.0.0.1:8080/',
        url:'api/script/sql',
        params:{
            micsql:sql
            ,user:'admin'
            ,tstamp:tstamp
            ,token:getMicToken({micsql:sql,user:'admin',tstamp:tstamp},'df5cbcafc6a12759c6ac17e9f93e83516F7B')
        }
    }).then(function(response){
        console.log(response.data);
    });
};
```

详细示例参见 [计算Token方法测试](index.html)和[API测试](test.html)
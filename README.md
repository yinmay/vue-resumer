# vue-resumer

> A Vue.js project
* npm init -y
* npm i -g vue-cli
* vue init webpack .(当前目录)
* npm i
* npm run dev

* npm i -D sass-loader node-sass(用sass，不需要配置webpack)




### topbar

### 简历编辑

### 预览 

### 简历保存

* 全局注册:在new vue之前注册，不需要import,少用全局
```
Vue.component('Jack',{
    template:'<p>{{name}}</p>',
    data(){
        return{
            name:'Jack'
        }
    }
})

```


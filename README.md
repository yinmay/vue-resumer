# vue-resumer

> A Vue.js project
### initialize
* npm init -y
* npm i -g vue-cli
* vue init webpack .(当前目录)
* npm i
* npm run dev

* npm i -D sass-loader node-sass(用sass，不需要配置webpack)


### import element UI
* `npm i element-ui -S`
```
//eleme ui
import ElementUI from 'element-ui';
import 'element-ui/lib/theme-chalk/index.css';

Vue.use(ElementUI);

```

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


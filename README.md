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
 * import iconfont(symbol)
 * tab
```
   <li v-for="i in [0,1,2,3,4,5]"
       v-bind:class="{active:currentTab === i}"
       v-on:click="currentTab = i">
            <svg class="icon" >
            <use v-bind:xlink:href=" `#icon-${icons[i]}` "></use>
        </svg>
    </li>
    //替代
    <li v-bind:class="{active:currentTab === 0}" v-on:click="currentTab = 0">
         <svg class="icon" >
            <use xlink:href="#icon-shenfen"></use>
        </svg>
       </li>
     
```
```
     <li v-for="i in [0,1,2,3,4,5]" 
         v-bind:class="{active:currentTab === i}">
         tab {{i+1}}
     </li>

     //替代
     <li v-bind:class="{active:currentTab === 1}">tab 2</li>
```

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

* 解决404问题就是添加目录或者减目录
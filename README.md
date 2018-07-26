# vue-toast
vue-toast插件测试

##Usage
###Install:

```aidl
npm install sl-toast --save-dev
```

###Import:

```aidl
import 'vue2-toast/lib/toast.css';
import Toast from 'vue2-toast';
Vue.use(Toast);
```

###Extend
```aidl
Vue.use(Toast, {
    defaultType: 'center',
    duration: 3000,
    wordWrap: true,
    width: '150px'
});
```

###Use in component:

```aidl
<template>
    <div id="app">
        <button @click="openTop()">top</button>
        <button @click="openCenter()">center</button>
        <button @click="openBottom()">bottom</button>
		<button @click="openLoading()">loading</button>
    </div>
</template>
export default {
    methods:{
        openTop(){
            this.$toast.top('top');
        },
        openCenter(){
            this.$toast.center('center');
        },
        openBottom(){
            this.$toast('bottom');  // or this.$toast.bottom('bottom'); 
        },
        openLoading(){
            this.$loading('loading...');
			let self = this;
	        setTimeout(function () {
	          self.closeLoading()
	        }, 2000)
        },
        closeLoading(){
            this.$loading.close();
        }
    }
}
```


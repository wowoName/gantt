<h1 align="center">lgjs-gantt</h1>
# LgjGantt
<p align="center"><img src="https://github.com/wowoName/gantt/blob/main/demo.jpg" alt="logo"></p>
## 安装

```bash
npm install lgjs-gantt -s
```

注册:

```js
import 'lgjs-gantt/lgjs-gantt.css'
import LgjGantt from 'lgjs-gantt'
Vue.use(LgjGantt)
```

使用：

```vue
<template>
  <div>
    <input type="button" value="自适应" @click="zoomToFit()" />
    <LgjGantt ref="gantt" :task-datas="taskDatas" :resource-datas="resourceDatas" startDates="2021-01-01 10:9:00" endDates="2021-01-05 00:00:00" viewPresets="minute" @editTask="editTask" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      resourceDatas: [
        {
          name: '泳道一',
          id: 'lane1',
        },
      ],
      taskDatas: [
        {
          resourceId: 'lane1',
          name: '1',
          startDate: '2021-01-01 10:10:00',
          endDate: '2021-01-01 12:00:00',
        },
      ],
    }
  },
  methods: {
    /**
     * 自适应
     */
    zoomToFit() {
      this.$refs.gantt.taskLayout.zoomToFit()
    },
    // 编辑事件
    editTask(taskRecord) {
      console.log('编辑事件', taskRecord)
    },
  },
}
</script>
```

### Props

#### resourceDatas

Type: `Array`<br>
Required: `false`<br>
Default: `[]`
泳道数据（左侧资源树）

```html
<lgjs-gantt :resource-datas="[]"></lgjs-gantt>
```

#### taskDatas

Type: `Array`<br>
Required: `false`<br>
Default: `[]`
事件

```html
<lgjs-gantt :task-datas="[]"></lgjs-gantt>
```

#### startDates

Type: `String`<br>
Required: `false`<br>
Default: `2000-01-01 00:00:00`
时间轴开始日期

```html
<lgjs-gantt startDates="2000-01-01 00:00:00"></lgjs-gantt>
```

#### endDates

Type: `String`<br>
Required: `false`<br>
Default: `2000-10-01 00:00:00`
时间轴结束日期

```html
<lgjs-gantt endDates="2000-10-01 00:00:00"></lgjs-gantt>
```

#### viewPresets

Type: `String`<br>
Required: `false`<br>
Default: `month`
时间轴缩放级别

```html
<lgjs-gantt viewPresets="minute"></lgjs-gantt>
```

## 联系方式

```
QQ：1069722589
```

## License

[MIT license](LICENSE)


```bash
# 进入docker环境内部

cd api

# 修改 taskProcessor.js

```

```js

let do_task = false;

if (isTest) {
    do_task = true;
} else {
    if (!task.last_time) do_task = true;
    if (task.last_time && dayjs(task.last_time).add(task.minutes, 'minutes').isBefore(dayjs())) {
        do_task = true;
    }
}
/*新增逻辑 分钟配置成-1的收，禁用*/
if(task.minutes==-1){
        do_task = false;
}

if (!do_task)
{ 
    /*增加日志，提示哪一个rss记录没有添加到当前的任务队列里面*/
    console.log("task "+ task.title+" not allow add ")
    return;
}

    /*增加日志，提示哪一个rss记录会添加到当前的任务队列里面*/
console.log("task "+ task.title+"  add ")



```
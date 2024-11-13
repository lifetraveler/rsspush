
```bash
# 进入docker环境内部

cd api

# 修改 taskProcessor.js
# cron.js
```

```js
/* taskProcessor.js */
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

/* cron.js */
 let  do_task = false;

        if(!tasks[index]?.last_time ) do_task = true;

        if(tasks[index].last_time && dayjs(tasks[index].last_time).add(tasks[index].minutes,'minutes').isBefore(dayjs()))
        {
            do_task = true;
        }
        /*............ ...............-1...............*/
        if(tasks[index].minutes==-1){
            do_task = false;
        }
        if( !do_task ){

    /*..............................rss................................................*/
            console.log("task "+ tasks[index].title+" not allow add ")
         continue;}
        // if(   minutes % tasks[index].minutes != 0 ) continue;
        let requestOptions = {};
        console.log("task "+ tasks[index.title+"  add ")

```

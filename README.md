# todo-ddl
Todo CLI with DDLs on nodejs.


## Architecture

### overview

```js
|todo-ddl
|
|---config
|   |---email
|   |---remote url
|
|---td
|   |---task
|   |---todo
|   |---history
|
|---ddl
|
|---log
|

```

### td structure

```js

td new        td add        td done
------>      -------->     --------->
        task          todo           history
<------     <--------      <---------
  td rm       td return      td recover

```




## Commands

### config set
+ `td config [-e email] [-r remote]`: Set 


### td set

+ `td new <name> [class]`: Create new tesk..
+ `td add <id>`: Add task to todo..
+ `td done <id>`: Finish todo..
+ `td recover`: Recover todo from history..
+ `td return <id>`: Return todo to task..
+ `td rm <id>`: Remove task..

+ `td ls`: List todos..
+ `td lt`: List tasks..
+ `td history`: List history

### log set

+ `td select <id>`: Select todo for loging..
+ `td log <comment>`: Record logs..
+ `td ll`: List logs..
+ `td rml <id>`: Remove log..

### ddl set

+ `td newd <name> <date>`: Create new ddl..
+ `td link <ddlID> <tdID>`: Link task to ddl..
+ `td ld`: List ddls..
+ `td rmd <id>`: Remove ddl..

### systemctl

+ `td init`: Reset all..
+ `td push`: Push local to remote..
+ `td pull`: Pull from remote..
+ `td sync`: Sync with remote..


## Data structure

```js
config:{
  email: "",
  remote: "https://api.yimian.xyz/todo-ddl/"
}


data:{
  td:{[{
    id: 'a2s3s2ds',
    name: '',
    class: 'default',
    createTime: (new Date()).valueOf(),
    todoTime: (new Date()).valueOf(),
    endTime: (new Date()).valueOf(),
    idDel: false,
    logs: [{
      id: 'fdkr8ei9odleiw93',
      content: '',
      createTime: (new Date()).valueOf()
    }]
  }]},
  
  ddl: {[{
    id: 'di8eio',
    name: '',
    class: 'default',
    link: [<tdID>],
    createTime: (new Date()).valueOf(),
    expireTime: (new Date()).valueOf(),
  }]}
}

```

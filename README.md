# qlogfetch
融合CDN日志下载工具

### 简介
qlogFetch是一个七牛CDN日志文件查询及下载的命令行工具。


### 使用
调用七牛的API需要一对`AccessKey`和`SecretKey`，这个可以从七牛的后台的账号设置->[密钥](https://portal.qiniu.com/user/key)获取。

首先要使用必须设置`AccessKey`和`SecretKey`。命令如下：

```bash
qlogfetch reg -ak <Access_Key> -sk <Secret_Key>
```
如果你想查看当前的`AccessKey`和`SecretKey`设置，使用命令：

```
qlogfetch info
```
### 帮助信息
如果想获取命令帮助信息 统一采用以下方式

```bash
	qlogfetch -h
	qlogfetch <cmd> -h
```

### 功能

|命令|描述|
|------|----------|
|reg|设置当前用户的AccessKey和SecretKey|
|info|显示当前设置的AccessKey和SecretKey|
|listlog|列出某日指定域名的日志文件列表|
|downlog|下载指定日期某域名下的所有日志文件|
|domains|查询账户下的所有域名|

### 详解
date请采用 20xx-xx-xx 的格式

#### 1.listlog 
> -header 为可选项

```bash
qlogfetch [-header] -date <Date> -domain <Domain>
example: qlogfetch listlog -date '2016-11-23' -domain 'img.abc.com'
```


##### downlow
>worker 为并发下载数,默认为1 
>如果网速不够快 不建议设置worker

```bash
qlogfetch downlog -date <Date> -domain <Domain> -dest <DestDir> -worker <Worker>
example: qlogfetch downlog -date '2016-11-23' -domain 'img.abc.com' -dest '/tmp/logs'
```


## FeedBack
如果使用遇到问题或者发现bug，欢迎及时反馈   \^_^


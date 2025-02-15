# 服务 sc - Windows 服务管理

## 列出服务
sc query type=service state= all
加上 > log.log 输出日志

## 启动/停止服务
sc [start/stop/pause/continue] [服务名]

## 删除服务
sc delete [服务名]



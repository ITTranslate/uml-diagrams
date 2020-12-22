@startuml
start
:<b>Exception</b>;
note right
//Pooling, Default: true//
====
<b>MySqlException:</b>
* User juxxxxxxxxxx already has more than 
max_user_connections active connections
end note

fork
:Thread.Sleep;
note left
降低 CRUD 频率
====
在循环中添加 //Thread.Sleep//
end note

#SkyBlue:连接数：280，
运行 68 分钟;
floating note left: 运行结果

fork again
:Pooling=false;
note right
禁用连接池
====
在连接字符串中添加 //Pooling=false;//
end note
#SkyBlue:连接数：5，
运行8分钟;
floating note right: 运行结果
endfork

:<b>运行完成</b>;
@enduml
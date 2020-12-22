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
���� CRUD Ƶ��
====
��ѭ������� //Thread.Sleep//
end note

#SkyBlue:��������280��
���� 68 ����;
floating note left: ���н��

fork again
:Pooling=false;
note right
�������ӳ�
====
�������ַ�������� //Pooling=false;//
end note
#SkyBlue:��������5��
����8����;
floating note right: ���н��
endfork

:<b>�������</b>;
@enduml
```
@startuml
start
:"步骤 1 处理";
:"步骤 2 处理";
if ("条件 1 判断") then (true)
:条件 1 成立时执行的动作;
if ("分支条件 2 判断") then (no)
:"条件 2 不成立时执行的动作";
else
if ("条件 3 判断") then (yes)
:"条件 3 成立时的动作";
else (no)
:"条件 3 不成立时的动作";
endif
endif
:"顺序步骤 3 处理";
endif

if ("条件 4 判断") then (yes)
:"条件 4 成立的动作";
else
if ("条件 5 判断") then (yes)
:"条件 5 成立时的动作";
else (no)
:"条件 5 不成立时的动作";
endif
endif
stop
@enduml
```

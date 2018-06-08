# 数据库设计 [返回](../README.md)

- ## Users表（用户表）

    
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:--:|:--:|:--:|:--:|:--:|:--:|:--|
|id|varchar(20)|主键|否|||学号、教师编号、管理员编号|
|passwowrd|varchar(20)||否||||
|name|varchar(12)||否||||
|identity|int||否|||身份，0-管理员，1-老师，2-学生|
|class|varchar(20)||是||||
|github|varchar(128)||是|||github网址|

- ## Course表(课程表)
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:--:|:--:|:--:|:--:|:--:|:--:|:--|
|id|varchar(20)|主键|否|||课程编号|
|creator|varchar(20)|外键|否|||对应教师编号|
|name|varchar(56)||否|||课程名|

- ## Experiments表(实验表)
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:--:|:--:|:--:|:--:|:--:|:--:|:--|
|id|varchar(20)|主键|否|||实验编号|
|studentid|varchar(20)|主键|否|||对应学生编号|
|course|varchar(20)|外键|否|||对应课程编号|
|name|varchar(20)||否|||实验名|
|score|float||是|||总分|
|content|varchar(52000)||否|||实验内容|

- ## Score表(分数表)
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:--:|:--:|:--:|:--:|:--:|:--:|:--|
|experimentid|varchar(20)|主键|否|||实验编号|
|studentid|varchar(20)|主键|否|||学生编号|
|score|float||是|||总分|
|score1|float||是|||评分项1|
|score2|float||是|||评分项2|
|score3|float||是|||评分项3|
|score4|float||是|||评分项4|
|score5|float||是|||评分项5|
|comment|varchar(4096)||是|||老师点评信息|

- ## StuCourse表(选课表)
|字段|类型|主键、外键|可以为空|默认值|约束|说明|
|:--:|:--:|:--:|:--:|:--:|:--:|:--|
|courseid|varchar(20)|主键|否|||课程编号|
|studentid|varchar(20)|主键|否|||学生编号|
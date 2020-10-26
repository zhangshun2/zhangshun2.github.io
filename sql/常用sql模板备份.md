# 常用sql模板备份

> @author zhangshun
>

## MYSQL

---

~~~sql
-- 根据字段名模糊查询在那个表,叫啥名
select COLUMN_COMMENT as cc , COLUMN_NAME,TABLE_NAME from information_schema.COLUMNS where COLUMN_COMMENT like '%字段名%';
~~~
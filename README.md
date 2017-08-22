{ "name": <строка>
, "short_name": <строка>
, "email": <строка>
, "legal_person_post_id": [<число>,...]
, "inn": <число>
, "legal_person_role_list" :
        [ { "role_id": <число>,
            "infrastructure_list":[<строка>,...],
            "okrug_id": [<число>,..]
          }
        , ...
        ]
}
-- 1. Найти строки таблицы где ключ "name" содержит значение "зоди"
-- Пусть таблица будет называться "okrugs"
select * from okrugs where name like '%зоди%' or name like '%зоди' or name like 'зоди%';

-- 2. Найти строки таблицы где ключ "name" содержит значение "зоди", а также где ключ legal_person_post_id содержит значения 1,2,3
select * from okrugs where ((name like '%зоди%' or name like '%зоди' or name like 'зоди%') and legal_person_post_id in (1,2,3)); 

-- 3. Найти строки таблицы где ключ "role_id" = 5 или 6
select * from okrugs where role_id=5 or role_id=6;

-- 4. Найти строки таблицы где ключ "okrug_id" содержит только значение 99
select * from okrugs where okrug_id like '%99' or okrug_id like '99%' or okrug_id like '%99%';

--5. Найти строки таблицы где ключ "infrastructure_list" содержит хотя бы одно значение в котором содержится слово "интернет"
select * from okrugs where infrastructure_list like 'интернет%';

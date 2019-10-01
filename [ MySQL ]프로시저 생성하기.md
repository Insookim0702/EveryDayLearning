# MySQL

# 프로시저 생성하기
```

-- 프로시저 생성
DELIMITER $$
CREATE PROCEDURE 프로시저이름()
BEGIN
	-- SET i =396;
    DECLARE i INT DEFAULT 396;
    -- DELETE FROM tbl_infodata;
    WHILE i <= (SELECT extdata_id FROM if_extdata ORDER BY extdata_id DESC LIMIT 1) DO
        INSERT INTO tbl_infodata(title,date,image,linkurl,content,attach,url,seedName) VALUE(
	   (SELECT ExtractValue((SELECT extdata_content from if_extdata where extdata_id=i), '//DataItem[./@name="title"]')),
	   (SELECT ExtractValue((SELECT extdata_content from if_extdata where extdata_id=i), '//DataItem[./@name="date"]')),
       (SELECT ExtractValue((SELECT extdata_content from if_extdata where extdata_id=i), '//DataItem[./@name="image"]//Url')),
       (SELECT ExtractValue((SELECT extdata_content from if_extdata where extdata_id=i), '//DataItem[./@name="EXTRACTHREF"]')),
       (SELECT ExtractValue((SELECT extdata_content from if_extdata where extdata_id=i), '//DataItem[./@name="content"]')),
       (SELECT ExtractValue((SELECT extdata_content from if_extdata where extdata_id=i), '//DataItem[./@name="attach"]//Url')),
	   (SELECT ExtractValue((SELECT extdata_content from if_extdata where extdata_id=i), '//DataItem[./@name="url"]')),
       (SELECT seed_name FROM if_seed WHERE seed_id = (SELECT seed_id FROM if_extdata WHERE extdata_id = i))
);
        SET i = i + 1;
    END WHILE;
END$$
DELIMITER $$

```

# 프로시저 삭제하기
```
-- 프로시저 삭제하기
DROP PROCEDURE IF EXISTS 프로시저이름$$
```

# 프로시저만 실행하기
```
-- 프로시저만 실행하기
CALL 프로시저 이름();
```

```
ex)
CALL extractFromExtdata_content();
```

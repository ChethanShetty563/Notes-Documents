
### 1) Character Data

* Character data can be stored as either fixed length or variable length
```sql
char(20) /* fixed length*/
varchar(20) /* variable length*/
```

* The diff is that fixed length are padded with right padded with spaces and iyt always consumes specified amout of memory always
* Varibale length are not right padded, it doesn't consume always the same number of bytes. You define the most number bytes it can store.
* The maximum length for "char" columns is 255 bytes
* The maximum length for varchar is 65535 bytes
* To store string we use the above 2 data types

### 2) Character Sets

* Languages that use latin alphabet, such as English, there is sufficienly small number of characters and they need single byte to store each character
* Other languages such as Japanese and korean contain large number of characters , thus it requires multiple bytes of storage for each character. These are therefore called multibyte character sets
* MySQL supports the below Character sets

```sql
To view the character sets

SHOW CHARACTER SET;
+----------+---------------------------------+---------------------+--------+
| Charset  | Description                     | Default collation   | Maxlen |
+----------+---------------------------------+---------------------+--------+
| armscii8 | ARMSCII-8 Armenian              | armscii8_general_ci |      1 |
| ascii    | US ASCII                        | ascii_general_ci    |      1 |
| big5     | Big5 Traditional Chinese        | big5_chinese_ci     |      2 |
| binary   | Binary pseudo charset           | binary              |      1 |
| cp1250   | Windows Central European        | cp1250_general_ci   |      1 |
| cp1251   | Windows Cyrillic                | cp1251_general_ci   |      1 |
| cp1256   | Windows Arabic                  | cp1256_general_ci   |      1 |
| cp1257   | Windows Baltic                  | cp1257_general_ci   |      1 |
| cp850    | DOS West European               | cp850_general_ci    |      1 |
| cp852    | DOS Central European            | cp852_general_ci    |      1 |
| cp866    | DOS Russian                     | cp866_general_ci    |      1 |
| cp932    | SJIS for Windows Japanese       | cp932_japanese_ci   |      2 |
| dec8     | DEC West European               | dec8_swedish_ci     |      1 |
| eucjpms  | UJIS for Windows Japanese       | eucjpms_japanese_ci |      3 |
| euckr    | EUC-KR Korean                   | euckr_korean_ci     |      2 |
| gb18030  | China National Standard GB18030 | gb18030_chinese_ci  |      4 |
| gb2312   | GB2312 Simplified Chinese       | gb2312_chinese_ci   |      2 |
| gbk      | GBK Simplified Chinese          | gbk_chinese_ci      |      2 |
| geostd8  | GEOSTD8 Georgian                | geostd8_general_ci  |      1 |
| greek    | ISO 8859-7 Greek                | greek_general_ci    |      1 |
| hebrew   | ISO 8859-8 Hebrew               | hebrew_general_ci   |      1 |
| hp8      | HP West European                | hp8_english_ci      |      1 |
| keybcs2  | DOS Kamenicky Czech-Slovak      | keybcs2_general_ci  |      1 |
| koi8r    | KOI8-R Relcom Russian           | koi8r_general_ci    |      1 |
| koi8u    | KOI8-U Ukrainian                | koi8u_general_ci    |      1 |
| latin1   | cp1252 West European            | latin1_swedish_ci   |      1 |
| latin2   | ISO 8859-2 Central European     | latin2_general_ci   |      1 |
| latin5   | ISO 8859-9 Turkish              | latin5_turkish_ci   |      1 |
| latin7   | ISO 8859-13 Baltic              | latin7_general_ci   |      1 |
| macce    | Mac Central European            | macce_general_ci    |      1 |
| macroman | Mac West European               | macroman_general_ci |      1 |
| sjis     | Shift-JIS Japanese              | sjis_japanese_ci    |      2 |
| swe7     | 7bit Swedish                    | swe7_swedish_ci     |      1 |
| tis620   | TIS620 Thai                     | tis620_thai_ci      |      1 |
| ucs2     | UCS-2 Unicode                   | ucs2_general_ci     |      2 |
| ujis     | EUC-JP Japanese                 | ujis_japanese_ci    |      3 |
| utf16    | UTF-16 Unicode                  | utf16_general_ci    |      4 |
| utf16le  | UTF-16LE Unicode                | utf16le_general_ci  |      4 |
| utf32    | UTF-32 Unicode                  | utf32_general_ci    |      4 |
| utf8     | UTF-8 Unicode                   | utf8_general_ci     |      3 |
| utf8mb4  | UTF-8 Unicode                   | utf8mb4_0900_ai_ci  |      4 |
+----------+---------------------------------+---------------------+--------+
41 rows in set (0.04 sec)

```

If the value in the fourth column, `maxlen`, is greater than 1, then the character set is a multibyte character set.

* In previous version the latin1 was the default character set. 
* In the latest version 8 defaults to "utf8mb4"

To Set the Charcater set for the colmns use below step;

```sql
varchar(20) character set latin1;
```

In MYSQL you can set the character set for entire database as below

```sql
create database european_sales character set latin1;
```

### 2) Text data

If you need to store the data that might exceed the 64 kb limit for varchar columns, you will need to use one of the text types

| Text Type | MAximum number of bytes|
|---|---|
| tinytext | 255 |
| text | 65535 |
| mediumtext | 16777215 |
| longtext | 4,294,967,295 |

To choose the above text types you should be aware of following

* If the data being loaded into text column exceed the max size, the data will be truncated
* Trailing spaces will not be removed when data is loaded into the column.
* The different text types are unique to MySQL. SQL Server has a single `text` type for large character data, whereas DB2 and Oracle use a data type called `clob`, for Character Large Object.
*  Now that MySQL allows up to 65,535 bytes for `varchar` columns (it was limited to 255 bytes in version 4), there isn’t any particular need to use the `tinytext` or `text` type.

### Numeric Data

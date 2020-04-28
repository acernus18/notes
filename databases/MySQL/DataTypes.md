
# Number

> For integer data types, M indicates the maximum display width. 
> The maximum display width is 255. Display width is unrelated to the range of values a type can store.
> As of MySQL 8.0.17, the display width and ZEROFILL attribute is deprecated for integer data types.


| TYPE                                           | SIZE\(Byte\) | GOLANG | COMMENT                   |
|:----------------------------------------------:|:------------:|:------:|:-------------------------:|
| TINYINT\[\(M\)\] \[UNSIGNED\] \[ZEROFILL\]     | 1            | int8   | Nil                       |
| SMALLINT\[\(M\)\] \[UNSIGNED\] \[ZEROFILL\]    | 2            | int16  | Nil                       |
| MEDIUMINT\[\(M\)\] \[UNSIGNED\] \[ZEROFILL\]   | 3            | int32  | Nil                       |
| INT/INTEGER\[\(M\)\] \[UNSIGNED\] \[ZEROFILL\] | 4            | int32  | Nil                       |
| BIGINT\[\(M\)\] \[UNSIGNED\] \[ZEROFILL\]      | 8            | int64  | Nil                       |

| TYPE                                             | SIZE\(Byte\)   | GOLANG        | COMMENT                                                    |
|:------------------------------------------------:|:--------------:|:-------------:|:----------------------------------------------------------:|
| DECIMAL\[\(M\[,D\]\)\] \[UNSIGNED\] \[ZEROFILL\] | MAX\(M, D\)\+2 | RawBytes      |  M: the precision, D: the scale                            |
| FLOAT \[UNSIGNED\] \[ZEROFILL\]                  | 4              | float32       | The actual range depending on hardware or operating system |
| DOUBLE \[UNSIGNED\] \[ZEROFILL\]                 | 8              | float64       | The actual range depending on hardware or operating system |

| TYPE      | SIZE\(Byte\) | GOLANG   | COMMENT                                          |
|:---------:|:------------:|:--------:|:------------------------------------------------:|
| DATE      | 3            | NullTime | 'YYYY\-MM\-DD'                                   |
| TIME      | 3            | RawBytes | 'hh:mm:ss\[\.fraction\]'                         |
| DATETIME  | 8            | NullTime | 'YYYY\-MM\-DD hh:mm:ss\[\.fraction\]'            |
| TIMESTAMP | 4            | NullTime | '1970\-01\-01 00:00:01'\-'2038\-01\-19 03:14:07' |

> The effective maximum length of a VARCHAR is subject to the maximum row size and the character set used. 
> For example, utf8 characters can require up to three bytes per character, 
> so a VARCHAR column that uses the utf8 character set can be declared to be a maximum of 21,844 characters.

| TYPE                                              | SIZE\(Byte\) | GOLANG   | COMMENT                   |
|:-------------------------------------------------:|:------------:|:--------:|:-------------------------:|
| CHAR\[\(M\)\] \[CHARACTER SET cs\] \[COLLATE cl\] | M            | RawBytes | M in \[0, 255\] default 1 |
| VARCHAR\(M\) \[CHARACTER SET cs\] \[COLLATE cl\]  | M            | RawBytes | M in \[0, 65535\]         |
| MEDIUMTEXT \[CHARACTER SET cs\] \[COLLATE cl\]    | \-           | RawBytes | M in \[0, 16777215\]      |

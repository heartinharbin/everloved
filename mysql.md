# charset(uft8 与 utf8mb4), collate是什么

1. ## MySQL 的“utf8”实际上不是真正的 UTF-8

   > 在MySQL中，“utf8”编码只支持每个字符最多三个字节，而真正的 UTF-8 是每个字符最多四个字节。

   在utf8编码中，中文是占3个字节，其他数字、英文、符号占一个字节

   但emoji符号占4个字节，一些较复杂的文字、繁体字也是4个字节。所以导致写入失败，应该改成utf8mb4

2. ## utf8mb4 才是真正的UTF-8

   所有在使用“utf8”的 MySQL 和 MariaDB 用户都应该改用“utf8mb4”，永远都不要再使用“utf8”

   > 旧版的 UTF-8 标准（RFC 2279）最多支持每个字符 6 个字节
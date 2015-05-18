# Menutree V 1.0

最初用于对于后台管理系统->菜单及权限的数据库表的->极简设计（只标明继承关系）

最后将此 二维数据表 转化为 多维数据数组的公共方法提出：

Example:
1  数据库表：\<br /\>
   id    parent .....\<br /\>
    1       0\<br /\>
    2       0\<br /\>
    3       1\<br /\>
    4       1\<br /\>
    5       4\<br /\>
2   得到相应数组（此处 JSON 表示）
Array\<br /\>
( \<br /\>
    [0] => Array\<br /\>
        (\<br /\>
            [id] => 1\<br /\>
            [parent] => 0\<br /\>
            [data] => \<br /\>
        )\<br /\>

    [1] => Array
        (
            [id] => 2
            [parent] => 0
            [data] => 
        )

    [2] => Array
        (
            [id] => 3
            [parent] => 1
            [data] => 
        )

    [3] => Array
        (
            [id] => 4
            [parent] => 1
            [data] => 
        )

    [4] => Array
        (
            [id] => 5
            [parent] => 4
            [data] => 
        )

)

3  Menutree 整理

Array
(
    [2] => Array
        (
            [id] => 2
            [parent] => 0
            [data] => 
        )

    [1] => Array
        (
            [id] => 1
            [parent] => 0
            [data] => 
            [child] => Array
                (
                    [4] => Array
                        (
                            [id] => 4
                            [parent] => 1
                            [data] => 
                            [child] => Array
                                (
                                    [5] => Array
                                        (
                                            [id] => 5
                                            [parent] => 4
                                            [data] => 
                                        )

                                )

                        )

                    [3] => Array
                        (
                            [id] => 3
                            [parent] => 1
                            [data] => 
                        )

                )

        )

)

  

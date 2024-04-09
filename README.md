# MediaRecognitionRule

## 自定义识别词识别规则

###规则划分

规则使用yaml语法，总体分为三类

1. 通用规则 `common.yaml`
2. 电影规则 `movie.yaml`
3. 电视剧规则 tv.yaml



### 规则描述

- 通用规则

  - 格式如下：

    ```
    common:
      - type: 1
        replaced: '[【\[](Fin|END)[】\]]|(?:|\s|\s-\s)(Fin|END)(?=\])|(?<=\d{1,2})(Fin|END)'
        replace: ''
        front: ''
        back: ''
        offset: ''
        season: -1
        help: '通用动漫识别'
    ```

    

- 电视电影规则

  - 格式与通用规则一致，common 改为对应的tmdbid

    ```yaml
    229676:
      - type: 1
        replaced: 'Ookami to Koushinryou：'
        replace: ''
        front: ''
        back: ''
        offset: ''
        season: -1
        help: '狼与香辛料 行商邂逅贤狼 (2024)'
    
    ```

- 字段描述

  - type: 替换类型
    - 1 屏蔽
    - 2 替换
    - 3 替换+集偏移
    - 4 集偏移
  - replaced: 被替换内容
  - replace: 替换的内容
  - front: 前定位词，定位集数用
  - back: 后定位词，定位集数用
  - offset: 集偏移
  - season: 电视剧第几季，-1 表示所有季
  - help: 规则说明

# 信息检索与推荐期末大作业——关于Last.fm数据集的设计方案

如果你喜欢，请给我一个星星。❤️❤️❤️⭐⭐⭐

pls give me a star if you like. heart.❤️❤️❤️⭐⭐⭐
## 数据集介绍

Last.fm提供音乐推荐的数据集。 该数据集包含来自Last.fm在线音乐系统的一组2k用户，以及他们提供的社交网络、标签和音乐艺术家收听信息

下载地址：https://grouplens.org/datasets/hetrec-2011/

### artists.dat

|       |     0 |                 1 |                                            2 |                                                 3 |
| ----: | ----: | ----------------: | -------------------------------------------: | ------------------------------------------------: |
|     0 |    id |              name |                                          url |                                        pictureURL |
|     1 |     1 |      MALICE MIZER |        http://www.last.fm/music/MALICE+MIZER |   http://userserve-ak.last.fm/serve/252/10808.jpg |
|     2 |     2 |   Diary of Dreams |     http://www.last.fm/music/Diary+of+Dreams | http://userserve-ak.last.fm/serve/252/3052066.jpg |
|     3 |     3 | Carpathian Forest |   http://www.last.fm/music/Carpathian+Forest | http://userserve-ak.last.fm/serve/252/40222717... |
|     4 |     4 |      Moi dix Mois |        http://www.last.fm/music/Moi+dix+Mois | http://userserve-ak.last.fm/serve/252/54697835... |
|   ... |   ... |               ... |                                          ... |                                               ... |
| 17628 | 18741 |    Diamanda Galás | http://www.last.fm/music/Diamanda+Gal%C3%A1s | http://userserve-ak.last.fm/serve/252/16352971... |
| 17629 | 18742 |            Aya RL |              http://www.last.fm/music/Aya+RL |  http://userserve-ak.last.fm/serve/252/207445.jpg |
| 17630 | 18743 |       Coptic Rain |         http://www.last.fm/music/Coptic+Rain |  http://userserve-ak.last.fm/serve/252/344868.jpg |
| 17631 | 18744 |      Oz Alchemist |        http://www.last.fm/music/Oz+Alchemist | http://userserve-ak.last.fm/serve/252/29297695... |
| 17632 | 18745 |  Grzegorz Tomczak |    http://www.last.fm/music/Grzegorz+Tomczak | http://userserve-ak.last.fm/serve/252/59486303... |

17633 rows × 4 columns

此表为音乐艺术家表，列出了该数据集中的所有音乐艺术家

需要使用到的数据介绍：

id：音乐艺术家id

name：音乐艺术家的名字

### tags.dat

|       |     0 |                 1 |
| ----: | ----: | ----------------: |
|     0 | tagID |          tagValue |
|     1 |     1 |             metal |
|     2 |     2 | alternative metal |
|     3 |     3 |         goth rock |
|     4 |     4 |       black metal |
|   ... |   ... |               ... |
| 11942 | 12644 |             suomi |
| 11943 | 12645 |         symbiosis |
| 11944 | 12646 |           sverige |
| 11945 | 12647 |              eire |
| 11946 | 12648 |    electro latino |

11947 rows × 2 columns

此表为标签表，列出了该数据集中的所有标签

需要使用到的数据介绍：

tagID：对音乐艺术家评价的标签id

tagValue：对音乐艺术家的标签内容

### user_artists.dat

|       |      0 |        1 |      2 |
| ----: | -----: | -------: | -----: |
|     0 | userID | artistID | weight |
|     1 |      2 |       51 |  13883 |
|     2 |      2 |       52 |  11690 |
|     3 |      2 |       53 |  11351 |
|     4 |      2 |       54 |  10300 |
|   ... |    ... |      ... |    ... |
| 92830 |   2100 |    18726 |    337 |
| 92831 |   2100 |    18727 |    297 |
| 92832 |   2100 |    18728 |    281 |
| 92833 |   2100 |    18729 |    280 |
| 92834 |   2100 |    18730 |    263 |

92835 rows × 3 columns

此表列出了该数据集中的用户对音乐艺术家的感兴趣程度

需要使用到的数据介绍：

userID：用户id

artistID：音乐艺术家id

weight：用户对该音乐艺术家的兴趣权重

### user_friends.dat

|       |      0 |        1 |
| ----: | -----: | -------: |
|     0 | userID | friendID |
|     1 |      2 |      275 |
|     2 |      2 |      428 |
|     3 |      2 |      515 |
|     4 |      2 |      761 |
|   ... |    ... |      ... |
| 25430 |   2099 |     1801 |
| 25431 |   2099 |     2006 |
| 25432 |   2099 |     2016 |
| 25433 |   2100 |      586 |
| 25434 |   2100 |      607 |

25435 rows × 2 columns

此表为列出了该数据集中用户与用户之间的朋友关系

需要使用到的数据介绍：

userID：用户id

friendID：用户的朋友id

### user_taggedartists.dat

|        |      0 |        1 |     2 |    3 |     4 |    5 |
| -----: | -----: | -------: | ----: | ---: | ----: | ---: |
|      0 | userID | artistID | tagID |  day | month | year |
|      1 |      2 |       52 |    13 |    1 |     4 | 2009 |
|      2 |      2 |       52 |    15 |    1 |     4 | 2009 |
|      3 |      2 |       52 |    18 |    1 |     4 | 2009 |
|      4 |      2 |       52 |    21 |    1 |     4 | 2009 |
|    ... |    ... |      ... |   ... |  ... |   ... |  ... |
| 186475 |   2100 |    16437 |     4 |    1 |     7 | 2010 |
| 186476 |   2100 |    16437 |   292 |    1 |     5 | 2010 |
| 186477 |   2100 |    16437 |  2087 |    1 |     7 | 2010 |
| 186478 |   2100 |    16437 |  2801 |    1 |     5 | 2010 |
| 186479 |   2100 |    16437 |  3335 |    1 |     7 | 2010 |

186480 rows × 6 columns

此表列出了该数据集中用户对音乐艺术家的评价

需要使用到的数据介绍：

userID：用户id

artistID：音乐艺术家ID

tagID：对音乐艺术家评价的标签id

## 实现功能描述

### 检索

根据音乐艺术家名字进行检索、根据标签进行检索

### 推荐

基于用户感兴趣程度的推荐、基于用户好友的推荐、根据用户查询的具体歌手进行相似的歌手推荐

## 实现思路描述

### 检索

通过多表数据连接，直接进行查找，同时使用库函数进行模糊查询

### 推荐

由于该数据集提供了用户对音乐艺术家的兴趣度权重表，因此可通过直接查表完成兴趣度推荐；基于好友推荐同理，先查询该用户的好友，再对好友使用兴趣度推荐即可；根据用户查询的具体歌手进行相似的歌手推荐则先分别创建标签与音乐艺术家的倒排表字典，再通过”查表得到当前搜索音乐艺术家最符合的标签，再根据标签查找高度符合此标签的其他音乐艺术家“的步骤完成推荐

## 实现步骤描述

### 根据音乐艺术家名字进行检索

1. 读取artist.dat表
2. 创建一个空的list，用来储存音乐艺术家的名字
3. 遍历name列，向list中添加音乐艺术家的名字
4. 根据音乐艺术家名字进行模糊检索

### 根据标签进行检索

1. 读取tags.dat表与user_taggedartists.dat表
2. 通过键连接artists.dat、tags.dat和user_taggedartists.dat三表
3. 保留标签名，音乐艺术家名两列数据，并去重
4. 创建一个空的list，用来储存标签名
5. 遍历tagValue列，向list中添加音乐艺术家的名字
6. 根据标签名进行模糊检索

### 基于用户感兴趣程度的推荐

1. 读取user_artists.dat表
2. 通过userID分类并获取每个用户最感兴趣的5位音乐艺术家，通过键连接user_artists.dat和artists.dat两表
3. 保留用户ID，音乐艺术家名两列数据
4. 根据用户感兴趣程度进行推荐

### 基于用户好友的推荐

1. 读取user_friends.dat表
2. 查询用户好友
3. 根据用户好友感兴趣程度进行推荐

### 根据用户查询的具体歌手进行相似的歌手推荐

1. 通过词袋模型与TD-IDF模型创建标签的倒排表字典
2. 通过词袋模型与TD-IDF模型创建音乐艺术家的倒排表字典
3. 查表得到当前搜索音乐艺术家最符合的标签
4. 根据标签查找高度符合此标签的其他音乐艺术家进行推荐

## 实现技术描述

### 基于内容的推荐算法

应用场景：私人电台等个性化推荐

优点：推荐非常准确，针对用户进行个性化推荐

缺点：有用户、物品、系统冷启动问题，在数据较少的条件下十分不准确；无法推送新内容

### 基于协同的推荐算法

应用场景：基于好友、基于当地的热门歌曲推荐

优点：可以推送新内容，同时推荐的准确性较高

缺点：有用户、物品、系统冷启动问题，在数据较少的条件下十分不准确

### 基于关联规则的推荐算法

应用场景：发现潜在关系，比如喜欢Maroon 5的人都喜欢听传统R&B

优点：可以推送比协同推荐准确性更高的新内容

缺点：有用户、物品、系统冷启动问题，在数据较少的条件下十分不准确



**共同优化点**：

- 提供非个性化的推荐：
    - **提供热门排行榜**：最简单的就是给用户推荐热门排行榜，等到用户数据收集到一定的时候，再切换为个性化推荐；
    - **推荐随机的热门内容**：推荐随机的热门内容，再通过评估用户的点击来快速调整；
    - **提供具有很高覆盖率的启动物品集合**：在冷启动时，我们不知道用户的兴趣，而用户兴趣的可能性非常多，我们需要提供具有很高覆盖率的启动物品集合，这些物品能覆盖几乎所有主流的用户兴趣。

- 利用用户注册信息：
    - 人口统计学信息：年龄、性别、职业、民族、学历和居住地等；
    - 用户兴趣的描述：部分网站会让用户用文字来描述兴趣；
    - 从其他网站导入的用户站外行为：比如用户利用社交网站账号登录，就可以在获得用户授权的情况下导入用户在该社交网站的部分行为数据和社交网络数据。

- 利用内容特征的相似度：
    - 如果是要对一个新内容推荐相关的其他内容，那么可以多多利用内容特征的相似度。

## 方案实现

### 实现度：100%

### 实现语言：python

### 注释：已包含在实现代码中

### 其他：上传的数据集文件均有使用

## 总结

### 结论

这份大作业根据Last.fm数据集，完成了”二查三推荐“，根据音乐艺术家名字进行检索；根据标签进行检索；基于用户感兴趣程度的推荐；基于用户好友的推荐；根据用户查询的具体歌手进行相似的歌手推荐。可以精准地搜索到想要寻找的音乐艺术家，并根据用户过往的评价与当前搜索的音乐艺术家进行精准的推荐，但无法解决冷启动问题，以上的推荐功能的准确性很大程度上收到原始数据量的影响

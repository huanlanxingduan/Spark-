(1) 已知电影数据集movie_metadata.csv（下载地址：https://pan.baidu.com/s/1qXN8oOW ）,其包含28列，每列数据用“,”分割，每列数据名称为：  
"movie_title" "color" "num_critic_for_reviews" "movie_facebook_likes" "duration" "director_name" "direct_facebook_likes"  
"actor_3_name" "actor_3_facebook_likes" "actor_2_name" "actor_2_facebook_likes" "actor_1_name" "actor_1_facebook_likes"  
"gross" "genres" "num_voted_users" "cast_total_facebook_likes" "facenumber_in_poster" "plot_keywords" "movie_imdb_link"  
"num_user_for_reviews" "language" "country" "content_rating" "budget" "title_year" "imdb_score" "aspect_ratio"  

每一列的数据含义可通过列名自行判断。  
提示：读取数据集，并将值保存成RDD，部分代码如下，请接着以下代码编写程序：
```
//将文件读成RDD，并过滤掉第一行元信息
val rdd=sc.textFile("movie_metadata.csv").filter(!_.startsWith("color,director_name"))
//将每一行按照“，”分割
val movieRdd=rdd.map(_.split(","))
```
请根据以上提示，在spark-shell中利用RDD API编写代码片段实现以下功能：  
- 请输出该数据集包含的所有不同国家的名称（用到country一列）  
- 请输出该数据集中包含的中国电影的数目（用到country一列）  
- 请输出最受关注的三部中国电影的电影名称、导演、以及放映时间（用到movie_title、director_name、num_voted_users、country以及title_year五列）  
- 请使用spark sql的Dataframe和Dataset API实现以上功能（提示：可创建一个case class，并进一步将movieRdd创建为DataFrame）

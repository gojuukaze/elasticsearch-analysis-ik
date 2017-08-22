IK Analysis for Elasticsearch
=============================

forked from ：elasticsearch-analysis-ik（https://github.com/medcl/elasticsearch-analysis-ik）

修改了一些小地方，使其更适合自己使用
详细使用教程参照源工程，暂时只提供5.5.1版本的zip文件



Versions
--------

IK version | ES version
-----------|-----------
master | 5.x -> master
5.5.1| 5.5.1

Changes
------
*5.5.1*

- 移除加载远程字典的详细log（源工程加载远程字典会把每个加载的词都输出）

- 增加配置获取远程字典的时间间隔配置：update_remote_ext_dict_period，update_remote_stop_dict_period  
  在IKAnalyzer.cfg.xml中配置：
  ```xml
     <!--获取远程扩展字典的时间间隔，单位:s ,默认60s-->
	 <entry key="update_remote_ext_dict_period">60</entry>
     <!--获取远程扩展停止词字典的时间间隔，单位:s ,默认60s-->
	 <entry key="update_remote_stop_dict_period">60</entry>
  ```

- 在版本c4c498a里热更新词库有个bug，就算字典没修改还是会重新加载，原作者用equalsIgnoreCase()判断字符串相等，我改成了equals()后就没问题了



# 论纯函数管道数据流方法，兼评：左耳朵耗子 《什么是函数式编程？》

版权所有 © 2018 林鹏程， 保留所有权利。

左耳朵耗子 《什么是函数式编程？》写的纯函数管道方法我在QQ群、微信群里说过好多年了，在2017年1～3月的推特和微博,也发过几篇相关的短文，我的项目也应用了该方法。

Clojure语言一直都是极力推崇这写流水线写法，提供了语言级的支持，->>宏写法更漂亮。只是编程人员有下力气去这么做的人少而已, 毕竟设计一条流畅的流水线了是一件比较费时间的事。不过是一堆老概念, 耳熟能详的东西，Unix和FP都出了多少年了。

管道流水线最早的思想就是模拟工业流水线, FP最早的思想就是模拟机器组装,两者都对大工业的模仿，数学只是FP用来装点门面的, 这叫内用黄老,外示儒术，说一套，做一套，古今中外都有。

对于纯函数管道方法，以前我在QQ群、微信群里讲过一个更容易理解的借喻：把数据当成电流，函数当成各种设备或电器，数据（电流）从电厂出发，经过高压线，配电设备，电表，电线等纯函数，最终到达电器做功产生副作用，完成使命结束。

基于上例，一个纯函数管道数据流由纯函数构成，最多只有一个副作用函数，且只能在末尾，可以没有副作用。纯函数管道数据流的作用，主要是实现数据流和逻辑流分离，方便重用、组合、维护、并发、扩展。

快2018年春节了，我再发一遍2017年春节在微博发的一个clojure数据流祝福代码，中文表达是: 把各种祝福放在福袋里, 送给大家.

```clojure
(-> []

    (conj "新年快乐")

    (conj "幸福安康")

    (conj "事业发达")

    (->> (assoc {} :大家)))
```    

附文：《左耳朵耗子：什么是函数式编程？》网址

https://mp.weixin.qq.com/s?__biz=MjM5MDE0Mjc4MA==&mid=2651001208&idx=1&sn=88e9bf49f5a2bc095dde59642968dbac&chksm=bdbee92b8ac9603dcdc37278f47f1f97c25ed371c51f01041db45b3730f87da3ba8118cbddd7&mpshare=1&scene=1&srcid=02126bOIcpSrotvnqbUVJlcg#rd

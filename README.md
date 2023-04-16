# OpenDRG的目标是成为国家医保局CHS-DRG的开源实现，就像OpenJDK是Java SE的开源实现一样

## 业务背景

&emsp;&emsp;疾病诊断相关组（Diagnosis Related Groups，DRG）是用于衡量医疗服务质量效率以及进行医保支付的重要工具。国家医保局已经出台文件，要求从2022到2024年，三年内全面完成DRG/DIP付费方式改革，很多省市医保局已经采用DRG方式与医院进行结算。医院为了应对DRG支付改革，需要掌握DRG分组规则。但是各地DRG分组规则不统一，经常变化，医院很难通过自行研究去掌握。如果花高价去采购商业DRG软件，一方面软件厂商在各地规则的研究方面，水平参差不齐，很多时候不能及时满足需求；另一方面，大部分厂商的软件是封闭式的，医院不能自由的调用底层分组接口或者进行二次开发，尤其很难满足大批量数据分析方面的需求。

&emsp;&emsp;我们一批志同道合的的小伙伴，花费大量时间精力，学习DRG理论、研究国家DRG政策、跟踪各省市的DRG改革进程，并且研发了DRG分组器软件，在一些地区成功实践。为了帮助更多的医院解决DRG难题，助力国家DRG改革，我们在“开放源代码软件”运动的启发下，决定按照“开放、透明、协作、交付”的原则，向全国的医院免费提供OpenDRG分组器源代码，并欢迎所有的信息化厂商进行集成。

## OpenDRG分组器产品优势
* 严格按照医保局规则进行分组，其正确性经过多个地区、多家医院的实际验证
* 以插件方式嵌入医院业务系统运行，不需要部署服务器，不增加医院服务器负担
* 采用Java、C#、python、js等多种语言实现，方便医院HIS、EMR、病案等不同技术架构的系统来集成
* 性能非常高，5000份病案的分组，最多只要1秒钟，即满足日常业务处理，也能应用到大数据分析场景
* 采用开源方式运作，很多业内有志之士提供支持，不管是分组规则还是软件功能，都更新非常快
* 如果以上优势都不能吸引你，再看看这最后一项：**它永久免费提供，不谋求任何商业利益！！！**

## 各地方分组方案支持情况
|DRG分组方案|DRG组数|适用地区|
|-|-|-|
|CHS-DRG 1.1 标准版|628组| 陕西省铜川市；山东省临沂市；贵州省六盘水市、铜仁市|
|CHS-DRG 1.0 修订版|618组| 陕西省西安市；四川省成都市|
|CHS-DRG 1.1 盐城2023细分组|628组| 江苏省盐城市|
|CHS-DRG 1.1 苏州2023细分组|667组| 江苏省苏州市|
|CHS-DRG 1.1 泰州2022细分组|758组| 江苏省泰州市|
|CHS-DRG 1.1 无锡2022细分组|599组| 江苏省无锡市|
|CHS-DRG 1.0 修订版 武汉2022细分组|660组| 湖北省武汉市|
|CHS-DRG 1.1 北京版细分组|696组| 北京市|
|CHS-DRG 1.1 福州2022细分组|563组| 福建省福州市|
|ZJ-DRG 1.1 浙江2022细分组|1006组| 浙江省|
|CHS-DRG 1.1 乌鲁木齐2022细分组|718组| 新疆乌鲁木齐市|
|CHS-DRG 1.1 长株潭衡2023细分组|737组| 湖南省长沙市、株洲市、湘潭市、衡阳市|
|CHS-DRG 1.1 兰州2023细分组|794组| 甘肃省兰州市|
|CHS-DRG 1.1 烟台2023细分组|647组| 山东省烟台市|
|CHS-DRG 1.0 修订版 常州2022细分组|740组| 江苏省常州市|

&emsp;&emsp;江苏徐州、四川自贡、河南开封、广东佛山、广西等地区版本的分组器正在开发，将逐步发布，敬请关注

## 子项目介绍
### DRG_Rules
&emsp;&emsp;国家医保局以及浙江、北京等省医保局发布的分组方案文件，经过结构化处理后形成的知识库
### DRG_Datas
&emsp;&emsp;DRG分组相关的各类数据集，包括不同版本的ICD编码、各地医保局的分组权重及支付标准、各类医院病案数据文件等
### DRG_Java/DRG_Csharp/DRG_Python/DRG_JavaScript
&emsp;&emsp;Java、Csharp、Python、JavaScript四种不同语言开发的DRG分组器源代码，功能实现完全一致，可直接使用或集成到医院内部各种业务系统
### opendrg.github.io
&emsp;&emsp;分组器演示平台，一个简单的网页，集成了JavaScript版本的分组器，可以按不同省市的分组方案对病案进行分组，并显示分组结果、支付信息及统计指标等

## 分组器演示平台 
* 网址：[opendrg.github.io](https://opendrg.github.io/)

* 网页加载会有点慢，因为DRG规则文件较大，请耐心等待

* 该网站为静态网站，不收集任何用户数据。网页加载完后，导入的数据文件是在本地进行处理，不会通过网络发送数据

* 如果觉得网页打开慢，或者担心信息泄露，可以点击以下链接，下载网页源码，解压后再双击index.html打开页面即可使用（之后无需再访问网络）

https://github.com/OpenDRG/OpenDRG.github.io/archive/refs/heads/main.zip

## 联系开发团队
请发邮件至14463966@qq.com

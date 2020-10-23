新闻稿 @link [oracle发布Java15简介](https://www.oracle.com/news/announcement/oracle-announces-java-15-091520.html)

## 甲骨文宣布Java 15



- Java 15添加了新功能以提高开发人员的工作效率和安全性，其中包括Edwards-Curve数字签名算法（JEP 339）和隐藏类（JEP 371）
- 文本块（JEP 378）和ZGC（JEP 377）已在此发行版中完成
- 包含密封类（JEP 360）作为新的预览功能，并添加了instanceof（JEP 375）和记录（JEP 384）的模式匹配作为第二个预览，以进一步征询开发人员的意见



**加利福尼亚州红木海岸-2020年9月15日**

![Java徽标](https://www.oracle.com/oce/press/assets/CONT3F1340E86D91451E80213DA41423DB63/native/rc24-java-25yrs.gif)

Oracle今天宣布了Java 15（Oracle JDK 15）的全面上市。经过25年的创新，Java仍然是排名第一的编程语言，全球69％以上的专职开发人员使用Java。最新的Java开发套件（JDK）提供了新功能，包括Edwards-Curve数字签名算法（JEP 339）和隐藏类（JEP 371），以及现已定稿的以前的预览功能：文本块（JEP 378）和ZGC（JEP 377）。Java 15包括密封类（JEP 360）作为第一次预览功能，而模式匹配（JEP 375）和记录（JEP 384）的第二次预览提供了更多社区反馈。[立即开始使用Java 15](http://www.oracle.com/java)。

Oracle按照2018年与Java 10首次建立的为期六个月的Java发布节奏按时交付了Java15。六个月的发布计划为开发人员提供了更快的创新以及更好的可预测性和稳定性。Java遍及各种规模和所有行业的组织中。随着[51级十亿全球部署积极的JVM](https://blogs.oracle.com/java/java-in-2020)，Java是现代企业应用程序的开发，包括分析，微服务，数据管理，社会，大数据，DevOps的，移动的，不断发展的工具，以及聊天机器人的首选。

“ Java庆祝成立25周年之际，我们将继续进行技术投资，以推动Java创新向前发展，并帮助应对瞬息万变的技术格局，” Oracle Java Platform Group开发副总裁Georges Saab说。“ Java 15的可用性以及向六个月发布节奏的转变所带来的增量创新，为Java社区提供了构建现代应用程序所需的工具，这些应用程序可以推动我们的世界前进。”

在[Java的15版本](https://blogs.oracle.com/java-platform-group/the-arrival-of-java-15)是全行业的发展，涉及公开审查结果，每周建立并通过Oracle的工程师和全世界的Java开发人员社区的成员之间的广泛合作[的OpenJDK社区](http://openjdk.java.net/)和Java社区进程。Java 15中提供的新功能包括：

- 新功能：
  - JEP 339：[爱德华兹曲线数字签名算法（EdDSA）](https://openjdk.java.net/jeps/339) –此功能通过使用[RFC 8032](https://tools.ietf.org/html/rfc8032)所述的EdDSA实施加密签名来提高安全性和性能。
  - JEP 371：[隐藏类](https://openjdk.java.net/jeps/371)–此功能通过改进Java与运行时生成类并通过反射间接使用类的框架的配合使用，从而提高了生产率。
- 预览功能现已完成：
  - JEP 378：[文本块](https://openjdk.java.net/jeps/378)–此功能是JDK 13和JDK 14中的预览功能，它通过添加多行字符串文字并以可预测的方式自动格式化字符串来提高开发人员的生产率。
  - JEP 377：[ZGC](https://openjdk.java.net/jeps/377) –这种可扩展的，低延迟的垃圾收集器在JDK 11中作为实验功能引入后投入生产。
- 孵化和预览功能：
  - JEP 360：[密封类](https://openjdk.java.net/jeps/360)–此预览功能通过使用密封类和接口增强Java编程语言来提高开发人员的生产率。密封的类和接口限制可以扩展或实现它们的其他类或接口。
  - JEP 375：[用于instanceof的模式匹配](https://openjdk.java.net/jeps/375)–此预览功能是JDK 14中首次引入的，它消除了对通用样板代码的需要，从而提高了开发人员的工作效率，并且应允许使用更简洁的类型安全代码。
  - JEP 384：[记录](https://openjdk.java.net/jeps/384)–该预览功能是JDK 14中首次引入的，它通过提供用于声明包含浅层不变数据的类的紧凑语法来提高开发人员的生产率。 
  - JEP 383：[外部存储器访问API](https://openjdk.java.net/jeps/383) –此孵化功能是JDK 14中首次引入的，它定义了一个API，以允许Java程序安全有效地访问Java堆外部的外部存储器。
- 现代化现有代码：
  - JEP 373：[旧数据报套接字和MulticastSocket API的重新实现](https://openjdk.java.net/jeps/373)–此功能通过用更简单，更现代的实现替换java.net.DatagramSocket和java.net.MulticastSocket API的基础实现，提高了JDK的可维护性和稳定性。
- 清理：
  - 与以前的功能版本一样，JDK 15弃用了过时的功能（JEP 374：[偏置锁定](https://openjdk.java.net/jeps/374)，JEP 385：[RMI激活](https://openjdk.java.net/jeps/385)），并删除了以前不建议使用的功能（JEP 372：[Nashorn JavaScript Engine](https://openjdk.java.net/jeps/372)）和端口（JEP 381：[Solaris和Sparc](https://openjdk.java.net/jeps/381)）。

## 管理Java

[Java](https://www.oracle.com/java/moved-by-java/)已有[25年历史的](https://www.oracle.com/java/moved-by-java/)一个重要里程碑是JDK 10，该版本已过渡到六个月的功能发布节奏。新的可预测的发布节奏使Java生态系统的创新步伐比以前快得多。通过利用[Oracle Java SE订阅](https://www.oracle.com/java/java-se-subscription.html)来管理Java资产的组织不仅可以受益于[Oracle](https://www.oracle.com/java/java-se-subscription.html)的最新增强功能和对Java专家的直接访问，还可以在四年的时间里节省大量费用（[大型企业为31％](https://www.oracle.com/a/ocom/resources/the-next-decade-of-java-(2).pdf)，[29％与中型企业](https://www.oracle.com/a/ocom/resources/java_for_mid-size_enterprises.pdf)每六个月升级的替代方法相比）。

在[Java 25岁时](https://www.oracle.com/a/ocom/docs/corporate/analystrelations/omdia-java-turns-25.pdf)Omdia研究报告的首席分析师Bradley Shimmin指出：“由于Oracle用Java重写了大量内部软件并使Java成为Oracle数据库和Oracle云基础架构的关键组件，因此Java和Oracle的成功无可避免地交织在一起。对于数以百万计的依赖Java来驱动关键任务软件的企业而言，这同样适用。对于Oracle，这扩展到了公司向云的推动力。由于众多语言专用工具和丰富的支持服务，Oracle Cloud Infrastructure是最好的运行企业Java代码的位置。” 他接着说：“正如多行文本块和高级开关语句等功能的引入所证明的那样，Oracle优先考虑了'开发人员的经验，

## 其他资源

- 阅读[Java 15技术博客](https://blogs.oracle.com/java-platform-group/the-arrival-of-java-15)
- 了解有关[Oracle OpenJDK 15 General Availability版本的更多信息](https://jdk.java.net/15/)
- 了解有关[Oracle Java SE订阅的](https://www.oracle.com/a/tech/docs/javase-subscription-datasheet.pdf)更多信息
- 阅读[2020年Java](https://blogs.oracle.com/java/java-in-2020)博客
- 收听[Java 15](https://inside.java/podcast)播客

## 联络资料

- #### 特拉维斯·安德森（Travis Anderson）

- 甲骨文公关

- [travis.j.anderson@oracle.com](mailto:travis.j.anderson@oracle.com)

- +1.208.880.8134

## 关于甲骨文

Oracle云为销售，服务，营销，人力资源，财务，供应链和制造提供了一套完整的集成应用程序，以及具有Oracle自治数据库的高度自动化和安全的第二代基础架构。有关Oracle（NYSE：ORCL）的更多信息，请访问我们的网站[www.oracle.com。](https://www.oracle.com/)

## 商标

Oracle和Java是Oracle和/或其分支机构的注册商标。其他名称可能是其各自所有者的商标。
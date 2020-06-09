# Anatomy of URL [阅读资料](https://doepud.co.uk/blog/anatomy-of-a-url)
  * scheme + 域名 + 端口号 + 路径 + 参数 + 锚点
    * e.g. https://baidu.com:443/s?wd=hello&rsv_spt=1#5
  * scheme
    * The scheme tells web servers which protocol to use when it accesses a page on your website.
      * protocol: define了如何书写request和response：用于制定网络传输规则
  * 域名（Domain Name）
    * 用于在数据传输时标识计算机的电子方位（the readability of IP is bad, then thranslate it to Domain Name)
  * 端口号（port #）
    * in an incoming message/packet, the IP address is used to identify the destination computer/node, whereas the port number further specifies the destination application/program in that computer. Similarly, all outgoing network packets contain application port numbers in the packet header to enable the receiver to distinguish the specific application.
  * 查询参数(query)
    * represented by a question mark followed by one or more parameters. The query directly follows the domain name, path or port number.
      * e.g. http://www.google.co.uk/search?q=url&ie=utf-8&oe=utf-8&aq=t&rls=org.mozilla:en-GB:official&client=firefox-a.  
  * 锚点
    * An anchor allows users to leapfrog to a specific point on a website page. It saves them the need to scroll and skim read – and makes navigation easier
# DNS 的作用是什么
- Domain Name System translates more readily memorized domain names to the numerical IP addresses needed for locating and identifying computer services and devices with the underlying network protocols.
# nslookup命令
check the IP address of a Domain Name
```cmd
nslookup github.com
```
# IP (Internet Protocol)
- An Internet Protocol address (IP address) is a numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication.
- ping命令
  - Using the Ping command works by sending out packets and waiting for replies over the network from another computer or network device. This can be useful to test the ability of the source computer to reach a specified destination computer. It is also used as a complementary command with the traceroute command to further determine any connectivity issues.
```cmd
ping qq.com
```
# 域名(Domain Name)
- use to locate the device connected into the network
- www.baidu.com
  - com --> 一级域名
  - badu --> 二级域名
  - www --> 三级域名
- 因特网采用层次树状结构命名方法。域是名字空间中一个可被管理的划分（按机构组织划分），域可被划分为子域，子域可再被划分，即形成了顶级域名、二级域名、三级域名等。从右向左为顶级域名、二级域名、三级域名等，用点隔开。最左边的部分是单台计算机的名字（不能再进行划分了）。这里的顶级域名、二级域名、三级域名只是从右向左用点隔开的位置的称呼方式。如 abc.com.cn 其中 cn 是顶级域名、com 是二级域名、abc 是三级域名，如 abc.com 其中 com 为顶级域名，abc 为二级域名。

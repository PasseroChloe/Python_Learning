# coding=utf-8
# 接受url请求的模块
import urllib
# 正则表达式操作
import re


# 定义一个函数，用于获取html
def getHtml(url):
    # try:
    # urlopen方法用于打开一个url地址
    page = urllib.urlopen(url)
    # read方法用于读取url上的数据
    html = page.read()
    # 若有错误，返回错误原因
    # except urllib2.URLError() as e:
    # print 'Get html error:', e.reason
    # html = None
    # 返回html
    return html


# 定义一个函数，用于获取图片
def getImg(html):
    # 获取图片的正则表达式
    reg = r'src="(.+?\.jpg.+?)" alt'
    # 把正则表达式编译成一个正则表达式对象
    imgre = re.compile(reg)
    # 读取包含正则表达式的数据
    imglist = re.findall(imgre, html)
    x = 0
    # for进行遍历
    for imgurl in imglist:
        urllib.urlretrieve(imgurl, 'page%d-picture%d.jpg' %(pageno,x) )
        x += 1

for pageno in range(1,200):
# 输入想要下载的页面的页面数
#pageno = raw_input("Please enter the page number you want to download:")
# 得到相应页面的pageno
    html = getHtml("http://www.luoo.net/tag/?p=" + str(pageno))
    print getImg(html)

---
layout: post
comments: true
---

# Wordpress技巧：使用Github图床；CDN加速个性化字体

对于主机带宽和容量有限的个人网站站长，我们可以使用Github免费为自己的网站提供图床和CDN加速。鉴于Github已经是世界上最大的代码托管网站，这样的图床和CDN亦相对可靠。
<h2>Github图床：使用PicX工具</h2>
PicX是基于 GitHub API &amp; jsDelivr 开发的具有 CDN 加速功能的图床管理工具。无需下载与安装，网页端在线使用！参考picX的官方介绍文档：<a href="https://picx-docs.xpoet.cn/tutorial/get-start.html">https://picx-docs.xpoet.cn/tutorial/get-start.html</a>
<h2>Github CDN加速字体文件</h2>
Wordpress对中文字体的支持很差，如果我们想要个性化网站字体该怎么做呢？

<strong>1. 首先下载一款自己喜欢的字体，最好是ttf格式。</strong>例如本网站选择使用飞花宋体。

<img class="alignnone size-medium" src="https://raw.githubusercontent.com/iDayDayPlus/image-hosting/master/20220312/Snipaste_2022-03-12_16-08-17.us15100ycz4.webp" width="239" height="74" />

<strong>2.新建一个Github仓库，将下载好的ttf格式文件上传到新建好的仓库中。</strong>这里推荐使用Github Desktop软件上传文件。上传完成后点击仓库release发布版本，具体操作请参考：<a href="https://zhuanlan.zhihu.com/p/346643522">https://zhuanlan.zhihu.com/p/346643522</a>。该步骤完成后，你应该会有一个ttf字体文件的链接,例如：
<blockquote>https://cdn.jsdelivr.net/gh/iDayDayPlus/myCDN/FeiHuaSongTi-2.ttf</blockquote>
<strong>3.利用Firefox浏览器检查元素，拷贝有关font-family的代码段。</strong>

<img class="alignnone size-medium" src="https://raw.githubusercontent.com/iDayDayPlus/image-hosting/master/20220312/Snipaste_2022-03-12_16-14-59.6bbk19p97qs0.webp" width="646" height="344" />

<img class="alignnone size-medium" src="https://raw.githubusercontent.com/iDayDayPlus/image-hosting/master/20220312/Snipaste_2022-03-12_16-17-22.7pondtld4tw.webp" width="1362" height="479" />
<blockquote>body, button, input, select, textarea {
font-family: "ChineseFont";
font-weight: 400;
font-size: 14px;
}</blockquote>
<strong>4. 在Wordpress中配置自定义字体。</strong>

进入Wordpress后台，打开外观-自定义-额外CSS。首先定义个性字体的地址，该地址即为第二步中生成的地址。然后粘贴第三部中得到的代码块，将font-family后的字体名称改为自定义好的名称即可。

<img class="alignnone size-medium" src="https://raw.githubusercontent.com/iDayDayPlus/image-hosting/master/20220312/Snipaste_2022-03-12_16-24-46.6sr5z9gnino0.webp" width="300" height="327" />

经过以上步骤后刷新网页，应该就可以看到个性化的字体被应用到了所有文章正文中。值得一提的是，利用同样的操作，也可以对博客标题字体进行自定义。字体的大小，粗细，颜色也可以类比进行设置。

下图即为本网站重构后的结果。相比系统自带的字体，新的个性化字体让博客典雅了许多。

<img class="alignnone size-medium" src="https://raw.githubusercontent.com/iDayDayPlus/image-hosting/master/20220312/Snipaste_2022-03-12_16-30-12.6f2cqgvof7k0.webp" width="1345" height="692" />

&nbsp;

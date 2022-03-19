<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
<!-- qtcore-index.qdoc -->
  <title>Qt Core 6.2.3 | Qt6 中文参考手册</title>
  <link rel="stylesheet" type="text/css" href="http://qtdoc.cutebook.net/qtcore/style/offline-simple.css" />
  <script type="text/javascript">
    document.getElementsByTagName("link").item(0).setAttribute("href", "style/offline.css");
    // loading style sheet breaks anchors that were jumped to before
    // so force jumping to anchor again
    setTimeout(function() {
        var anchor = location.hash;
        // need to jump to different anchor first (e.g. none)
        location.hash = "#";
        setTimeout(function() {
            location.hash = anchor;
        }, 0);
    }, 0);
  </script>
</head>
<body>
<div class="header" id="qtdocheader">
    <div class="main">
    <div class="main-rounded">
        <div class="navigationbar">
        <ul>
<li><a href="http://qtdoc.cutebook.net/qtcore/../qtdoc/index.html">Qt 6.2</a></li>
<li>Qt Core</li>
<li id="buildversion">Qt 6.2.3 参考文档</li>
    </ul>
    </div>
</div>
<div class="content">
<div class="line">
<div class="content mainContent">
<div class="sidebar">
<div class="toc">
<h3 id="toc">Contents</h3>
<ul>
<li class="level1"><a href="#using-the-module">使用模块</a></li>
<li class="level2"><a href="#building-with-cmake">使用 CMake 进行构建</a></li>
<li class="level2"><a href="#building-with-qmake">使用 qmake 进行构建</a></li>
<li class="level1"><a href="#threading-and-concurrent-programming">线程和并发编程</a></li>
<li class="level1"><a href="#input-output-resources-and-containers">输入/输出、资源和容器</a></li>
<li class="level1"><a href="#additional-frameworks">其他框架</a></li>
<li class="level1"><a href="#module-evolution">模块演变</a></li>
<li class="level1"><a href="#licenses-and-attributions">许可和归属</a></li>
<li class="level1"><a href="#reference">参考</a></li>
</ul>
</div>
<div class="sidebar-content" id="sidebar-content"></div></div>
<h1 class="title">Qt Core</h1>
<!-- $$$qtcore-index.html-description -->
<div class="descr" id="details">
<p>Qt Core模块将以下功能添加到C++：</p>
<ul>
<li>一种非常强大的无缝对象通信机制，称为信号和插槽</li>
<li>可查询和可设计的对象属性</li>
<li>组织起来的分层和可查询对象树</li>
<li>使用受保护的指针，以自然的方式拥有对象所有权 (<a href="http://qtdoc.cutebook.net/qtcore/qpointer.html">QPointer</a>)</li>
<li>跨库边界工作的动态强制转换</li>
</ul>
<p>以下页面提供了有关Qt核心功能的更多信息：</p>
<ul>
<li><a href="http://qtdoc.cutebook.net/qtcore/metaobjects.html">元对象系统(The Meta-Object System)</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/properties.html">属性系统(The Property System)</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/object.html">对象模型(Object Model)</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/objecttrees.html">对象树和所有权(Object Trees &amp; Ownership)</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/signalsandslots.html">信号和插槽(Signals &amp; Slots)</a></li>
</ul>
<h2 id="using-the-module">使用模块</h2>
<p>使用Qt模块需要直接或通过其他依赖项链接到模块库。一些构建工具对此有专门的支持，包括 <a href="http://www.cmake.org/cmake/help/documentation.html">CMake</a> and <a href="http://qtdoc.cutebook.net/qtcore/resources.html#qmake">qmake</a>.</p>
<h3 id="building-with-cmake">使用 CMake 进行构建</h3>
<p>使用 <code>find_package()</code> 命令在<code>Qt6</code> 包中找到所需的模块组件：</p>
<pre class="cpp">
 find_package(Qt6 REQUIRED COMPONENTS Core)
 target_link_libraries(mytarget PRIVATE Qt6::Core)
</pre>
<p>另请参见<a href="http://qtdoc.cutebook.net/qtcore/../qtcmake/cmake-manual.html">使用 CMake 构建</a> 概述。</p>
<h3 id="building-with-qmake">使用 qmake 进行构建</h3>
<p>如果您使用<a href="http://qtdoc.cutebook.net/qtcore/resources.html#qmake">qmake</a> 来构建工程项目，则默认情况下会链接Qt6Core。</p>
<h2 id="threading-and-concurrent-programming">线程和并发编程</h2>
<p>Qt 以独立于平台的<a href="http://qtdoc.cutebook.net/qtcore/../qtdoc/thread.html">线程类</a>、线程安全发布事件的方式，以及跨线程的信号槽连接。多线程编程也是在不阻塞应用程序用户界面的情况下，执行耗时操作的范例。</p>
<p>The <a href="http://qtdoc.cutebook.net/qtcore/../qtdoc/threads.html">Qt 的线程支持</a> 页面包含有关在应用程序中实现线程的资料。其他并发类由<a href="http://qtdoc.cutebook.net/qtcore/../qtconcurrent/qtconcurrent-index.html">Qt Concurrent</a>模块提供.</p>
<h2 id="input-output-resources-and-containers">输入/输出、资源和容器</h2>
<p>Qt提供了一个用于编译应用程序文件和资源文件(assets)的资源系统，一组容器以及用于接收输入和打印输出的类。</p>
<ul>
<li><a href="http://qtdoc.cutebook.net/qtcore/containers.html">容器类</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/datastreamformat.html">可序列化的 Qt 数据类型</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/implicit-sharing.html">隐式共享(Implicit Sharing)</a></li>
</ul>
<p>此外，Qt Core还提供了一种独立于平台的机制，用于将二进制文件存储在应用程序的可执行文件中。</p>
<ul>
<li><a href="http://qtdoc.cutebook.net/qtcore/resources.html">Qt资源系统</a></li>
</ul>
<h2 id="additional-frameworks">其他框架</h2>
<p>Qt Core还提供了Qt的一些关键框架。</p>
<ul>
<li><a href="http://qtdoc.cutebook.net/qtcore/animation-overview.html">动画框架</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/json.html">Qt 的 JSON 支持</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/../qtdoc/plugins-howto.html">如何创建Qt插件</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/eventsandfilters.html">事件系统</a></li>
</ul>
<h2 id="module-evolution">模块演变</h2>
<p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-changes-qt6.html">切换到Qt Core更改页面</a>，列出了Qt系列Qt在模块API和功能方面所做的重要更改。</p>
<h2 id="licenses-and-attributions">许可和归属</h2>
<p>Qt Core在<a href="http://www.qt.io/about-us/">Qt Company</a>的商业许可下可用. 此外，它还在自由软件许可证下提供： <a href="http://www.gnu.org/licenses/lgpl-3.0.html">GNU Lesser General Public License, version 3</a>, 或 <a href="http://www.gnu.org/licenses/gpl-2.0.html">GNU General Public License, version 2</a>. 有关详细信息，请参阅<a href="http://qtdoc.cutebook.net/qtcore/../qtdoc/licensing.html">Qt Licensing</a>。</p>
<p>Windows上的可执行文件可能链接到<a href="http://qtdoc.cutebook.net/qtcore/../qtdoc/qtentrypoint.html">The QtEntryPoint Library</a>。此库在商业许可证下可用，也可在<a href="https://spdx.org/licenses/BSD-3-Clause.html">BSD 3条款&quot;新的&quot;或&quot;修订&quot;许可证下使用</a>。</p>
<p>此外，Qt 6.2.3 中的 Qt Core 可能包含以下许可协议下的第三方模块：</p>
<div class="table"><table class="annotated">
<tr class="odd topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-blake2.html">BLAKE2（参考实现），版本 54f4faa4c16ea34bcd59d16e8da46a64b259fc07</a></p></td><td class="tblDescr"><p>Creative Commons Zero v1.0 Universal 或 Apache 许可协议 2.0</p></td></tr>
<tr class="even topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-zlib.html">数据压缩库 (zlib), version 1.2&#x2e;11</a></p></td><td class="tblDescr"><p>zlib 许可证</p></td></tr>
<tr class="odd topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-easing.html">《缓和方程》(Easing Equations)作者：Robert Penner</a></p></td><td class="tblDescr"><p>BSD 3-clause &quot;New&quot; or &quot;Revised&quot; License</p></td></tr>
<tr class="even topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-doubleconversion.html">IEEE Doubles 的高效二进制-十进制和十进制-二进制转换例程, version 3.1&#x2e;5-30-gbf46072</a></p></td><td class="tblDescr"><p>BSD 3-clause &quot;New&quot; or &quot;Revised&quot; License</p></td></tr>
<tr class="odd topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-freebsd.html">FreeBSD strtoll and strtoull, version 18b29f3fb8abee5d57ed8f4a44f806bec7e0eeff</a></p></td><td class="tblDescr"><p>BSD 3-clause &quot;New&quot; or &quot;Revised&quot; License</p></td></tr>
<tr class="even topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-kwin.html">KWin, version 5.13.4</a></p></td><td class="tblDescr"><p>BSD-3-Clause</p></td></tr>
<tr class="odd topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-kwin.html">KWin, version 5.13.4</a></p></td><td class="tblDescr"><p>BSD-3-Clause</p></td></tr>
<tr class="even topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-md4.html">MD4</a></p></td><td class="tblDescr"><p>Public Domain</p></td></tr>
<tr class="odd topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-md5.html">MD5</a></p></td><td class="tblDescr"><p>Public Domain</p></td></tr>
<tr class="even topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-pcre2-sljit.html">PCRE2 - 无堆栈实时编译器(Stack-less Just-In-Time Compile), version 10.39</a></p></td><td class="tblDescr"><p>BSD 2-clause &quot;Simplified&quot; License</p></td></tr>
<tr class="odd topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-pcre2.html">PCRE2, version 10.39</a></p></td><td class="tblDescr"><p>BSD 3-clause &quot;New&quot; or &quot;Revised&quot; License</p></td></tr>
<tr class="even topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-qeventdispatcher-cf.html">QEventDispatcher on macOS</a></p></td><td class="tblDescr"><p>BSD 3-clause &quot;New&quot; or &quot;Revised&quot; License</p></td></tr>
<tr class="odd topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-sha1.html">安全哈希算法 SHA-1</a></p></td><td class="tblDescr"><p>Public Domain</p></td></tr>
<tr class="even topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-sha3-keccak.html">安全哈希算法 SHA-3 - Keccak, version 3.2</a></p></td><td class="tblDescr"><p>Creative Commons Zero v1.0 Universal</p></td></tr>
<tr class="odd topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-sha3-endian.html">安全哈希算法 SHA-3 - brg_endian, version https://github.com/BrianGladman/sha/ commit 4b9e13ead2c5b5e41ca27c65de4dd69ae0bac228</a></p></td><td class="tblDescr"><p>BSD 2-clause &quot;Simplified&quot; License</p></td></tr>
<tr class="even topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-rfc6234.html">安全哈希算法 SHA-384 and SHA-512</a></p></td><td class="tblDescr"><p>BSD 3-clause &quot;New&quot; or &quot;Revised&quot; License</p></td></tr>
<tr class="odd topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-siphash.html">SipHash 算法</a></p></td><td class="tblDescr"><p>Creative Commons Zero v1.0 Universal</p></td></tr>
<tr class="even topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-psl.html">公共后缀列表, version d4e247a71d1b6da08dad906b098c818493166fcc, 获取于2021-06-11</a></p></td><td class="tblDescr"><p>Mozilla 公共许可证 2.0</p></td></tr>
<tr class="odd topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-tinycbor.html">TinyCBOR, version 0.6+patches</a></p></td><td class="tblDescr"><p>MIT License</p></td></tr>
<tr class="even topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-unicode-character-database.html">Unicode 字符数据库(UCD), version 26</a></p></td><td class="tblDescr"><p>Unicode 许可协议 - 数据文件和软件 （2016）</p></td></tr>
<tr class="odd topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-unicode-cldr.html">Unicode 通用区域数据存储库 (CLDR), version v40</a></p></td><td class="tblDescr"><p>Unicode 许可协议 - 数据文件和软件 （2016）</p></td></tr>
<tr class="even topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-extra-cmake-modules.html">extra-cmake-modules, version 5.84.0</a></p></td><td class="tblDescr"><p>BSD-3-Clause</p></td></tr>
<tr class="odd topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-extra-cmake-modules.html">extra-cmake-modules, version 5.84.0</a></p></td><td class="tblDescr"><p>BSD-3-Clause</p></td></tr>
<tr class="even topAlign"><td class="tblName"><p><a href="http://qtdoc.cutebook.net/qtcore/qtcore-attribution-forkfd.html">forkfd</a></p></td><td class="tblDescr"><p>MIT License</p></td></tr>
</table></div>
<h2 id="reference">参考</h2>
<p>这些是指向 API 参考资料的链接。</p>
<ul>
<li><a href="http://qtdoc.cutebook.net/qtcore/qtcore-module.html">QT Core的C++类</a><ul>
<li><a href="http://qtdoc.cutebook.net/qtcore/animation.html">动画类</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/../qtdoc/thread.html">线程类</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/containers.html">容器类</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/plugins.html">插件类</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/shared.html">隐式共享类</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/io.html">输入/输出类</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/events.html">事件类</a></li>
</ul>
</li>
<li>CMake API<ul>
<li><a href="http://qtdoc.cutebook.net/qtcore/cmake-commands-qtcore.html">CMake 命令</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/cmake-variables-qtcore.html">CMake 变量</a></li>
<li><a href="http://qtdoc.cutebook.net/qtcore/cmake-target-properties-qtcore.html">CMake Target 属性</a></li>
</ul>
</li>
</ul>
</div>
<!-- @@@qtcore-index.html -->
        </div>
       </div>
   </div>
   </div>
</div>
<div class="footer">
   <p>
   <acronym title="Copyright">&copy;</acronym> 2022 Qt Company Ltd. 此处包含的文档贡献是其各自所有者的版权。
   <br/>    此处提供的文档是根据自由软件基金会发布的<a href="http://www.gnu.org/licenses/fdl.html"> GNU 自由文档许可证 1.3 版</a> 的条款授予许可的。<br/>    Qt 和相应的商标是Qt Company Ltd.在芬兰和/或全球其他国家/地区的商标。所有其他商标均为其各自所有者的财产。</p>
</div>
</body>
</html>

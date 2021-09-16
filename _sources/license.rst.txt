.. _license:

License
==================
.. contents::
    :local:

.. image:: _static/images/License1.png
    :target: https://www.runoob.com/w3cnote/open-source-license.html

.. _license_gpl:

GPL
-----------

GPL软件的使用者有权力得到软件的代码，只要使用了GPL，在发布(redistribution)时，整个项目也必须是GPL的，即主程序和静态链接的库（linux的.a和Windows的.lib）必须是GPL的，动态链接库(Linux的.so，Windows的.dll)必须是GPL兼容的。所谓GPL兼容，也就是GPL软件中可以使用的库，这些许可证必须比GPL弱(如LGPL，BSD)，而不能是某个商业许可证。正因如此，GPL是带有很强的传染性，只要你的软件使用了GPL的代码，那么就请以GPL开放源代码吧，并且你的项目中也不能有任何和GPL不兼容的库。

.. _license_lgpl:

LGPL
-----------

:ref:`license_gpl` 带有很强的传染性，那么如果一个库使用GPL发布，那么使用这个库的所有软件也必须使用GPL发布，这对不想开放源代码的商业软件来讲是致命的打击——你可以不使用其他的库，但最基本的libc是无论如何绕不开的，如果libc是以GPL发布，就相当于所有软件必须以GPL发布了。所以，LGPL(Lesser GPL)诞生了。

LGPL定义为，在以LGPL发布的库的基础上开发新的库的时候，新的库必须以LGPL发布，但是如果仅仅是动态链接，那么则不受任何限制。这样商业软件就可以随意的使用LGPL的库了。因此，LGPL也具有传染性，但限制在其基础上开发的库上，而并不限制使用它的程序本身——它的传染性远小于GPL。

LGPL是GPL的一个为主要为类库使用设计的开源协议。和GPL要求任何使用/修改/衍生之GPL类库的的软件必须采用GPL协议不同。LGPL允许商业软件通过类库引用(link)方式使用LGPL类库而不需要开源商业软件的代码。这使得采用LGPL协议的开源代码可以被商业软件作为类库引用并发布和销售。

但是如果修改LGPL协议的代码或者衍生，则所有修改的代码，涉及修改部分的额外代码和衍生的代码都必须采用LGPL协议。因此LGPL协议的开源代码很适合作为第三方类库被商业软件引用，但不适合希望以LGPL协议代码为基础，通过修改和衍生的方式做二次开发的商业软件采用。

GPL/LGPL都保障原作者的知识产权，避免有人利用开源代码复制并开发类似的产品。


.. _license_apache:

Apache 2.0
-----------

相对:ref:`license_lgpl` 的开放源代码，BSD，Apache 2.0就宽松许多——商业软件可以任意的使用BSD，Apache 2.0发布的软件代码，而不需要开放源代码，只需要提及代码的原出处就可以了。BSD和Apache 2.0提及的方式稍有不同，具体可以参考协议的详细内容。它们是GPL兼容的


.. _license_mit:

MIT
-----------

MIT是和BSD一样宽范的许可协议,源自麻省理工学院（Massachusetts Institute of Technology, MIT），又称X11协议。作者只想保留版权,而无任何其他了限制。MIT与BSD类似，但是比BSD协议更加宽松，是目前最少限制的协议。这个协议唯一的条件就是在修改后的代码或者发行包包含原作者的许可信息。适用商业软件。使用MIT的软件项目有：jquery、Node.js。

MIT与BSD类似，但是比BSD协议更加宽松，是目前最少限制的协议。这个协议唯一的条件就是在修改后的代码或者发行包包含原作者的许可信息。适用商业软件。使用MIT的软件项目有：jquery、Node.js。

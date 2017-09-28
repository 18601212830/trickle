# 限制进程的网速
    trickle -s -d 100 wget http://domain/path/to/file.suffix -O /dev/null    
    -s 表示独立运行，因为 trickle 还有一个 trickled 管理端可以用；
    -d 表示下载方向；
    -u 表示上传方向，两个的单位都是KB/s。

# REF
    http://www.topjishu.com/2010.html
    
# 解决overload object找不到问题
    config.h:#define LIBDIR "/usr/local/lib/trickle"
    修改为/usr/lib
    
    trickle.c: LIBNAME 修改为想要的内容
    生成的 trickle-overload.so 修改为想要的内容

trickle
=======

  by Marius Aamodt Eriksen <marius@monkey.org>

   http://monkey.org/~marius/trickle

[![Build Status](https://travis-ci.org/mariusae/trickle.svg)](https://travis-ci.org/mariusae/trickle)

Description
-----------

   trickle is a voluntary, cooperative bandwidth shaper.  trickle works
   entirely in userland and is cross platform compatible.

Install
-------

    autoreconf -if
    ./configure
    make
    su
    make install

   Note that on certain systems you may get the following error on `make`:

    configure.in:220: error: do not use LIBOBJS directly, use AC_LIBOBJ (see 
    section `AC_LIBOBJ vs LIBOBJS'
          If this token and others are legitimate, please use m4_pattern_allow.
          See the Autoconf documentation.
    make: *** [configure] Error 1

   this is easily circumvented by running make again.

   To make a RedHat RPM, simply type

    rpmbuild -ta trickle-1.07.tar.gz

Documentation
-------------

   See the manpage trickle(1), trickled(8) and trickled.conf(5).

Thanks
------

*   Jolan Luff <jolan@cryptonomicon.org>  
       for testing and access to esoteric platforms.

*   Tony Kurc  
       for the awesome logo.

*   Dag Wieers <dag@wieers.com>  
       for the RedHat SPEC. 

*   Niels Provos <provos@citi.umich.edu>,

*   Gareth Watts <gareth@omnipotent.net>,

*   Jolan Luff <jolan@cryptonomicon.org>,

*   Todd Vierling <tv@duh.org> and

*   MESH (http://mesh.eecs.umich.edu/)  
       for useful discussions and suggestions.

License
-------

   trickle is distributed under a BSD like license.  Feel free to use,
   modify and distribute in any form.  See the LICENSE file for more
   information.

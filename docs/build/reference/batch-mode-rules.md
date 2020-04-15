---
title: Toplu İş Modu Kuralları
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
ms.openlocfilehash: 38402e7b8a937cebb823ce13fa1ac01fc1099878
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328406"
---
# <a name="batch-mode-rules"></a>Toplu İş Modu Kuralları

```
{frompath}.fromext{topath}.toext::
   commands
```

Toplu iş modu çıkarım kuralları, N komutları bu çıkarım kuralından geçtiğinde çıkarım kuralının yalnızca bir çağrılması sağlar. Toplu iş modu çıkarım kuralları olmadan, N komutlarının çağrılmasını gerektirir. N, çıkarım kuralını tetikleyen bağımlı ların sayısıdır.

Toplu iş modu çıkarım kuralları içeren makefiles NMAKE sürüm 1.62 veya daha yüksek kullanmalıdır. NMAKE sürümünü kontrol etmek için, NMAKE sürüm 1.62 veya daha yüksek _NMAKE_VER makroçalıştırın. Bu makro, Visual C++ ürün sürümünü temsil eden bir dize döndürür.

Standart çıkarım kuralından tek sözdizim farkı, toplu iş modu çıkarım kuralının çift iki nokta üst üste (::)) ile sonlandırılmasıdır.

> [!NOTE]
> Çağrılan araç birden çok dosyayı işleyebilir. Toplu iş modu çıkarım kuralı `$<` bağımlı dosyalara erişmek için makro olarak kullanılmalıdır.

Toplu iş modu çıkarım kuralları yapı işlemini hızlandırabilir. Derleyici sürücüsü yalnızca bir kez çağrılır, çünkü toplu olarak derleyiciye dosya sağlamak daha hızlıdır. Örneğin, C ve C++ derleyicisi, işlem sırasında bellek tespüleden biri olarak kalabildiği için bir dosya kümesini işlerken daha iyi performans gösterir.

Aşağıdaki örnek, toplu iş modu çıkarım kurallarının nasıl kullanılacağını gösterir:

```
#
# sample makefile to illustrate batch-mode inference rules
#
O = .
S = .
Objs = $O/foo1.obj $O/foo2.obj $O/foo2.obj $O/foo3.obj $O/foo4.obj
CFLAGS = -nologo

all : $(Objs)

!ifdef NOBatch
{$S}.cpp{$O}.obj:
!else
{$S}.cpp{$O}.obj::
!endif
   $(CC) $(CFLAGS) -Fd$O\ -c $<

$(Objs) :

#end of makefile
```

NMAKE, toplu iş modu çıkarım kuralları olmadan aşağıdaki çıktıyı üretir:

```
E:\tmp> nmake -f test.mak -a NOBatch=1

Microsoft (R) Program Maintenance Utility   Version 7.00.0000
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.
        cl -nologo -Fd.\ -c .\foo1.cpp
foo1.cpp
        cl -nologo -Fd.\ -c .\foo2.cpp
foo2.cpp
        cl -nologo -Fd.\ -c .\foo3.cpp
foo3.cpp
        cl -nologo -Fd.\ -c .\foo4.cpp
foo4.cpp
```

NMAKE, toplu iş modu çıkarım kurallarıyla aşağıdaki sonucu üretir:

```
E:\tmp> nmake -f test.mak -a

Microsoft (R) Program Maintenance Utility   Version 7.00.0000
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.

        cl -nologo -Fd.\ -c .\foo1.cpp .\foo2.cpp .\foo3.cpp .\foo4.cpp
foo1.cpp
foo2.cpp
foo3.cpp
foo4.cpp
Generating Code...
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıkarsama Kuralları](inference-rules.md)

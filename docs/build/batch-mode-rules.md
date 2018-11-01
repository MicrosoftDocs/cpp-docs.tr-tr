---
title: Toplu İş Modu Kuralları
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
ms.openlocfilehash: 46387fc13c28d95d7b19fb18774daa6fc3064970
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429776"
---
# <a name="batch-mode-rules"></a>Toplu İş Modu Kuralları

```
{frompath}.fromext{topath}.toext::
   commands
```

N komutları bu çıkarım kuralı olduğunuzda toplu iş modu çıkarım kuralları çıkarım kuralı yalnızca bir çağrı sağlar. Toplu iş modu çıkarım kuralları çağrılacak N komutları olması gerekir. N tetikleyen çıkarım kuralı bağımlılara sayısıdır.

Toplu iş modu çıkarım kuralları içeren derleme görevleri dosyalarını NMAKE 1.62 veya üzeri bir sürümü kullanmanız gerekir. NMAKE sürümü denetlemek için 1.62 ya da daha yüksek kullanılabilir _NMAKE_VER makrosu NMAKE sürümü ile çalıştırın. Bu makro, Visual C++ ürün sürümü temsil eden bir dize döndürür.

Standart çıkarım kuralı yalnızca söz dizimi fark, toplu iş modu çıkarım kuralı çift iki nokta (:) ile sonlandırılır ' dir.

> [!NOTE]
>  Çağrılan aracın birden çok dosya işleyebilir olması gerekir. Toplu iş modu çıkarım kuralı kullanmalısınız `$<` bağımlı dosyalara erişmek için makrosu.

Toplu iş modu çıkarım kuralları derleme sürecinize hız kazandırabilir. Derleyici sürücüsü yalnızca bir kez çağrıldığından dosyaları, toplu derleyici tedarik hızlıdır. Örneğin, C ve C++ Derleyici daha iyi bellek sürecinde yerleşik kalabileceği çünkü dosya kümesini işlerken gerçekleştirir.

Aşağıdaki örnek, toplu iş modu çıkarım kuralları kullanma işlemini gösterir:

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

NMAKE toplu iş modu çıkarım kuralları olmadan aşağıdaki çıktıyı üretir:

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

NMAKE toplu iş modu çıkarım kuralları ile aşağıdaki sonucu verir:

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

## <a name="see-also"></a>Ayrıca Bkz.

[Çıkarım Kuralları](../build/inference-rules.md)
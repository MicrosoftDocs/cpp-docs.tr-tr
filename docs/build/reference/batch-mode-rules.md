---
description: 'Hakkında daha fazla bilgi edinin: Batch-Mode kuralları'
title: Toplu İş Modu Kuralları
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
ms.openlocfilehash: 73439082b4e2ad8e33b104329d861ddd1919ec63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182742"
---
# <a name="batch-mode-rules"></a>Toplu İş Modu Kuralları

```
{frompath}.fromext{topath}.toext::
   commands
```

Batch modu çıkarımı kuralları, N komutları bu çıkarım kuralına geldiğinde, çıkarım kuralının yalnızca bir çağrılmasını sağlar. Toplu işlem modu çıkarımı kuralları olmadan, N komutlarının çağrılması gerekir. N, çıkarım kuralını tetikleyen bağımlıların sayısıdır.

Batch modu çıkarımı kuralları içeren makefiles, NMAKE sürüm 1,62 veya üstünü kullanmalıdır. NMAKE sürümünü denetlemek için NMAKE sürüm 1,62 veya üzeri ile birlikte _NMAKE_VER makrosunu çalıştırın. Bu makro, Visual C++ ürün sürümünü temsil eden bir dize döndürür.

Standart çıkarım kuralından oluşan sözdizimsel fark, Batch modu çıkarımı kuralının çift iki nokta (::) ile sonlandırılacağı bir değer.

> [!NOTE]
> Çağrılan aracın birden çok dosyayı işleyebilmesi gerekir. Toplu işlem modundaki çıkarım kuralı, `$<` bağımlı dosyalara erişmek için makro olarak kullanılmalıdır.

Toplu işlem modu çıkarımı kuralları yapı sürecini hızlandırabilir. Derleyici sürücüsü yalnızca bir kez çağrıldığı için Batch 'de derleyiciye dosya sağlamak daha hızlıdır. Örneğin, C ve C++ derleyicisi işlem sırasında bellekte yer kalabileceğinden bir dosya kümesini işlerken daha iyi çalışır.

Aşağıdaki örnek, Batch modu çıkarımı kurallarının nasıl kullanılacağını gösterir:

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

NMAKE, Batch modu çıkarımı kuralları olmadan aşağıdaki çıktıyı üretir:

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

NMAKE, Batch modu çıkarımı kuralları ile aşağıdaki sonucu üretir:

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

[Çıkarım kuralları](inference-rules.md)

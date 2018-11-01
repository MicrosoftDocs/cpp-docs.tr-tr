---
title: Örnek Derleme Görevleri Dosyası
ms.date: 11/04/2016
ms.assetid: 8343ce71-5556-4ae0-8d1e-7efd82673070
ms.openlocfilehash: 248924ff83befdefe1045da197be5328095c0caf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534895"
---
# <a name="sample-makefile"></a>Örnek Derleme Görevleri Dosyası

Bu konu, bir örnek derleme görevleri dosyası içerir.

## <a name="sample"></a>Örnek

### <a name="code"></a>Kod

```
# Sample makefile

!include <win32.mak>

all: simple.exe challeng.exe

.c.obj:
  $(cc) $(cdebug) $(cflags) $(cvars) $*.c

simple.exe: simple.obj
  $(link) $(ldebug) $(conflags) -out:simple.exe simple.obj $(conlibs) lsapi32.lib

challeng.exe: challeng.obj md4c.obj
  $(link) $(ldebug) $(conflags) -out:challeng.exe $** $(conlibs) lsapi32.lib
```

## <a name="see-also"></a>Ayrıca Bkz.

[Derleme Görevleri Dosyası İçeriği](../build/contents-of-a-makefile.md)
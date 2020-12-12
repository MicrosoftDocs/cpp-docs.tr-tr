---
description: 'Daha fazla bilgi için: Örnek makefile'
title: Örnek Derleme Görevleri Dosyası
ms.date: 11/04/2016
ms.assetid: 8343ce71-5556-4ae0-8d1e-7efd82673070
ms.openlocfilehash: 95b7eef18ca2b517d1b3de9ca450b1bbd03116d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224913"
---
# <a name="sample-makefile"></a>Örnek Derleme Görevleri Dosyası

Bu konu, örnek makefile içerir.

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

## <a name="see-also"></a>Ayrıca bkz.

[Derleme görevleri dosyası içeriği](contents-of-a-makefile.md)

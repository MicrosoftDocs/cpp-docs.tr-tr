---
title: Derleme Görevleri Dosyası Açıklamaları
ms.date: 11/04/2016
helpviewer_keywords:
- makefiles, comments
ms.assetid: 76fd9e3d-5966-47f4-a091-c9e80b232b49
ms.openlocfilehash: c66819210d2112f9a68243ed4d3b34f491caae9d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824040"
---
# <a name="comments-in-a-makefile"></a>Derleme Görevleri Dosyası Açıklamaları

Önünde bir açıklama sayı işaretiyle (#). NMAKE sayı işareti metne sonraki yeni satır karakterini yoksayar. Örnekler:

```
# Comment on line by itself
OPTIONS = /MAP  # Comment on macro definition line

all.exe : one.obj two.obj  # Comment on dependency line
    link one.obj two.obj
# Comment in commands block
#   copy *.obj \objects  # Command turned into comment
    copy one.exe \release

.obj.exe:  # Comment on inference rule line
    link $<

my.exe : my.obj ; link my.obj  # Err: cannot comment this
# Error: # must be the first character
.obj.exe: ; link $<  # Error: cannot comment this
```

Şapka işareti ile önünde bir değişmez değer sayı işareti belirtmek için (**^**) aşağıdaki gibi:

```
DEF = ^#define  #Macro for a C preprocessing directive
```

## <a name="see-also"></a>Ayrıca bkz.

[Derleme Görevleri Dosyası İçeriği](contents-of-a-makefile.md)

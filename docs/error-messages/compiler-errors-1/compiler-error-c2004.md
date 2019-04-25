---
title: Derleyici Hatası C2004
ms.date: 11/04/2016
f1_keywords:
- C2004
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
ms.openlocfilehash: fb100d977188cd3a7d5b0ebbb3e29b53942871dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208951"
---
# <a name="compiler-error-c2004"></a>Derleyici Hatası C2004

'defined(id)' bekleniyor

Bir tanımlayıcının önişlemci anahtar sözcüğünü izleyen parantez içinde görünmesi gerekir.

Bu hata için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucu olarak da oluşturulabilir: önişlemci yönergesi parantezin eksik olması. Bir ön işlemci yönergesinden kaynaklandığından eksik kapatma parantezi ise, derleyici bir hata oluşturur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2004 oluşturur:

```
// C2004.cpp
// compile with: /DDEBUG
#include <stdio.h>

int main()
{
    #if defined(DEBUG   // C2004
        printf_s("DEBUG defined\n");
    #endif
}
```

## <a name="example"></a>Örnek

Olası çözüm:

```
// C2004b.cpp
// compile with: /DDEBUG
#include <stdio.h>

int main()
{
    #if defined(DEBUG)
        printf_s("DEBUG defined\n");
    #endif
}
```
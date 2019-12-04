---
title: Derleyici hatası C2004
ms.date: 11/04/2016
f1_keywords:
- C2004
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
ms.openlocfilehash: b781e9f81342f35d66eca222bd338252b739096c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737497"
---
# <a name="compiler-error-c2004"></a>Derleyici hatası C2004

' defined (id) ' bekleniyor

Bir tanımlayıcı, Önişlemci anahtar sözcüğünden sonraki parantez içinde görünmelidir.

Bu hata, Visual Studio .NET 2003 için yapılan derleyici uygunluk işinin sonucu olarak da oluşturulabilir: Önişlemci yönergesinde eksik parantez. Bir Önişlemci yönergesinde kapatma parantezi eksikse, derleyici bir hata oluşturur.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2004 oluşturur:

```cpp
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

```cpp
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

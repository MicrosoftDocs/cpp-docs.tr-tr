---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2004'
title: Derleyici hatası C2004
ms.date: 11/04/2016
f1_keywords:
- C2004
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
ms.openlocfilehash: f418d2c2c372b228cc50b82237d8ebc56321e2c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340391"
---
# <a name="compiler-error-c2004"></a>Derleyici hatası C2004

' defined (id) ' bekleniyor

Bir tanımlayıcı, Önişlemci anahtar sözcüğünden sonraki parantez içinde görünmelidir.

Bu hata, Visual Studio .NET 2003 için yapılan derleyici uygunluk işinin sonucu olarak da oluşturulabilir: Önişlemci yönergesinde eksik parantez. Bir Önişlemci yönergesinde kapatma parantezi eksikse, derleyici bir hata oluşturur.

## <a name="examples"></a>Örnekler

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

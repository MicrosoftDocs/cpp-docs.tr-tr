---
title: Derleyici Hatası C2004 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2004
dev_langs:
- C++
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b560ef96c4fadcb7c5ce57ece13647032ca9e902
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118758"
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
---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4286'
title: Derleyici Uyarısı (düzey 1) C4286
ms.date: 11/04/2016
f1_keywords:
- C4286
helpviewer_keywords:
- C4286
ms.assetid: 93eadd6c-6f36-413b-ba91-c9aa2314685a
ms.openlocfilehash: 52a17f66c20efc52f3d12da3a9cfbd041e5f262d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311779"
---
# <a name="compiler-warning-level-1-c4286"></a>Derleyici Uyarısı (düzey 1) C4286

' type1 ': satır numarasında taban sınıf (' type2 ') tarafından yakalandı

Belirtilen özel durum türü, önceki bir işleyici tarafından işlenir. İkinci catch türü, ilki türünden türetilir. Bir temel sınıf için özel durumlar türetilmiş bir sınıf için catch özel durumları.

## <a name="example"></a>Örnek

```cpp
//C4286.cpp
// compile with: /W1
#include <eh.h>
class C {};
class D : public  C {};
int main()
{
    try
    {
        throw "ooops!";
    }
    catch( C ) {}
    catch( D ) {}  // warning C4286, D is derived from C
}
```

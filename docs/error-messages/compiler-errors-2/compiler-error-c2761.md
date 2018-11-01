---
title: Derleyici Hatası C2761
ms.date: 11/04/2016
f1_keywords:
- C2761
helpviewer_keywords:
- C2761
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
ms.openlocfilehash: 6ad42beea28bd2070d1c7dc12086146e6ab70ff5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667018"
---
# <a name="compiler-error-c2761"></a>Derleyici Hatası C2761

'function': üye işlev yeniden bildirimi izin verilmiyor

Üye işlevini yeniden bildirilemiyor. Tanımlayabilirsiniz, ancak yeniden bildirmek değil.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2761 oluşturur.

```
// C2761.cpp
class a {
   int t;
   void test();
};

void a::a;     // C2761
void a::test;  // C2761

```

## <a name="example"></a>Örnek

Statik olmayan üye bir sınıfın veya yapının tanımlanamaz.  Aşağıdaki örnek, C2761 oluşturur.

```
// C2761_b.cpp
// compile with: /c
struct C {
   int s;
   static int t;
};

int C::s;   // C2761
int C::t;   // OK
```
---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4281'
title: Derleyici Uyarısı (düzey 3) C4281
ms.date: 11/04/2016
f1_keywords:
- C4281
helpviewer_keywords:
- C4281
ms.assetid: a9771261-5725-4fc6-87b6-16cf92113a25
ms.openlocfilehash: ad62244fb851e9aed93cb2c3f48282b77f0cf411
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344126"
---
# <a name="compiler-warning-level-3-c4281"></a>Derleyici Uyarısı (düzey 3) C4281

' operator-> ' özyineleme ' Type ' türü aracılığıyla gerçekleşti

Kodunuz, **operator->** 'ın kendisini çağırmasını sağlar.

Aşağıdaki örnek C4281 oluşturur:

```cpp
// C4281.cpp
// compile with: /W3 /WX
struct A;
struct B;
struct C;

struct A
{
   int z;
   B& operator->();
};

struct B
{
   C& operator->();
};

struct C
{
   A& operator->();
};

void f(A p)
{
   int i = p->z; // C4281
}
```

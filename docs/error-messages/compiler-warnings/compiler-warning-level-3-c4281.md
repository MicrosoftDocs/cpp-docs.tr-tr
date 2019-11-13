---
title: Derleyici Uyarısı (düzey 3) C4281
ms.date: 11/04/2016
f1_keywords:
- C4281
helpviewer_keywords:
- C4281
ms.assetid: a9771261-5725-4fc6-87b6-16cf92113a25
ms.openlocfilehash: 454118aa9b9cb1fdea5fb10576ac8d26833cb08c
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051689"
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
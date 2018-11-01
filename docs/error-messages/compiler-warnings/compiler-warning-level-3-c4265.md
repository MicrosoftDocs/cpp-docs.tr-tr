---
title: Derleyici Uyarısı (Düzey 3) C4265
ms.date: 11/04/2016
f1_keywords:
- C4265
helpviewer_keywords:
- C4265
ms.assetid: 20547159-6f30-4cc4-83aa-927884c8bb4c
ms.openlocfilehash: f06e70f88bc0a34e2feecba19da8dd9edc630230
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558359"
---
# <a name="compiler-warning-level-3-c4265"></a>Derleyici Uyarısı (Düzey 3) C4265

'class': sınıfın sanal işlevleri var ancak yok edici sanal değil

Bir sınıf sanal işlevler ancak sanal olmayan bir yok Edicisi varsa, sınıf bir temel sınıf işaretçisi kaldırıldığında türünden nesnelerin düzgün şekilde yok değil.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

Aşağıdaki örnek, C4265 oluşturur:

```
// C4265.cpp
// compile with: /W3 /c
#pragma warning(default : 4265)
class B
{
public:
   virtual void vmf();

   ~B();
   // try the following line instead
   // virtual ~B();
};   // C4265

int main()
{
   B b;
}
```
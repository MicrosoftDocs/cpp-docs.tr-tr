---
title: Derleyici hatası C3254
ms.date: 11/04/2016
f1_keywords:
- C3254
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
ms.openlocfilehash: 6b9ff41fb4f45d9570869ca90e3c6091cc03a58a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754257"
---
# <a name="compiler-error-c3254"></a>Derleyici hatası C3254

' Explicit override ': sınıf açık geçersiz kılma ' override ' içeriyor, ancak işlev bildirimini içeren bir arabirimden türetilmiyor

Açıkça bir yöntemi [geçersiz kıldığınızda](../../cpp/explicit-overrides-cpp.md) , geçersiz kılmayı içeren sınıfın, geçersiz kıldığınız işlevi içeren türden doğrudan veya dolaylı olarak türetilmesi gerekir.

Aşağıdaki örnek C3254 oluşturur:

```cpp
// C3254.cpp
__interface I
{
   void f();
};

__interface I1 : I
{
};

struct A /* : I1 */
{
   void I1::f()
   {   // C3254, uncomment : I1 to resolve this C3254
   }
};

int main()
{
}
```

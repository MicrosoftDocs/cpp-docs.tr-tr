---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3254'
title: Derleyici hatası C3254
ms.date: 11/04/2016
f1_keywords:
- C3254
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
ms.openlocfilehash: 7d0084f52060803cd99b973c9f6105fc8915c2aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194221"
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

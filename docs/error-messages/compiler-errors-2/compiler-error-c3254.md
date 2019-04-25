---
title: Derleyici Hatası C3254
ms.date: 11/04/2016
f1_keywords:
- C3254
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
ms.openlocfilehash: 7e051c6c44d3b85f6f3faaf5380ecf54cba5d73c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173515"
---
# <a name="compiler-error-c3254"></a>Derleyici Hatası C3254

'açık geçersiz kılma': sınıf açık geçersiz kılma 'override' içeriyor, ancak işlev bildirimini içeren bir arabirimden türetilmiyor

Olduğunda, [açıkça geçersiz kılma](../../cpp/explicit-overrides-cpp.md) geçersiz kıldıkları içeren işlev türü, bir yöntemi geçersiz kılma içeren sınıf, doğrudan veya dolaylı olarak türetilmesi gerekir.

Aşağıdaki örnek, C3254 oluşturur:

```
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
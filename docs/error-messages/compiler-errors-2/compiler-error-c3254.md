---
title: Derleyici Hatası C3254 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3254
dev_langs:
- C++
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9e42071c55ef3c7a4fc950b1b25656cf68d4024
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081188"
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
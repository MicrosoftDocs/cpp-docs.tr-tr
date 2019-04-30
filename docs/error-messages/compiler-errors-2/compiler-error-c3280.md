---
title: Derleyici Hatası C3280
ms.date: 11/04/2016
f1_keywords:
- C3280
helpviewer_keywords:
- C3280
ms.assetid: 86dc5bbc-8818-4786-a728-9334268d308b
ms.openlocfilehash: b43ea73a626ba35f58054a94046915d4eba97181
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382053"
---
# <a name="compiler-error-c3280"></a>Derleyici Hatası C3280

'class': bir yönetilen türün üye işlevi yönetilmeyen bir işlev olarak derlenemez

Sınıf üyesi işlevleri, yönetilmeyen bir işlev derlenemez yönetilen.

Aşağıdaki örnek, C3280 oluşturur:

```
// C3280_2.cpp
// compile with: /clr
ref struct A {
   void func();
};

#pragma managed(push,off)

void A::func()   // C3280
{
}

#pragma managed(pop)
```

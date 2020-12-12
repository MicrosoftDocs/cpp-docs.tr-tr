---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3280'
title: Derleyici hatası C3280
ms.date: 11/04/2016
f1_keywords:
- C3280
helpviewer_keywords:
- C3280
ms.assetid: 86dc5bbc-8818-4786-a728-9334268d308b
ms.openlocfilehash: f85731b20e98088fdfd8e894a942ce8d16b553bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194182"
---
# <a name="compiler-error-c3280"></a>Derleyici hatası C3280

' class ': yönetilen bir türün üye işlevi yönetilmeyen bir işlev olarak derlenemez

Yönetilen sınıf üyesi işlevleri yönetilmeyen işlevler olarak derlenemiyor.

Aşağıdaki örnek C3280 oluşturur:

```cpp
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

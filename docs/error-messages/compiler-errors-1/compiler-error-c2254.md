---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2254'
title: Derleyici hatası C2254
ms.date: 11/04/2016
f1_keywords:
- C2254
helpviewer_keywords:
- C2254
ms.assetid: 49bb3d7e-3bdf-4af6-937c-fa627be412a9
ms.openlocfilehash: f649bcf46af3830881893e2520fabd3a4c2308ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134803"
---
# <a name="compiler-error-c2254"></a>Derleyici hatası C2254

' function ': saf belirtici veya soyut geçersiz kılma tanımlayıcısına arkadaş işlevinde izin verilmiyor

Bir **`friend`** işlev saf olarak belirtilir **`virtual`** .

Aşağıdaki örnek C2254 oluşturur:

```cpp
// C2254.cpp
// compile with: /c
class A {
public:
   friend void func1() = 0;   // C2254, func1 is friend
   void virtual func2() = 0;   // OK, pure virtual
   friend void func3();   // OK, friend not virtual nor pure
};

void func1() {};
void func3() {};
```

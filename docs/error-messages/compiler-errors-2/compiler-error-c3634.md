---
title: Derleyici Hatası C3634
ms.date: 11/04/2016
f1_keywords:
- C3634
helpviewer_keywords:
- C3634
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
ms.openlocfilehash: 2acd76fee5e7ca309991e639044a45ea83ed112b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527549"
---
# <a name="compiler-error-c3634"></a>Derleyici Hatası C3634

'function': yönetilen veya WinRTclass soyut bir yöntemi tanımlanamıyor

Soyut Metoda yönetilen veya WinRT sınıfı, ancak içinde bildirilebilir tanımlanamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3634 oluşturur:

```
// C3634.cpp
// compile with: /clr
ref class C {
   virtual void f() = 0;
};

void C::f() {   // C3634 - don't define managed class' pure virtual method
}
```

---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3634'
title: Derleyici hatası C3634
ms.date: 11/04/2016
f1_keywords:
- C3634
helpviewer_keywords:
- C3634
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
ms.openlocfilehash: 21407af8a86a3f82331d0f2a1d424457d8bee833
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239252"
---
# <a name="compiler-error-c3634"></a>Derleyici hatası C3634

' function ': yönetilen veya WinRTclass 'ın soyut bir yöntemi tanımlanamıyor

Abstract yöntemi yönetilen veya WinRT sınıfında bildirilemez, ancak tanımlanamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3634 oluşturur:

```cpp
// C3634.cpp
// compile with: /clr
ref class C {
   virtual void f() = 0;
};

void C::f() {   // C3634 - don't define managed class' pure virtual method
}
```

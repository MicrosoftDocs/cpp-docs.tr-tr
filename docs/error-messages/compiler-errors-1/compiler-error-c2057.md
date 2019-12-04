---
title: Derleyici hatası C2057
ms.date: 11/04/2016
f1_keywords:
- C2057
helpviewer_keywords:
- C2057
ms.assetid: 038a99d6-1f5a-42fa-8449-03b4ff11ee0b
ms.openlocfilehash: 37dbc2f6ae0614215f0a3de20baa601b48db9450
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742450"
---
# <a name="compiler-error-c2057"></a>Derleyici hatası C2057

Sabit ifade bekleniyordu

Bağlam, değeri derleme zamanında bilinen bir ifade olan sabit bir ifade gerektirir.

Derleyicinin, bu türün bir örneği için alan ayırabilmek üzere derleme zamanında bir türün boyutunu bilmesi gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2057 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2057.cpp
int i;
int b[i];   // C2057 - value of i is unknown at compile time
int main() {
   const int i = 8;
   int b[i]; // OK - value of i is fixed and known to compiler
}
```

## <a name="example"></a>Örnek

C, sabit ifadeler için daha kısıtlayıcı kurallara sahiptir.  Aşağıdaki örnek C2057 oluşturur ve nasıl düzeltileceğini gösterir:

```
// C2057b.c
#define ArraySize1 10
int main() {
   const int ArraySize2 = 10;
   int h[ArraySize2];   // C2057 - C does not allow variables here
   int h[ArraySize1];   // OK - uses preprocessor constant
}
```

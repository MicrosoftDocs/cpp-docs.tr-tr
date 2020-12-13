---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2758'
title: Derleyici hatası C2758
ms.date: 11/04/2016
f1_keywords:
- C2758
helpviewer_keywords:
- C2758
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
ms.openlocfilehash: 28ca42a5dc62ad17fef59ca129092f791a12a39f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336177"
---
# <a name="compiler-error-c2758"></a>Derleyici hatası C2758

' üye ': başvuru türünün bir üyesinin başlatılması gerekir

Derleyici hatası C2758, Oluşturucu bir başlatıcı listesinde başvuru türünün bir üyesini başlatmadığında oluşur. Derleyici, üyeyi tanımsız olarak bırakır. Başvuru üye değişkenleri, oluşturucunun başlatma listesinde bir değer verildiğinde veya verildiğinde başlatılmalıdır.

Aşağıdaki örnek C2758 oluşturur:

```cpp
// C2758.cpp
// Compile by using: cl /W3 /c C2758.cpp
struct A {
   const int i;

   A(int n) { };   // C2758
   // try the following line instead
   // A(int n) : i{n} {};
};
```

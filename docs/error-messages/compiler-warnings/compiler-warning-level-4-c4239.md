---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4239'
title: Derleyici Uyarısı (düzey 4) C4239
ms.date: 11/04/2016
f1_keywords:
- C4239
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
ms.openlocfilehash: 635795392b5544f4985305a02e8534188c049224
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334854"
---
# <a name="compiler-warning-level-4-c4239"></a>Derleyici Uyarısı (düzey 4) C4239

Standart olmayan uzantı kullanıldı: ' token ': ' Type ' türünden ' Type ' türüne dönüştürme

C++ standardı tarafından bu tür dönüştürmeye izin verilmez, ancak burada bir uzantı olarak izin verilir. Bu uyarı, her zaman, ihlal edilen dil kuralını açıklayan en az bir açıklama satırı tarafından izlenir.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C4239 oluşturur.

```cpp
// C4239.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

void func(void) {
   C & rC = C();   // C4239
   const C & rC2 = C();   // OK
   rC2;
}
```

İntegral türünden numaralandırma türüne dönüştürmeye kesinlikle izin verilmez.

Aşağıdaki örnek C4239 oluşturur.

```cpp
// C4239b.cpp
// compile with: /W4 /c
enum E { value };
struct S {
   E e : 2;
} s = { 5 };   // C4239
// try the following line instead
// } s = { (E)5 };
```

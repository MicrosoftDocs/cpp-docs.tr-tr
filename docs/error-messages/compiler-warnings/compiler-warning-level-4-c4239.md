---
title: Derleyici Uyarısı (düzey 4) C4239
ms.date: 11/04/2016
f1_keywords:
- C4239
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
ms.openlocfilehash: 25b97cfb50847a0929f3d3a97b822209e6a11900
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686684"
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

---
title: Derleyici Uyarısı (düzey 4) C4239
ms.date: 11/04/2016
f1_keywords:
- C4239
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
ms.openlocfilehash: fcb66fca7e5b8708171849f885518c15b8355ac4
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541728"
---
# <a name="compiler-warning-level-4-c4239"></a>Derleyici Uyarısı (düzey 4) C4239

Standart olmayan uzantı kullanıldı: ' token ': ' Type ' türünden ' Type ' türüne dönüştürme

Bu tür dönüştürmeye C++ standart tarafından izin verilmez, ancak burada uzantı olarak izin verilir. Bu uyarı, her zaman, ihlal edilen dil kuralını açıklayan en az bir açıklama satırı tarafından izlenir.

## <a name="example"></a>Örnek

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

## <a name="example"></a>Örnek

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
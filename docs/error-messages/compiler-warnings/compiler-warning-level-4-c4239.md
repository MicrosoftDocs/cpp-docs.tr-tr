---
title: Derleyici Uyarısı (düzey 4) C4239
ms.date: 11/04/2016
f1_keywords:
- C4239
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
ms.openlocfilehash: 067d1aef41280f4d14fe799e4f4ee26a9f1b9f5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401026"
---
# <a name="compiler-warning-level-4-c4239"></a>Derleyici Uyarısı (düzey 4) C4239

Standart olmayan uzantı kullanıldı: 'belirteci': 'type' öğesinden 'type' dönüştürme

Bu tür dönüştürme C++ standardına göre izin verilmez, ancak izin verilip bir uzantısı olarak burada. Bu uyarı, her zaman en az bir ihlal dil kuralı tanımlayan bir açıklama satırı tarafından izlenir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4239 oluşturur.

```
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

İntegral türünden numaralandırma türüne dönüştürme kesinlikle izin verilmiyor.

Aşağıdaki örnek, C4239 oluşturur.

```
// C4239b.cpp
// compile with: /W4 /c
enum E { value };
struct S {
   E e : 2;
} s = { 5 };   // C4239
// try the following line instead
// } s = { (E)5 };
```
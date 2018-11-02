---
title: Derleyici Hatası C2271
ms.date: 11/04/2016
f1_keywords:
- C2271
helpviewer_keywords:
- C2271
ms.assetid: ea47bf57-f55d-4171-8e98-95a71d62820e
ms.openlocfilehash: 68de819ca62e117036bb415a1708afc0ecd6028c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572828"
---
# <a name="compiler-error-c2271"></a>Derleyici Hatası C2271

'operator': yeni/delete biçimsel liste değiştiricilerine sahip olamaz

İşleç (`new` veya `delete`) bellek-model tanımlayıcısı ile bildirilir.

Aşağıdaki örnek, C2271 oluşturur:

```
// C2271.cpp
// compile with: /c
void* operator new(size_t) const {   // C2271
// try the following line instead
// void* operator new(size_t) {
   return 0;
}

struct X {
   static void* operator new(size_t) const;   // C2271
   // try the following line instead
   // void * X::operator new(size_t) const;   // static member operator new
};
```
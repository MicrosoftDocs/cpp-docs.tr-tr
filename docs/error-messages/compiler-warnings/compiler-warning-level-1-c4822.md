---
title: Derleyici Uyarısı (düzey 1) C4822
ms.date: 11/04/2016
f1_keywords:
- C4822
helpviewer_keywords:
- C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
ms.openlocfilehash: f54f29fcbc6fb71033bc6d1d87c7ddb31622ee40
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051249"
---
# <a name="compiler-warning-level-1-c4822"></a>Derleyici Uyarısı (düzey 1) C4822

' üye ': Yerel sınıf üyesi işlevin gövdesi yok

Yerel sınıf üyesi işlevi bildirildi ancak sınıfında tanımlı değil. Yerel sınıf üyesi işlevi kullanmak için, bunu sınıfında tanımlamanız gerekir. Bu sınıfı sınıfında bildiremezsiniz ve sınıfından tanımlayamazsınız.

Yerel sınıf üyesi işlevi için herhangi bir sınıf dışı tanım bir hata olacaktır.

Aşağıdaki örnek C4822 oluşturur:

```cpp
// C4822.cpp
// compile with: /W1
int main() {
   struct C {
      void func1(int);   // C4822
      // try the following line instead
      // void func1(int){}
  };
}
```
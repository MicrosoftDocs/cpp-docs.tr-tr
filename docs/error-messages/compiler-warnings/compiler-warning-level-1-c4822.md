---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4822'
title: Derleyici Uyarısı (düzey 1) C4822
ms.date: 11/04/2016
f1_keywords:
- C4822
helpviewer_keywords:
- C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
ms.openlocfilehash: 8e5fe62d70243da0121d58e553c500e5a079022a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198056"
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

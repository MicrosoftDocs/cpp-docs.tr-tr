---
title: Derleyici Uyarısı (düzey 1) C4822
ms.date: 11/04/2016
f1_keywords:
- C4822
helpviewer_keywords:
- C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
ms.openlocfilehash: 59c42227c7e8be9bd31c37776d9724d23db61837
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174875"
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

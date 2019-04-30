---
title: Derleyici Uyarısı (düzey 1) C4822
ms.date: 11/04/2016
f1_keywords:
- C4822
helpviewer_keywords:
- C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
ms.openlocfilehash: 02e7ba11f7bda134bcc98ce2c494a3ef367c0d6f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378511"
---
# <a name="compiler-warning-level-1-c4822"></a>Derleyici Uyarısı (düzey 1) C4822

'member': yerel sınıf üyesi işlevinde bir gövde yok

Bir yerel sınıf üyesi işlevinde bildirildi, ancak sınıfta tanımlı değil. Bir yerel sınıf üyesi işlevi kullanmak için sınıfta tanımlamanız gerekir. Sınıfında bildirin ve dışında sınıfı tanımlayın.

Bir hata için bir yerel sınıf üyesi işlevinde herhangi bir sınıf çıkış tanımının olacaktır.

Aşağıdaki örnek, C4822 oluşturur:

```
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
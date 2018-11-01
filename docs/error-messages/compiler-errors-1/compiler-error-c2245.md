---
title: Derleyici Hatası C2245
ms.date: 11/04/2016
f1_keywords:
- C2245
helpviewer_keywords:
- C2245
ms.assetid: 08aaeadf-10ec-485a-b2a6-6e775289082b
ms.openlocfilehash: 53288d86a59fe2cd31ddac4af7766360544c65c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603950"
---
# <a name="compiler-error-c2245"></a>Derleyici Hatası C2245

var olmayan üye işlevi 'function' arkadaş olarak belirtildi (üye işlev imzası hiçbir aşırı yüklemeyle eşleşmiyor)

Bir işlev bir arkadaş olarak belirtildi, derleyici tarafından bulunamadı.

Aşağıdaki örnek, C2245 oluşturur:

```
// C2245.cpp
// compile with: /c
class B {
   void f(int i);
};

class A {
   int m_i;
   friend void B::f(char);   // C2245
   // try the following line instead
   // friend void B::f(int);
};

void B::f(int i) {
   A a;
   a.m_i = 0;
}
```
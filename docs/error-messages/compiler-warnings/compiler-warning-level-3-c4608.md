---
title: Derleyici Uyarısı (düzey 3) C4608
ms.date: 11/04/2016
f1_keywords:
- C4608
helpviewer_keywords:
- C4608
ms.assetid: 8b8f5f28-8ce9-457e-9d3d-a8c0efce9b6a
ms.openlocfilehash: 4f1bef80b8cddccc036a5151bb4cc4ac01483a36
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466852"
---
# <a name="compiler-warning-level-3-c4608"></a>Derleyici Uyarısı (düzey 3) C4608

'union_member', 'union_member' Başlatıcı listesindeki başka bir birleşim üyesi tarafından zaten başlatıldı

İki üye aynı birleşimin bir başlatma listesi hazırlaması başlatılmış. Yalnızca birleşimin bir üyesine erişebilir.

Aşağıdaki örnek, C4608 oluşturur:

```
// C4608.cpp
// compile with: /W3 /c
class X {
public:
   X(char c) : m_i( c + 1), m_c(c) {}   // C4608
   // try the following line instead
   // X(char c) : m_c(c) {}

private:
   union {
      int m_i;
      char m_c;
   };
};

union Y {
public:
   Y(char * name) : m_number(0.3), m_string( name ) {} // C4608

private:
   double m_number;
   char * m_string;
};
```
---
title: Derleyici Uyarısı (düzey 4) C4673
ms.date: 11/04/2016
f1_keywords:
- C4673
helpviewer_keywords:
- C4673
ms.assetid: 95626ec6-f05b-43c7-8b9a-a60a6f98dd30
ms.openlocfilehash: cd53aeb7f767b06c017c64caa55c916aa1e2b9c9
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990571"
---
# <a name="compiler-warning-level-4-c4673"></a>Derleyici Uyarısı (düzey 4) C4673

' tanımlayıcı ' üretiliyor aşağıdaki türler, catch sitesinde değerlendirilmeyecek

Bir throw nesnesi **catch** bloğunda işlenemiyor. İşlenmeyen her tür, bu uyarıyı içeren satırın hemen ardından hata çıktısında listelenir. İşlenmemiş her tür kendi uyarısına sahiptir. Daha fazla bilgi için her belirli tür için uyarıyı okuyun.

Aşağıdaki örnek C4673 oluşturur:

```cpp
// C4673.cpp
// compile with: /EHsc /W4
class Base {
private:
   char * m_chr;
public:
   Base() {
      m_chr = 0;
   }

   ~Base() {
      if(m_chr)
         delete m_chr;
   }
};

class Derv : private Base {
public:
   Derv() {}
   ~Derv() {}
};

int main() {
   try {
      Derv D1;
      // delete previous line, uncomment the next line to resolve
      // Base D1;
      throw D1;   // C4673
   }

   catch(...) {}
}
```

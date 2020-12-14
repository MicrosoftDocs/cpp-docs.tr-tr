---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2296'
title: Derleyici hatası C2296
ms.date: 11/04/2016
f1_keywords:
- C2296
helpviewer_keywords:
- C2296
ms.assetid: 47d270f4-13ce-4c16-81e2-7d67c6c4a540
ms.openlocfilehash: 4c36eb5f01b970b9435b45c75232d875de5818a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235235"
---
# <a name="compiler-error-c2296"></a>Derleyici hatası C2296

' operator ': bozuk sol işlenen

İle kullanılan sol işlenen `operator` geçersiz.

Örneğin, derleyici bir işlev çağrısını amaçladığınız bir bildirim görebilir.

Aşağıdaki örnek C2296 oluşturur:

```cpp
// C2296.cpp
struct MyStruct {
   struct Help {
      Help(float f) : m_f(f) {}
      float m_f;
   };

   MyStruct(const Help &h) : m_f(h.m_f) {}
   MyStruct(float f) : m_f(f) {}
   MyStruct operator*(const MyStruct &f1) const {
      return MyStruct(m_f * f1.m_f);
   }

private:
   float m_f;
};

int main() {
   float f1 = 1.0f;

   MyStruct m_MyStruct1 ( MyStruct::Help( f1 ) );
   // try the following line instead
   // MyStruct m_MyStruct1 = MyStruct::Help( f1 );

   MyStruct m_MyStruct2 ( MyStruct::Help( f1 ) );
   // try the following line instead
   // MyStruct m_MyStruct2 = MyStruct::Help( f1 );

   MyStruct m_MyStruct3 = m_MyStruct1 * m_MyStruct2;   // C2296
}
```

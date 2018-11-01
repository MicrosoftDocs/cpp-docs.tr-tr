---
title: Derleyici Hatası C2297
ms.date: 11/04/2016
f1_keywords:
- C2297
helpviewer_keywords:
- C2297
ms.assetid: 65849fe5-17e1-4b7e-b50c-f508b05ddaa4
ms.openlocfilehash: f2b1fb0590b8fd72b0365185b245d7b16566d11d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601363"
---
# <a name="compiler-error-c2297"></a>Derleyici Hatası C2297

'operator': hatalı sağ işlenen

İle kullanılan sağ işlenen `operator` geçersiz.

Örneğin, derleyici bir bildirimi işlev çağrısı hedeflenen burada görebilirsiniz.

Aşağıdaki örnek, C2297 oluşturur:

```
// C2297.cpp
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

   MyStruct m_MyStruct3 = m_MyStruct1 * m_MyStruct2;   // C2297
}
```
---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3352'
title: Derleyici hatası C3352
ms.date: 11/04/2016
f1_keywords:
- C3352
helpviewer_keywords:
- C3352
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
ms.openlocfilehash: 66d6921c86c6b7a30026880f01ab2a5dada11a65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150949"
---
# <a name="compiler-error-c3352"></a>Derleyici hatası C3352

' function ': belirtilen işlev ' Type ' temsilci türüyle eşleşmiyor

İçin parametre listeleri `function` ve temsilci eşleşmiyor.

Daha fazla bilgi için bkz. [Temsilci (C++ Bileşen Uzantıları)](../../extensions/delegate-cpp-component-extensions.md).

Aşağıdaki örnek C3352 oluşturur:

```cpp
// C3352.cpp
// compile with: /clr
delegate int D( int, int );
ref class C {
public:
   int mf( int ) {
      return 1;
   }

   // Uncomment the following line to resolve.
   // int mf(int, int) { return 1; }
};

int main() {
   C^ pC = gcnew C;
   System::Delegate^ pD = gcnew D( pC, &C::mf );   // C3352
}
```

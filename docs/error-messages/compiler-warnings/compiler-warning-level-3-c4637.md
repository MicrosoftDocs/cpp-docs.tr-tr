---
title: Derleyici Uyarısı (Düzey 3) C4637
ms.date: 11/04/2016
f1_keywords:
- C4637
helpviewer_keywords:
- C4637
ms.assetid: 5fd347c1-2de9-408f-9136-1bf1ff273622
ms.openlocfilehash: 02c759b9ece2e0c842a86f3cd0269beac8e4dd83
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526691"
---
# <a name="compiler-warning-level-3-c4637"></a>Derleyici Uyarısı (Düzey 3) C4637

XML belgesi yorum hedef: \<dahil > Etiket atıldı.  Nedeni

Söz dizimi bir [ \<dahil >](../../ide/include-visual-cpp.md) etiketi doğru değildi.

Aşağıdaki örnek, C4637 oluşturur:

```
// C4637.cpp
// compile with: /clr /doc /LD /W3
using namespace System;

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <include file="c:\davedata\jtest\xml_include.doc"/>
   // Try the following line instead:
   // /// <include file='xml_include.doc' path='MyDocs/MyMembers/*' />
   void MyMethod() {
   }
};   // C4637
```
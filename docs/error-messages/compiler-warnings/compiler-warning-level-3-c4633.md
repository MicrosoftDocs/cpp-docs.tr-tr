---
title: Derleyici Uyarısı (düzey 3) C4633
ms.date: 11/04/2016
f1_keywords:
- C4633
helpviewer_keywords:
- C4633
ms.assetid: 6d76f268-ba8c-448b-8e83-b903a18b583b
ms.openlocfilehash: 91a1f2a646adca7cf121528779bf0ded4d37024e
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991910"
---
# <a name="compiler-warning-level-3-c4633"></a>Derleyici Uyarısı (düzey 3) C4633

XML belgesi Açıklama hedefi: hata: neden

[\<param >](../../build/reference/param-visual-cpp.md) etiketine geçirilen bir ad derleyici tarafından bulunamadı.

Aşağıdaki örnek C4633 oluşturur:

```cpp
// C4633.cpp
// compile with: /clr /doc /LD /W3

/// Text for class MyClass.
public ref class MyClass {
   // C4633 remove line for Int3
   /// <param name="Int1">Used to indicate status.</param>
   /// <param name="Int3">Used to indicate status.</param>
   void MyMethod(int Int1) {
      Int1 = 0;
      Int1++;
   }
};
```

---
title: Derleyici hatası C3195
ms.date: 11/04/2016
f1_keywords:
- C3195
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
ms.openlocfilehash: c8274e121e953c3e51a0f2ff8c68c315759ce3e1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760432"
---
# <a name="compiler-error-c3195"></a>Derleyici hatası C3195

' operator ': ayrılmıştır ve bir başvuru sınıfının veya değer türünün üyesi olarak kullanılamaz. CLR veya WinRT işleçleri ' operator ' anahtar sözcüğü kullanılarak tanımlanmalıdır

Derleyici, sözdizimi için C++ yönetilen uzantıları kullanarak bir operatör tanımı algıladı. İşleçler için C++ sözdizimini kullanmanız gerekir.

Aşağıdaki örnek C3195 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3195.cpp
// compile with: /clr /LD
#using <mscorlib.dll>
value struct V {
   static V op_Addition(V v, int i);   // C3195
   static V operator +(V v, char c);   // OK for new C++ syntax
};
```

---
title: Derleyici hatası C2364
ms.date: 11/04/2016
f1_keywords:
- C2364
helpviewer_keywords:
- C2364
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
ms.openlocfilehash: fb019d729bc100296742b15ba95460fe0e404673
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759886"
---
# <a name="compiler-error-c2364"></a>Derleyici hatası C2364

' Type ': özel öznitelik için geçersiz tür

Özel öznitelikler için adlandırılmış bağımsız değişkenler, derleme süresi sabitleriyle sınırlıdır. Örneğin, integral türleri (int, Char, vb.), System:: Type ^ ve System:: Object ^.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2364 oluşturur.

```cpp
// c2364.cpp
// compile with: /clr /c
using namespace System;

[attribute(AttributeTargets::All)]
public ref struct ABC {
public:
   // Delete the following line to resolve.
   ABC( Enum^ ) {}   // C2364
   ABC( int ) {}   // OK
};
```

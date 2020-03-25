---
title: Derleyici Uyarısı (düzey 3) C4357
ms.date: 11/04/2016
f1_keywords:
- C4357
helpviewer_keywords:
- C4357
ms.assetid: 9259c633-3c02-4900-b94a-2d8d366d61cd
ms.openlocfilehash: 3af2e742bde40bc3787603e32efbc34e59dcb419
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198711"
---
# <a name="compiler-warning-level-3-c4357"></a>Derleyici Uyarısı (düzey 3) C4357

' del ' temsilcisinin biçimsel bağımsız değişken listesinde param dizisi bağımsız değişkeni ' function ' üretilirken yoksayıldı

`ParamArray` özniteliği yoksayıldı ve `function` değişken bağımsız değişkenlerle çağrılamaz.

Aşağıdaki örnek C4357 oluşturur:

```cpp
// C4357.cpp
// compile with: /clr /W3 /c
using namespace System;
public delegate void f(int i, ... array<Object^>^ varargs);   // C4357

public delegate void g(int i, array<Object^>^ varargs);   // OK
```

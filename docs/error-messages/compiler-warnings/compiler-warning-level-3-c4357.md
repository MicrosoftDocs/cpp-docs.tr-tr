---
title: Derleyici Uyarısı (Düzey 3) C4357 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4357
dev_langs:
- C++
helpviewer_keywords:
- C4357
ms.assetid: 9259c633-3c02-4900-b94a-2d8d366d61cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5bf30112e152c473c4f88a98f5f1073b789216e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086752"
---
# <a name="compiler-warning-level-3-c4357"></a>Derleyici Uyarısı (Düzey 3) C4357

biçimsel bağımsız değişken listesinde param dizisi bağımsız değişkeni, '' function' üretilirken yoksayıldı del' temsilci seçme

`ParamArray` Özniteliği yoksayıldı ve `function` değişken bağımsız değişkenlerle çağrılamaz.

Aşağıdaki örnek, C4357 oluşturur:

```
// C4357.cpp
// compile with: /clr /W3 /c
using namespace System;
public delegate void f(int i, ... array<Object^>^ varargs);   // C4357

public delegate void g(int i, array<Object^>^ varargs);   // OK
```
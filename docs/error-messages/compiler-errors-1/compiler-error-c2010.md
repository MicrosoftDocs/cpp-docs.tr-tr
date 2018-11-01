---
title: Derleyici Hatası C2010
ms.date: 11/04/2016
f1_keywords:
- C2010
helpviewer_keywords:
- C2010
ms.assetid: 5795ed1d-e206-410b-b7b4-528d125c67b4
ms.openlocfilehash: 71cb0012f5e7bda3a0f1409fe71649a5bd0944b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434231"
---
# <a name="compiler-error-c2010"></a>Derleyici Hatası C2010

'character': makro biçimsel parametre listesinde beklenmeyen

Karakter, yanlış bir Makro tanımında biçimsel parametre listesinde kullanılır. Hatayı gidermek için karakteri kaldırın.

Aşağıdaki örnek, C2010 oluşturur:

```
// C2010.cpp
// compile with: /c
#define mymacro(a|) (2*a)   // C2010
#define mymacro(a) (2*a)   // OK
```
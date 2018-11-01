---
title: Derleyici Hatası C2344
ms.date: 11/04/2016
f1_keywords:
- C2344
helpviewer_keywords:
- C2344
ms.assetid: a84c7b37-c84e-4345-8691-c23abb2dc193
ms.openlocfilehash: d1ba3a0f975dbc96c9c6ca51a8dac89b5a614572
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439488"
---
# <a name="compiler-error-c2344"></a>Derleyici Hatası C2344

align(#): hizalama ikinin üssü olmalıdır

Kullanırken [hizalama](../../cpp/align-cpp.md) anahtar sözcüğü, geçirdiğiniz değer ikinin kuvveti olması gerekir.

Örneğin, 3 ikinin kuvveti olmadığı için aşağıdaki kodu C2344 oluşturur:

```
// C2344.cpp
// compile with: /c
__declspec(align(3)) int a;   // C2344
__declspec(align(4)) int b;   // OK
```
---
title: Derleyici Uyarısı (düzey 1) C4602
ms.date: 11/04/2016
f1_keywords:
- C4602
helpviewer_keywords:
- C4602
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
ms.openlocfilehash: c719ae23ed3799debf2db9c8f2d82b3c49db3156
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406463"
---
# <a name="compiler-warning-level-1-c4602"></a>Derleyici Uyarısı (düzey 1) C4602

\#pop_macro pragması: 'makro adı' önceki hiçbir #pragma push_macro bu tanımlayıcısı

Kullanırsanız [pop_macro](../../preprocessor/pop-macro.md) belirli bir makro için önce bu makro adı geçen gerekir [push_macro](../../preprocessor/push-macro.md). Örneğin, aşağıdaki örnek C4602 oluşturur:

```
// C4602.cpp
// compile with: /W1
int main()
{
   #pragma pop_macro("x")   // C4602 x is not on the stack
}
```
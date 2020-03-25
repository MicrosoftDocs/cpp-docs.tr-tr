---
title: Derleyici Uyarısı (düzey 1) C4602
ms.date: 11/04/2016
f1_keywords:
- C4602
helpviewer_keywords:
- C4602
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
ms.openlocfilehash: f93af5b37c87e30891dd09009b53e73c7d384b1c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162133"
---
# <a name="compiler-warning-level-1-c4602"></a>Derleyici Uyarısı (düzey 1) C4602

\#pragma pop_macro: ' makro adı ' Bu tanımlayıcı için önceki #pragma push_macro yok

Belirli bir makro için [pop_macro](../../preprocessor/pop-macro.md) kullanırsanız, önce bu makro adını [push_macro](../../preprocessor/push-macro.md)geçirmelisiniz. Örneğin, aşağıdaki örnek C4602 oluşturur:

```cpp
// C4602.cpp
// compile with: /W1
int main()
{
   #pragma pop_macro("x")   // C4602 x is not on the stack
}
```

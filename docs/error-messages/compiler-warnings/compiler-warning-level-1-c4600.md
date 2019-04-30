---
title: Derleyici Uyarısı (düzey 1) C4600
ms.date: 11/04/2016
f1_keywords:
- C4600
helpviewer_keywords:
- C4600
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
ms.openlocfilehash: fcfefd5b858df653551e7f3061a41d168c8ff3f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397230"
---
# <a name="compiler-warning-level-1-c4600"></a>Derleyici Uyarısı (düzey 1) C4600

\#pragma 'makro adı': geçerli bir boş olmayan dize bekleniyor

Anında iletme veya bir makro adı ile ya da açılan boş bir dize belirtilemiyor [pop_macro](../../preprocessor/pop-macro.md) veya [push_macro](../../preprocessor/push-macro.md).

Aşağıdaki örnek, C4600 oluşturur:

```
// C4600.cpp
// compile with: /W1
int main()
{
   #pragma push_macro("")   // C4600 passing an empty string
}
```
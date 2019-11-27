---
title: Derleyici Uyarısı (düzey 3) C4557
ms.date: 11/04/2016
f1_keywords:
- C4557
helpviewer_keywords:
- C4557
ms.assetid: 7d9db716-03b2-4ee5-9b09-ba8aa5aa7e4c
ms.openlocfilehash: 22ee456c5f79434c5e3b8a79b4c174aa3cdb3c7a
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188947"
---
# <a name="compiler-warning-level-3-c4557"></a>Derleyici Uyarısı (düzey 3) C4557

'__assume' 'effect' etkisini içeriyor

Bir [__assume](../../intrinsics/assume.md) Deyim2 'e geçirilen değer değiştirildi.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4557 oluşturur:

```cpp
// C4557.cpp
// compile with: /W3
#pragma warning(default : 4557)
int main()
{
   int i;
   __assume(i++);   // C4557
}
```
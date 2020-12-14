---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4557'
title: Derleyici Uyarısı (düzey 3) C4557
ms.date: 11/04/2016
f1_keywords:
- C4557
helpviewer_keywords:
- C4557
ms.assetid: 7d9db716-03b2-4ee5-9b09-ba8aa5aa7e4c
ms.openlocfilehash: 606c1cdb36d79b13ad914912fb570c82e38eed2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257790"
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

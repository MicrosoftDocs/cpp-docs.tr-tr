---
title: Derleyici Uyarısı (düzey 1) C4561
ms.date: 11/04/2016
f1_keywords:
- C4561
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
ms.openlocfilehash: 24a3ca8b35266e93f298314f45015b7a480e2af0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563793"
---
# <a name="compiler-warning-level-1-c4561"></a>Derleyici Uyarısı (düzey 1) C4561

'__fastcall' ile uyumsuz ' / clr' seçeneği: dönüştürme '\__stdcall'

[__Fastcall](../../cpp/fastcall.md) işlevi çağırma kuralı ile kullanılamaz [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği. Çağrıları derleyicinin yoksaydığı `__fastcall`. Bu uyarıyı düzeltmek için çağrıları kaldırın **__fastcall** veya olmadan derleme **/CLR**.

Aşağıdaki örnek, C4561 oluşturur:

```
// C4561.cpp
// compile with: /clr /W1 /c
// processor: x86
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve
```
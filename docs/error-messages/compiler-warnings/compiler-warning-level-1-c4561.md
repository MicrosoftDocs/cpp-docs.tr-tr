---
title: Derleyici Uyarısı (düzey 1) C4561
ms.date: 11/04/2016
f1_keywords:
- C4561
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
ms.openlocfilehash: 11a1bcdc8396b1eb74121c27154b8c6c24fa92a6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162289"
---
# <a name="compiler-warning-level-1-c4561"></a>Derleyici Uyarısı (düzey 1) C4561

' __fastcall ' '/CLR ' seçeneğiyle uyumsuz: '\__stdcall ' olarak dönüştürülüyor

[__Fastcall](../../cpp/fastcall.md) işlev çağırma kuralı [/clr](../../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ile kullanılamaz. Derleyici `__fastcall`çağrılarını yoksayar. Bu uyarıyı onarmak için **__fastcall** çağrıları kaldırın ya da **/clr**olmadan derleyin.

Aşağıdaki örnek C4561 oluşturur:

```cpp
// C4561.cpp
// compile with: /clr /W1 /c
// processor: x86
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve
```

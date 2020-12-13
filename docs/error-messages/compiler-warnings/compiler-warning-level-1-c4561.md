---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4561'
title: Derleyici Uyarısı (düzey 1) C4561
ms.date: 11/04/2016
f1_keywords:
- C4561
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
ms.openlocfilehash: fc94879039f72bba0734240bc26d152965d6b650
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337297"
---
# <a name="compiler-warning-level-1-c4561"></a>Derleyici Uyarısı (düzey 1) C4561

' __fastcall ' '/CLR ' seçeneğiyle uyumsuz: ' _stdcall ' olarak dönüştürülüyor \_

[__Fastcall](../../cpp/fastcall.md) işlev çağırma kuralı [/clr](../../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ile kullanılamaz. Derleyici, öğesine yapılan çağrıları yoksayar **`__fastcall`** . Bu uyarıyı onarmak için,/clr olmadan yapılan çağrıları kaldırın **`__fastcall`** veya derleyin. 

Aşağıdaki örnek C4561 oluşturur:

```cpp
// C4561.cpp
// compile with: /clr /W1 /c
// processor: x86
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve
```

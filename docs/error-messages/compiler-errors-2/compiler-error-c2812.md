---
title: Derleyici hatası C2812
ms.date: 11/04/2016
f1_keywords:
- C2812
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
ms.openlocfilehash: cec92982646c64e6c5b669df328e4836d4f44df8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202113"
---
# <a name="compiler-error-c2812"></a>Derleyici hatası C2812

> \#içeri aktarma/clr: Pure ve/clr: Safe ile desteklenmez

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

[#import yönergesi](../../preprocessor/hash-import-directive-cpp.md) **/clr: Pure** ve **/clr: Safe** ile desteklenmediğinden, `#import` yerel derleyici desteği kitaplıklarının kullanılmasını gerektirir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2812 oluşturur.

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```

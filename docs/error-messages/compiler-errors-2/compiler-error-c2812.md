---
title: Derleyici Hatası C2812
ms.date: 11/04/2016
f1_keywords:
- C2812
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
ms.openlocfilehash: 88b071f38cf41db9c929d25ffd526b3f2b7ca468
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531826"
---
# <a name="compiler-error-c2812"></a>Derleyici Hatası C2812

> \#içeri aktarma/CLR ile desteklenmiyor: pure ve/CLR: safe

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

[#import yönergesi](../../preprocessor/hash-import-directive-cpp.md) desteklenmeyen **/CLR: pure** ve **/CLR: safe** çünkü `#import` yerel derleyici desteği kitaplıklarını kendim kullanılmasını gerektirir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2812 oluşturur.

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```
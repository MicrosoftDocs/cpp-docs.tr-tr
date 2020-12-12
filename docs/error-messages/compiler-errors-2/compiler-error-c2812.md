---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2812'
title: Derleyici hatası C2812
ms.date: 11/04/2016
f1_keywords:
- C2812
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
ms.openlocfilehash: d59105397ae773c2a46b04a64eb50da3055c3a4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278434"
---
# <a name="compiler-error-c2812"></a>Derleyici hatası C2812

> \#/clr: Pure ve/clr: Safe ile içeri aktarma desteklenmez

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

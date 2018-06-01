---
title: Derleyici Hatası C2812 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2812
dev_langs:
- C++
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c5469e4f7be3c164cc63fa30f5069009846be48
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705029"
---
# <a name="compiler-error-c2812"></a>Derleyici Hatası C2812

> \#Alma/CLR ile desteklenmiyor: saf ve/CLR: safe

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

[#import yönergesi](../../preprocessor/hash-import-directive-cpp.md) desteklenmeyen **/CLR: pure** ve **/CLR: safe** çünkü `#import` yerel derleyici desteği kitaplıkları kullanılmasını gerektirir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2812 oluşturur.

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```
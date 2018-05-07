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
ms.openlocfilehash: 28d46b0f9744f192d677d7b2df27b67e734de1b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2812"></a>Derleyici Hatası C2812
\#Alma/CLR ile desteklenmiyor: saf ve/CLR: safe  
  
 **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
 [#import yönergesi](../../preprocessor/hash-import-directive-cpp.md) desteklenmeyen **/CLR: pure** ve **/CLR: safe** çünkü `#import` yerel derleyici desteği kitaplıkları kullanılmasını gerektirir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2812 oluşturur.  
  
```  
// C2812.cpp  
// compile with: /clr:pure /c  
#import "importlib.tlb"   // C2812  
```
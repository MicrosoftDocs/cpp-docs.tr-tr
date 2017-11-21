---
title: "Derleyici Hatası C2812 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2812
dev_langs: C++
helpviewer_keywords: C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 859d371d5886ece416ea6d60c405b114a527864f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
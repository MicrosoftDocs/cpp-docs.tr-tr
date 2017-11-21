---
title: "Derleyici Hatası C3641 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3641
dev_langs: C++
helpviewer_keywords: C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 992e2a5d34b380146a99f6f78145b022eacd21d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3641"></a>Derleyici Hatası C3641
'function': / CLR ile derlenmiş işlevi için 'calling_convention' çağırma kuralı geçersiz: Saf veya/CLR: safe  
  
 **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
 Yalnızca [__clrcall](../../cpp/clrcall.md) çağırma kuralı ile verilir [/CLR: pure](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Aşağıdaki örnek C3641 oluşturur:  
  
```  
// C3641.cpp  
// compile with: /clr:pure /c  
void __cdecl f() {}   // C3641  
```
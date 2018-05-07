---
title: Derleyici Uyarısı (düzey 1) C4186 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4186
dev_langs:
- C++
helpviewer_keywords:
- C4186
ms.assetid: caf3f7d8-f305-426b-8d4e-2b96f5c269ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc40d2b9f43d041c7b04ba2bc77a0aba0630274c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4186"></a>Derleyici Uyarısı (düzey 1) C4186
\#içeri aktarma öznitelik 'özniteliği' sayısı bağımsız değişkenler gerektirir; göz ardı  
  
 A `#import` özniteliğine sahip yanlış sayıda bağımsız değişken.  
  
## <a name="example"></a>Örnek  
  
```  
// C4186.cpp  
// compile with: /W1 /c  
#import "stdole2.tlb" no_namespace("abc") rename("a","b","c")  // C4186  
```  
  
 `no_namespace` Bağımsız değişkenler özniteliği alır. **Yeniden adlandırma** özniteliği yalnızca iki bağımsız değişkenleri alır.
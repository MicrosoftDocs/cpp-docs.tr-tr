---
title: Önemli hata C1103 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1103
dev_langs:
- C++
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19f991fd7449eda11651dcca4adc73190e276e35
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1103"></a>Önemli hata C1103
önemli hata ProgID içeri aktarma: 'iletisi  
  
 Derleyici tür kitaplığını içeri aktarma bir sorun algıladı.  Örneğin, olamaz bir tür kitaplığı ile ProgID belirtin ve ayrıca belirtin `no_registry`.  
  
 Daha fazla bilgi için bkz: [#import yönergesi](../../preprocessor/hash-import-directive-cpp.md).  
  
 Aşağıdaki örnek C1103 üretir:  
  
```  
// C1103.cpp  
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103  
```
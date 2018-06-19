---
title: Önemli hata C1104 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1104
dev_langs:
- C++
helpviewer_keywords:
- C1104
ms.assetid: 45bd85c4-77d3-4d3c-b167-49c563aefb4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a1df9fc846a2534004bb956b02edbfb9865985d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33199872"
---
# <a name="fatal-error-c1104"></a>Önemli hata C1104
Kitaplık kimliği alınırken önemli hata oluştu: 'iletisi  
  
 Derleyici tür kitaplığını içeri aktarma bir sorun algıladı.  Örneğin, olamaz kitaplık kimliği ile bir tür kitaplığı belirtin ve ayrıca belirtin `no_registry`.  
  
 Daha fazla bilgi için bkz: [#import yönergesi](../../preprocessor/hash-import-directive-cpp.md).  
  
 Aşağıdaki örnek C1104 üretir:  
  
```  
// C1104.cpp  
#import "libid:11111111.1111.1111.1111.111111111111" version("4.0") lcid("9") no_registry auto_search   // C1104  
```
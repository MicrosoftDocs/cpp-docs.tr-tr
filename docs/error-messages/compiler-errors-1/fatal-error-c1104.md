---
title: "Önemli hata C1104 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1104
dev_langs:
- C++
helpviewer_keywords:
- C1104
ms.assetid: 45bd85c4-77d3-4d3c-b167-49c563aefb4d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ec6f6f7df6187da19b65c399def08be2a021c482
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
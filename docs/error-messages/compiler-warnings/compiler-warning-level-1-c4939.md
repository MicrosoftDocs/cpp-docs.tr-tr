---
title: Derleyici Uyarısı (düzey 1) C4939 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4939
dev_langs:
- C++
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 459674bb4e6899563a18943f7ba510a6168d0e28
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4939"></a>Derleyici Uyarısı (düzey 1) C4939
\#pragma vtordisp kullanım dışıdır ve Visual C++'ın bir sonraki sürümde kaldırılacak  
  
 [Vtordisp](../../preprocessor/vtordisp.md) pragma Visual C++'ın bir sonraki sürümde kaldırılacak.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4939 oluşturur.  
  
```  
// C4939.cpp  
// compile with: /c /W1  
#pragma vtordisp(off)   // C4939  
```
---
title: "Derleyici Uyarısı (düzey 1) C4939 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4939
dev_langs: C++
helpviewer_keywords: C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9e89d71449149ee4a79b35b4371f9e8b31b1953a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
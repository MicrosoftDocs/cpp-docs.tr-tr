---
title: "Önemli hata C1020 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1020
dev_langs:
- C++
helpviewer_keywords:
- C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 815ba707b24de22dae491a82ac6d4041745296b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1020"></a>Önemli hata C1020
Beklenmeyen #endif  
  
 `#endif` Yönergesi sahip eşleşen `#if`, `#ifdef`, veya `#ifndef` yönergesi. Her emin olmanız `#endif` eşleşen yönergesi yok.  
  
 Aşağıdaki örnek C1020 oluşturur:  
  
```  
// C1020.cpp  
#endif     // C1020  
```  
  
 Olası çözüm:  
  
```  
// C1020b.cpp  
// compile with: /c  
#if 1  
#endif  
```
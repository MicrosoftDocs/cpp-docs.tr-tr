---
title: "Derleyici Uyarısı (düzey 1) C4085 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4085
dev_langs: C++
helpviewer_keywords: C4085
ms.assetid: 2bc6eb25-058f-4597-b351-fd69587b5170
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 562d2433240c57b4d21bf0b2984f709d9ff54375
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4085"></a>Derleyici Uyarısı (düzey 1) C4085
'on' veya 'off' olması beklenen pragma parametresi  
  
 Pragma gerektiren bir **üzerinde** veya **kapalı** parametresi. Pragma göz ardı edilir.  
  
 Aşağıdaki örnek C4085 oluşturur:  
  
```  
// C4085.cpp  
// compile with: /W1 /LD  
#pragma optimize( "t", maybe )  // C4085  
```
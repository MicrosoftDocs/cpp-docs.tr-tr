---
title: "Derleyici Uyarısı (düzey 1) C4114 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4114
dev_langs: C++
helpviewer_keywords: C4114
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 44f58eeda59295b77a663f033695d00c0d36a1ef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4114"></a>Derleyici Uyarısı (düzey 1) C4114
birden çok kez kullanılan aynı tür niteleyicisi  
  
 Tür niteleyicisi türü bildirimi veya tanımı kullanır (**const**, `volatile`, **imzalı**, veya `unsigned`) birden çok kez. Bu Microsoft Uzantıları (/Ze) içeren bir uyarı ve ANSI uyumluluğu (/Za) altında bir hata neden olur.  
  
 Aşağıdaki örnek C4114 oluşturur:  
  
```  
// C4114.cpp  
// compile with: /W1 /c  
volatile volatile int i;   // C4114  
```  
  
 Aşağıdaki örnek C4114 oluşturur:  
  
```  
// C4114_b.cpp  
// compile with: /W1 /c  
static const int const * ii;   // C4114  
static const int * const iii;   // OK  
```
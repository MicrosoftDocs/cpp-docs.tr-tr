---
title: "Derleyici Uyarısı (Düzey 3) C4619 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4619
dev_langs: C++
helpviewer_keywords: C4619
ms.assetid: 701fea21-01aa-4bea-93d4-1cb8824170b0
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 041bafed08d1a32d5fbb1dfb86de63a59473e84b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4619"></a>Derleyici Uyarısı (Düzey 3) C4619
\#pragma uyarısı: uyarı numarası 'numara' yok  
  
 Var olmayan bir uyarı devre dışı bırakmak için girişimde bulunuldu.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C4619 oluşturur:  
  
```  
// C4619.cpp  
// compile with: /W3 /c  
#pragma warning(default : 4619)  
#pragma warning(disable : 4354)   // C4619, C4354 does not exist  
```
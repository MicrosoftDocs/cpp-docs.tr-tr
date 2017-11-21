---
title: "Derleyici Hatası C2334 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2334
dev_langs: C++
helpviewer_keywords: C2334
ms.assetid: 36142855-e00b-4bbf-80f5-a301edeff46e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b31ba4a8a5711fcdfbfca725938beb9afdf4301c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2334"></a>Derleyici Hatası C2334
Önceki beklenmeyen belirteçleri ': veya {'; görünen işlev gövdesi atlanıyor  
  
 Aşağıdaki örnek C2334 oluşturur. Bu hata C2059 hatasından oluşur:  
  
```  
// C2334.cpp  
// compile with: /c  
// C2059 expected  
struct s1 {  
   s1   {}   // C2334  
   s1() {}   // OK  
};  
```
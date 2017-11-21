---
title: "Derleyici Hatası C2047 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2047
dev_langs: C++
helpviewer_keywords: C2047
ms.assetid: 686a5a81-3857-4753-84a0-5c2e7149cbee
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a5b177e639599681f0ae62ebaa0bafb9f1e753a2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2047"></a>Derleyici Hatası C2047
Geçersiz varsayılan  
  
 Anahtar sözcüğü `default` yalnızca görünebilir bir `switch` deyimi.  
  
 Aşağıdaki örnek C2047 oluşturur:  
  
```  
// C2047.cpp  
int main() {  
   int i = 0;  
   default:   // C2047  
   switch(i) {  
      case 0:  
      break;  
   }  
}  
```  
  
 Olası çözüm:  
  
```  
// C2047b.cpp  
int main() {  
   int i = 0;  
   switch(i) {  
      case 0:  
      break;  
      default:  
      break;  
   }  
}  
```
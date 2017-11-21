---
title: "Derleyici Hatası C3484 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3484
dev_langs: C++
helpviewer_keywords: C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0ec019561a042b5dd5fd05aa8660bc8ff6b1d976
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3484"></a>Derleyici Hatası C3484
Beklenen 'dönüş türü önce ->'  
  
 Sağlamanız gereken `->` önce bir lambda ifadesi dönüş türü.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Sağlamak `->` önce dönüş türü.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3484 oluşturur:  
  
```  
// C3484a.cpp  
  
int main()  
{  
   return []() . int { return 42; }(); // C3484  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek sağlayarak C3484 çözümler `->` lambda ifadesi dönüş türü önce:  
  
```  
// C3484b.cpp  
  
int main()  
{  
   return []() -> int { return 42; }();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
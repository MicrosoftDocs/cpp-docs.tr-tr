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
ms.workload: cplusplus
ms.openlocfilehash: 0814bb2b6e12d51982975a4fea1914294ca01e69
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
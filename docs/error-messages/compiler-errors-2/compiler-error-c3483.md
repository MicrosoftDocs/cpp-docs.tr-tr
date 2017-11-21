---
title: "Derleyici Hatası C3483 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3483
dev_langs: C++
helpviewer_keywords: C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 145e0162c47b360b9d37cf95b108446f919435de
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3483"></a>Derleyici Hatası C3483
'var' zaten lambda yakalama listenin bir parçasıdır  
  
 Lambda ifadesi birden fazla kez yakalama listesine aynı değişken geçirildi.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Tüm ek örneklerini değişkeni yakalama listesinden kaldırır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3483 oluşturur çünkü değişkeni `n` lambda ifadesi yakalama listesinde birden fazla kez görüntülenir:  
  
```  
// C3483.cpp  
  
int main()  
{  
   int m = 6, n = 5;  
   [m,n,n] { return n + m; }(); // C3483  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
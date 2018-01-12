---
title: "Derleyici Hatası C3493 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3493
dev_langs: C++
helpviewer_keywords: C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8094b3b03f06dcc799b6bdfeea2b57399f92b852
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3493"></a>Derleyici Hatası C3493
hiçbir varsayılan yakalama modu belirtilmediğinden 'var' örtük olarak yakalanamazsa  
  
 Boş lambda ifadesi yakalama `[]`, lambda ifadesi açıkça yapacağını belirtir veya örtülü hiçbir değişken yakalama.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Varsayılan bir yakalama modu sağlamak veya  
  
-   Açıkça bir veya daha fazla değişken yakalayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çünkü bir dış değişken değiştirir ancak boş yakalama yan tümcesi belirtir C3493 oluşturur:  
  
```  
// C3493a.cpp  
  
int main()  
{  
   int m = 55;  
   [](int n) { m = n; }(99); // C3493  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, başvuru tarafından varsayılan yakalama modu olarak belirterek C3493 çözümler.  
  
```  
// C3493b.cpp  
  
int main()  
{  
   int m = 55;  
   [&](int n) { m = n; }(99);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
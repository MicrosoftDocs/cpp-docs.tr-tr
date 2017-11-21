---
title: "Derleyici Hatası C3496 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3496
dev_langs: C++
helpviewer_keywords: C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 86c80c4b708bd4315b2ce2ceaf7b61e0629a8b2e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3496"></a>Derleyici Hatası C3496
'this' değeri her zaman yakalanır: '&' yoksayıldı  
  
 Yakalama yapılamaz `this` başvuruya işaretçi.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Yakalama `this` değeriyle işaretçi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3496 oluşturur çünkü bir başvuru `this` işaretçi lambda ifadesi yakalama listede görünür:  
  
```  
// C3496.cpp  
// compile with: /c  
  
class C  
{  
   void f()  
   {  
      [&this] {}(); // C3496  
   }  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
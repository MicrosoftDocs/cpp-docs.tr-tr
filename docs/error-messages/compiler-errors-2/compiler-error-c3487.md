---
title: "Derleyici Hatası C3487 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3487
dev_langs: C++
helpviewer_keywords: C3487
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: eb659f2d7971d1dd2ff27c438839336d4744767e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3487"></a>Derleyici Hatası C3487
'dönüş türü': tüm dönüş ifadeler aynı türünü türetme gerekir: 'dönüş türü' öncekinden  
  
 Tek bir dönüş ifadesi içermediği sürece bir lambda dönüş türünü belirtmeniz gerekir. Bir lambda birden çok return deyimlerinde içeriyorsa, tüm aynı türde olmalıdır.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Lambda için sonunda bir dönüş türü belirtin. Lambda tüm döndürür aynı türde veya dönüş türü örtük olarak dönüştürülebilir doğrulayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, lambda dönüş türleri eşleşmediğinden C3487 oluşturur:  
  
```  
// C3487.cpp  
// Compile by using: cl /c /W4 C3487.cpp  
  
int* test(int* pi) {  
   // To fix the error, uncomment the trailing return type below  
   auto odd_pointer = [=]() /* -> int* */ {  
      if (*pi % 2)   
         return pi;  
      return nullptr; // C3487 - nullptr is not an int* type  
   };  
   return odd_pointer();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
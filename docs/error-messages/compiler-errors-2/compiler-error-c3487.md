---
title: Derleyici Hatası C3487 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3487
dev_langs:
- C++
helpviewer_keywords:
- C3487
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb30b9a2cb0b77eff0888da6c387bd3b06182721
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
 [Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
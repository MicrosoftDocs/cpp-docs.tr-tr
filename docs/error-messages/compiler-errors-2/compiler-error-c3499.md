---
title: Derleyici Hatası C3499 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3499
dev_langs:
- C++
helpviewer_keywords:
- C3499
ms.assetid: 6717de5c-ae0f-4024-bdf2-b5598009e7b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de299c5da66790276433da22227a3aa97cb55c82
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257464"
---
# <a name="compiler-error-c3499"></a>Derleyici Hatası C3499
dönüş türü void için belirtilen bir lambda bir değer döndüremiyor  
  
 Bu hata belirten bir lambda ifadesi zaman derleyici oluşturur `void` dönüş türü bir değer verir; ya da bir lambda ifadesi birden fazla deyim içeren ve bir değer döndürür, ancak kendi dönüş türü belirtmiyor.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Lambda ifadesinden bir değer döndürmeyen veya  
  
-   Lambda ifadesi dönüş türü sağlamak veya  
  
-   Tek bir deyimde lambda ifadesine gövdesini oluşturan deyimleri birleştirin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çünkü bir lambda ifadesi gövdesi bir değer döndürür ve birden çok deyime içerir, ancak lambda ifadesi dönüş türü belirtmiyor C3499 oluşturur:  
  
```  
// C3499a.cpp  
  
int main()  
{  
   [](int x) { int n = x * 2; return n; } (5); // C3499  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte iki olası çözümler için C3499 gösterir. İlk çözümleme lambda ifadesi dönüş türü sağlar. İkinci çözüm, tek bir deyimde lambda ifadesine gövdesini oluşturan deyimleri birleştirir.  
  
```  
// C3499b.cpp  
  
int main()  
{  
   // Possible resolution 1:   
   // Provide the return type of the lambda expression.  
   [](int x) -> int { int n = x * 2; return n; } (5);  
  
   // Possible resolution 2:   
   // Combine the statements that make up the body of   
   // the lambda expression into a single statement.  
   [](int x) { return x * 2; } (5);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
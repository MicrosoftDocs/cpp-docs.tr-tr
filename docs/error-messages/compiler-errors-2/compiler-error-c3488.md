---
title: "Derleyici Hatası C3488 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3488
dev_langs: C++
helpviewer_keywords: C3488
ms.assetid: 0a6fcd76-dd3b-48d7-abb3-22eccda96034
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5006ca7cb3477730a4234a8e058acdae520a59c8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3488"></a>Derleyici Hatası C3488
varsayılan yakalama modu başvuru tarafından olduğunda 'var' izin verilmiyor  
  
 Lambda ifadesi için varsayılan yakalama modu başvuru tarafından olduğunu belirttiğinizde yakalama yan tümcesi bu deyim için başvuruya göre bir değişken geçiremezsiniz.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Açıkça değişkeni yakalama yan tümcesini geçmeyin veya  
  
-   Başvuru tarafından varsayılan yakalama modu olarak belirtmeyin veya  
  
-   Varsayılan yakalama modu olarak tarafından değeri belirtin veya  
  
-   Değişken değeri tarafından yakalama yan tümcesine geçirin. (Bu lambda ifadesi davranışını değiştirebilirsiniz.)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3488 oluşturur çünkü değişkeni bir başvuru `n` , varsayılan mod budur başvuru tarafından lambda ifadesi yakalama yan tümcesinde görünür:  
  
```  
// C3488a.cpp  
  
int main()  
{  
   int n = 5;  
   [&, &n]() { return n; } (); // C3488  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, dört olası çözümler için C3488 gösterir:  
  
```  
// C3488b.cpp  
  
int main()  
{  
   int n = 5;  
  
   // Possible resolution 1:  
   // Do not explicitly pass &n to the capture clause.  
   [&]() { return n; } ();  
  
   // Possible resolution 2:  
   // Do not specify by-reference as the default capture mode.  
   [&n]() { return n; } ();  
  
   // Possible resolution 3:  
   // Specify by-value as the default capture mode.  
   [=, &n]() { return n; } ();  
  
   // Possible resolution 4:  
   // Pass n by value to the capture clause.  
   [n]() { return n; } ();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
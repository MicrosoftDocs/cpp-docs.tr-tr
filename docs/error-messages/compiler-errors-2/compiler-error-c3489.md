---
title: "Derleyici Hatası C3489 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3489
dev_langs: C++
helpviewer_keywords: C3489
ms.assetid: 47b58d69-459d-4499-abc7-5f0b9303d773
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b4a0115bbb6d00a4e83d0ae3343b1af1b8024002
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3489"></a>Derleyici Hatası C3489
varsayılan yakalama modu değeri tarafından olduğunda 'var' gereklidir  
  
 Lambda ifadesi için varsayılan yakalama modu değeri tarafından olduğunu belirttiğinizde, bir değişken değerle ifade yakalama yan tümcesine geçiremezsiniz.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Açıkça değişkeni yakalama yan tümcesini geçmeyin veya  
  
-   Değer tarafından varsayılan yakalama modu olarak belirtmeyin veya  
  
-   Varsayılan yakalama modu olarak başvuru tarafından belirtin veya  
  
-   Yakalama yan tümcesine başvuruya değişkeni geçirin. (Bu lambda ifadesi davranışını değiştirebilirsiniz.)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3489 değişkeni oluşturan `n` , varsayılan mod budur değeri tarafından lambda ifadesi yakalama yan tümcesindeki değer görüntülenir:  
  
```  
// C3489a.cpp  
  
int main()  
{  
   int n = 5;  
   [=, n]() { return n; } (); // C3489  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, dört olası çözümler için C3489 gösterir:  
  
```  
// C3489b.cpp  
  
int main()  
{  
   int n = 5;  
  
   // Possible resolution 1:  
   // Do not explicitly pass n to the capture clause.  
   [=]() { return n; } ();  
  
   // Possible resolution 2:  
   // Do not specify by-value as the default capture mode.  
   [n]() { return n; } ();  
  
   // Possible resolution 3:  
   // Specify by-reference as the default capture mode.  
   [&, n]() { return n; } ();  
  
   // Possible resolution 4:  
   // Pass n by reference to the capture clause.  
   [&n]() { return n; } ();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
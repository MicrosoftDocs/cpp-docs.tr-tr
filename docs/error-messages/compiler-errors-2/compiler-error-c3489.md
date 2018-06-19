---
title: Derleyici Hatası C3489 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3489
dev_langs:
- C++
helpviewer_keywords:
- C3489
ms.assetid: 47b58d69-459d-4499-abc7-5f0b9303d773
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd620c969f89b1889384fe3f4d7f899957ae620b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253324"
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
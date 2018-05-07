---
title: Derleyici Hatası C3482 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3482
dev_langs:
- C++
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad7ea983d13f03add2772da173062b1ad5652d3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3482"></a>Derleyici Hatası C3482
'this' statik olmayan üye fonksiyonu içinde lambda yakalama olarak yalnızca kullanılabilir  
  
 Geçiremezsiniz `this` bir statik yöntem veya genel işlevinde bildirilmiş bir lambda ifadesi yakalama listesi.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Statik olmayan yönteme kapsayan işlevi Dönüştür veya  
  
-   Kaldırma `this` lambda ifadesi yakalama listesi işaretçi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3482 oluşturur:  
  
```  
// C3482.cpp  
// compile with: /c  
  
class C  
{  
public:  
   static void staticMethod()  
   {  
      [this] {}(); // C3482  
   }  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)
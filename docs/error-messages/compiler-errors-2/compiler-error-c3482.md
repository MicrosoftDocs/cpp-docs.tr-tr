---
title: "Derleyici Hatası C3482 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3482
dev_langs: C++
helpviewer_keywords: C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b19769a8a326613401263fa7700b85c36a9dbbe1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
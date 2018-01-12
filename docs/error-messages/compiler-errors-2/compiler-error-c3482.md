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
ms.workload: cplusplus
ms.openlocfilehash: 4ff7a17d663be7168c5743838d782043d7c0ee92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
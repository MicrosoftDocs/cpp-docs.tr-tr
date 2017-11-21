---
title: "Derleyici Uyarısı (düzey 4) C4714 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4714
dev_langs: C++
helpviewer_keywords: C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c9cf416dd3bff91e8adf8e3f31e9b23b465706c9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4714"></a>Derleyici Uyarısı (düzey 4) C4714
İşlev 'function' __forceinline içermesinden işaretlenmemiş  
  
 Verilen işlevi için satır içi genişletme seçildi, ancak derleyici kullanılmayacak satır içi kullanım.  
  
 Rağmen `__forceinline` derleyici daha güçlü bir göstergesidir `__inline`, satır içi kullanım derleyicinin istediğiniz kadar hala gerçekleştirilir, ancak hiçbir buluşsal yöntemler gelen avantajları belirlemek için kullanılan satır içi kullanım bu işlev.  
  
 Bazı durumlarda, derleyici olacak hizalı değil belirli bir işlev mekanik nedenleri. Örneğin, derleyici, hizalı değil olur:  
  
-   SEH ve C++ EH karıştırma sonuçlandığında bir işlev.  
  
-   Bazı işlevler kopyayla EHs / - GX/EHa açık olduğunda değeri tarafından geçirilen nesneleri oluşturulur.  
  
-   -GX/EHs/EHa açık olduğunda unwindable bir nesne değeri döndüren işlevler.  
  
-   Og/Ox/O1/O2 olmadan - derlerken satır içi derlemeyle işlevler.  
  
-   Bir değişken bağımsız değişken listesiyle birlikte çalışır.  
  
-   İşlevi ile bir **deneyin** (C++ özel durum işleme) ifadesi.  
  
 Aşağıdaki örnek C4714 oluşturur:  
  
```  
// C4714.cpp  
// compile with: /Ob1 /GX /W4  
__forceinline void func1()  
{  
   try  
   {  
   }  
   catch (...)  
   {  
   }  
}  
  
void func2()  
{  
   func1();   // C4714  
}  
  
int main()  
{  
}  
```
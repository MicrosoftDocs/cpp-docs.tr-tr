---
title: Derleyici Uyarısı (düzey 4) C4714 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4714
dev_langs:
- C++
helpviewer_keywords:
- C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0f327e7ffc5d2fe00abe3c0845af10a846243bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33295424"
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
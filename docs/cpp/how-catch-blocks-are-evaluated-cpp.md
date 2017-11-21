---
title: "Catch blokları nasıl değerlendirilir (C++)? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- try-catch keyword [C++], catchable types
- catch keyword [C++], types of catch handlers
- C++ exception handling, catch handlers
- exception handling, catching and deleting exceptions
- types [C++], exception handling
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3af6c63ab571738f2c963c3e9b90b9aae4b644eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-catch-blocks-are-evaluated-c"></a>Catch Blokları Nasıl Değerlendirilir (C++)
Genel olarak std::exception'dan türetilen türler oluşturulması önerilse de, C++ her türden özel durumlar oluşturmanıza olanak tanır. C++ özel durum tarafından yakalanan bir **catch** oluşturulan özel durum olarak ya da herhangi bir özel durum türü yakalayabilir bir işleyici tarafından aynı türde belirtir işleyici.  
  
 Oluşturulan özel durumun türü temel sınıfı (veya sınıfları) da olan bir sınıfsa, özel durum türünün temel sınıflarını kabul eden işleyiciler ve özel durum türünün başvuruları tarafından yakalanabilir. Özel durum bir başvuru tarafından yakalandığında oluşturulan gerçek özel durum nesnesine bağlanır; aksi takdirde bir kopya (işlevin bağımsız değişkeniyle hemen hemen aynı) olur.  
  
 Bir özel durum olduğunda, aşağıdaki türden tarafından yakalanan **catch** işleyicileri:  
  
-   Herhangi bir türü kabul edebilen bir işleyici (üç nokta sözdizimini kullanarak).  
  
-   Özel durum nesnesi aynı türü kabul eden bir işleyici; bir kopya olduğundan **const** ve `volatile` değiştiricileri yok sayılır.  
  
-   Özel durum nesnesiyle aynı türe yapılan başvuruyu kabul eden bir işleyici.  
  
-   Bir başvuru kabul eden bir işleyici bir **const** veya `volatile` form özel durum nesnesi ile aynı türde.  
  
-   Özel durum nesnesi ile aynı türde bir taban sınıf kabul işleyicisi; bir kopya olduğundan **const** ve `volatile` değiştiricileri yok sayılır. **Catch** bir taban sınıfı için işleyici değil gelmelidir **catch** türetilmiş bir sınıf için işleyici.  
  
-   Özel durum nesnesiyle aynı türden temel sınıf başvurusunu kabul eden bir işleyici.  
  
-   Bir başvuru kabul eden bir işleyici bir **const** veya `volatile` özel durum nesnesi ile aynı türde bir taban sınıfın formu.  
  
-   Oluşturulan bir işaretçi nesnesinin standart işaretçi dönüştürme kurallarıyla dönüştürülebileceği bir işaretçiyi kabul eden bir işleyici.  
  
 Hangi sırayla **catch** işleyicileri görünür olan önemli, çünkü işleyicileri için bir verilen **deneyin** blok görünümlerini sırayla inceledi. Örneğin, temel sınıfa yönelik bir işleyicisi türetilmiş sınıfa yönelik bir işleyiciden önce yerleştirmek hatadır. Eşleşen bir sonra **catch** işleyici bulunduğunda, sonraki işleyicileri incelenmesini değil. Sonuç olarak, bir üç nokta **catch** işleyici son işleyicisi olmalıdır, **deneyin** bloğu. Örneğin:  
  
```  
// ...  
try  
{  
    // ...  
}  
catch( ... )  
{  
    // Handle exception here.  
}  
// Error: the next two handlers are never examined.  
catch( const char * str )  
{  
    cout << "Caught exception: " << str << endl;  
}  
catch( CExcptClass E )  
{  
    // Handle CExcptClass exception here.  
}  
```  
  
 Bu örnekte, üç nokta **catch** işleyicisidir incelenir yalnızca işleyici.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ özel durum işleme](../cpp/cpp-exception-handling.md)
---
title: Catch blokları nasıl değerlendirilir (C++)? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- try-catch keyword [C++], catchable types
- catch keyword [C++], types of catch handlers
- C++ exception handling, catch handlers
- exception handling, catching and deleting exceptions
- types [C++], exception handling
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6343abec7e80bcbc47595856e6fd71a3e204ed54
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [C++ Özel Durum İşleme](../cpp/cpp-exception-handling.md)
---
title: Catch blokları değerlendirilir (C++) şeklini | Microsoft Docs
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
ms.openlocfilehash: 0190b62491dbb9d15ee4f01a1cbc4c2741f74dbe
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948207"
---
# <a name="how-catch-blocks-are-evaluated-c"></a>Catch Blokları Nasıl Değerlendirilir (C++)
Genel olarak std::exception'dan türetilen türler oluşturulması önerilse de, C++ her türden özel durumlar oluşturmanıza olanak tanır. Bir C++ özel durum tarafından yakalanabilir bir **catch** oluşan özel durum olarak veya her türden özel durumu yakalamak bir işleyici tarafından aynı türü belirten bir işleyici.  
  
 Oluşturulan özel durumun türü temel sınıfı (veya sınıfları) da olan bir sınıfsa, özel durum türünün temel sınıflarını kabul eden işleyiciler ve özel durum türünün başvuruları tarafından yakalanabilir. Özel durum bir başvuru tarafından yakalandığında oluşturulan gerçek özel durum nesnesine bağlanır; aksi takdirde bir kopya (işlevin bağımsız değişkeniyle hemen hemen aynı) olur.  
  
 Bir özel durum oluştuğunda, bunu aşağıdaki türleri tarafından yakalanabilirler **catch** işleyiciler:  
  
-   Herhangi bir türü kabul edebilen bir işleyici (üç nokta sözdizimini kullanarak).  
  
-   Özel durum nesnesiyle aynı türü kabul eden bir işleyici; bir kopya olduğundan **const** ve **geçici** değiştiricileri yoksayılır.  
  
-   Özel durum nesnesiyle aynı türe yapılan başvuruyu kabul eden bir işleyici.  
  
-   Bir başvuruyu kabul eden bir işleyici bir **const** veya **geçici** özel durum nesnesiyle aynı türden formu.  
  
-   Özel durum nesnesiyle aynı türden temel sınıf kabul eden bir işleyici; bir kopya olduğundan **const** ve **geçici** değiştiricileri yoksayılır. **Catch** bir temel sınıf için işleyici gelmemelidir **catch** türetilmiş sınıf için işleyici.  
  
-   Özel durum nesnesiyle aynı türden temel sınıf başvurusunu kabul eden bir işleyici.  
  
-   Bir başvuruyu kabul eden bir işleyici bir **const** veya **geçici** biçiminin özel durum nesnesiyle aynı türden temel sınıf.  
  
-   Oluşturulan bir işaretçi nesnesinin standart işaretçi dönüştürme kurallarıyla dönüştürülebileceği bir işaretçiyi kabul eden bir işleyici.  
  
 Bir sırayı **catch** işleyicilerinin görünme önemlidir; çünkü işleyicileri için bir verilen **deneyin** blok, görünme sırasına göre incelenir. Örneğin, temel sınıfa yönelik bir işleyicisi türetilmiş sınıfa yönelik bir işleyiciden önce yerleştirmek hatadır. Eşleşen bir sonra **catch** işleyicisi bulunursa, sonraki işleyiciler incelenmez. Sonuç olarak, üç nokta **catch** son işleyicisi olmalıdır, **deneyin** blok. Örneğin:  
  
```cpp 
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
  
 Bu örnekte, üç nokta **catch** işleyicisidir incelenen tek işleyicidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Özel Durum İşleme](../cpp/cpp-exception-handling.md)
---
title: "Özyinelemeli İşlevler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- functions [C], recursive
- function calls, recursive
- functions [C], calling recursively
- recursive function calls
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fcbe38eb67a31f6bb62750b44df57aa9d64b9272
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="recursive-functions"></a>Özyinelemeli İşlevler
C programındaki herhangi bir işlev özyinelemeli olarak çağrılabilir; diğer bir deyişle, kendisini çağırabilir. Özyinelemeli çağrıların sayısı, yığının boyutuyla sınırlıdır. Bkz: [/STACK (yığın ayırmaları)](../build/reference/stack-stack-allocations.md) (/ yığın) bağlayıcı hakkında bilgi için bağlayıcı seçeneği seçenekleri yığın boyutunu Ayarla. İşlevi çağrıldığında, her seferinde yeni bir depolama birimi ve parametreleri için ayrılan **otomatik** ve **kaydetmek** değişkenleri böylece önceki, tamamlanmamış çağrıları değerleri geçersiz kılınmaz. Parametrelere, yalnızca oluşturuldukları işlevin örneği doğrudan erişebilir. Önceki parametrelere, işlevin sonraki örnekleri tarafından doğrudan erişilemez.  
  
 Değişkenleri ile bildirilen Not **statik** depolama her özyinelemeli çağrısı ile yeni bir depolama birimi gerektirmez. Depolama alanları, programın ömrü boyunca kullanılır. Böyle bir değişkene yapılan her başvuru aynı depolama alanına erişir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, özyinelemeli aramalar gösterilmektedir:  
  
```  
int factorial( int num );      /* Function prototype */  
  
int main()  
{  
    int result, number;  
    .  
    .  
    .  
    result = factorial( number );  
}  
  
int factorial( int num )      /* Function definition */  
{  
    .  
    .  
    .  
    if ( ( num > 0 ) || ( num <= 10 ) )  
        return( num * factorial( num - 1 ) );  
}  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlev Çağrıları](../c-language/function-calls.md)
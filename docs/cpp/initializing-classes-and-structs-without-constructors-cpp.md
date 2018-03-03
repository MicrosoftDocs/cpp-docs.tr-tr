---
title: "Sınıfları ve yapıları oluşturucular (C++) olmadan başlatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c65bc0adb32d61cef76e02aa944826eaf866c7c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-classes-and-structs-without-constructors-c"></a>Sınıfları ve yapıları oluşturucular olmadan başlatma (C++)
Her zaman için bir sınıf, nispeten basit olanları özellikle bir oluşturucu tanımlamak gerekli değildir. Kullanıcılar nesnelerin sınıfta veya yapı tek düzen başlatma kullanarak aşağıdaki örnekte gösterildiği gibi başlatabilirsiniz:  
  
```  
#include "stdafx.h"  
#include <Windows.h>  
  
// No constructor  
struct TempData  
{  
    int StationId;  
    time_t time;  
    double current;  
    double maxTemp;  
    double minTemp;  
};  
  
// Has a constructor  
struct TempData2  
{  
    TempData2(double minimum, double maximum, double cur, int id, time_t t) :  
       minTemp(minimum), maxTemp(maximum), current(cur), stationId(id), time(t) {}  
    int stationId;  
    time_t time;  
    double current;  
    double maxTemp;  
    double minTemp;  
};  
  
int main()  
{  
    // Member initialization (in order of declaration):  
    TempData td{ 45978, GetCurrentTime(), 28.9, 37.0, 16.7 };  
  
    // Default initialization = {0,0,0,0,0}  
    TempData td_default{};  
  
    //Error C4700 uninitialized local variable  
    TempData td_noInit;  
  
    // Member declaration (in order of ctor parameters)  
    TempData2 td2{ 16.7, 37.0, 28.9, 45978, GetCurrentTime() };  
  
    return 0;  
}  
  
```  
  
 Sınıfta veya yapı oluşturucu yok olduğunda, liste öğelerini üyeler sınıfta bildirilir sırayla sağladığını unutmayın. Sınıfın bir oluşturucu varsa, parametreleri sırasına göre öğeleri sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar ve yapılar](../cpp/classes-and-structs-cpp.md)   
 [Oluşturucular](../cpp/constructors-cpp.md)
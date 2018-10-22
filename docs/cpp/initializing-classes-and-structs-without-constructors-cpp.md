---
title: Sınıfları ve yapıları oluşturucular (C++) olmadan başlatma | Microsoft Docs
ms.custom: ''
ms.date: 10/17/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb72bf8c8550d87a4e6bf86e440c7a468f4f878d
ms.sourcegitcommit: f9d9db80a8f13eae2c41337b974e1298109e33c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2018
ms.locfileid: "49640766"
---
# <a name="initializing-classes-and-structs-without-constructors-c"></a>Sınıfları ve yapıları oluşturucular olmadan başlatma (C++)

Her zaman için bir sınıf, görece basit olanları özellikle bir kurucu tanımlamak gerekli değildir. Kullanıcılar bir sınıf veya yapı nesneleri Tekdüzen başlatma kullanarak aşağıdaki örnekte gösterildiği gibi başlatabilirsiniz:

```cpp
// no_constructor.cpp
// Compile with: cl /EHsc no_constructor.cpp
#include <time.h>

// No constructor
struct TempData
{
    int StationId;
    time_t timeSet;
    double current;
    double maxTemp;
    double minTemp;
};

// Has a constructor
struct TempData2
{
    TempData2(double minimum, double maximum, double cur, int id, time_t t) :
       stationId{id}, timeSet{t}, current{cur}, maxTemp{maximum}, minTemp{minimum} {}
    int stationId;
    time_t timeSet;
    double current;
    double maxTemp;
    double minTemp;
};

int main()
{
    time_t time_to_set;

    // Member initialization (in order of declaration):
    TempData td{ 45978, time(&time_to_set), 28.9, 37.0, 16.7 };

    // Default initialization = {0,0,0,0,0}
    TempData td_default{};

    // Uninitialized = if used, emits warning C4700 uninitialized local variable
    TempData td_noInit;

    // Member declaration (in order of ctor parameters)
    TempData2 td2{ 16.7, 37.0, 28.9, 45978, time(&time_to_set) };

    return 0;
}
```

Bir sınıf veya yapı, hiçbir oluşturucu sahip olduğunda liste öğeleri üyeler sınıfta bildirilir sırayla sağladığını unutmayın. Sınıfın Oluşturucusu varsa, parametrelerin sırasına göre öğeleri sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)<br/>
[Oluşturucular](../cpp/constructors-cpp.md)

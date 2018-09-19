---
title: Sınıfları ve yapıları oluşturucular (C++) olmadan başlatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: c9cf80b9b1a6a7002e4176720cf12b305592c6fb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117523"
---
# <a name="initializing-classes-and-structs-without-constructors-c"></a>Sınıfları ve yapıları oluşturucular olmadan başlatma (C++)

Her zaman için bir sınıf, görece basit olanları özellikle bir kurucu tanımlamak gerekli değildir. Kullanıcılar bir sınıf veya yapı nesneleri Tekdüzen başlatma kullanarak aşağıdaki örnekte gösterildiği gibi başlatabilirsiniz:

```cpp
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

Bir sınıf veya yapı, hiçbir oluşturucu sahip olduğunda liste öğeleri üyeler sınıfta bildirilir sırayla sağladığını unutmayın. Sınıfın Oluşturucusu varsa, parametrelerin sırasına göre öğeleri sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)<br/>
[Oluşturucular](../cpp/constructors-cpp.md)
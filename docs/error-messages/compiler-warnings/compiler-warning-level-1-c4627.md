---
title: Derleyici Uyarısı (düzey 1) C4627
ms.date: 09/09/2018
f1_keywords:
- C4627
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
ms.openlocfilehash: e833141020de1aef51a1ea3823dea86b024e077d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542395"
---
# <a name="compiler-warning-level-1-c4627"></a>Derleyici Uyarısı (düzey 1) C4627

> '*header_fıle*': Ön derlenmiş üstbilgi kullanımı aranırken atlandı

Geçerli kaynak dosyanın varsa [/Yu \(kullanım önceden derlenmiş üst bilgi dosyası)](../../build/reference/yu-use-precompiled-header-file.md) seçenek kümesi, ardından önceden derlenmiş üst bilgi eklenir önce derleyici dosyadaki her şeyi yoksayar. Uyarı **C4627** , Visual Studio 2015 veya önceki sürümlerinde oluşturulan *header_fıle* önce önceden derlenmiş üst bilgi dosyasını dahil ve önceden derlenmiş üst bilgi de içermiyorsa*header_fıle*.

## <a name="example"></a>Örnek

Bu örnek nasıl hata ortaya çıkabilir ve nasıl düzeltileceğini gösteren gösterir:

```cpp
// c4627.cpp
#include <iostream>       // C4627 - iostream not included by pch.h
#include "pch.h"          // precompiled header file that does not include iostream
// #include <iostream>    // To fix, move the iostream header include here from above
int main()
{
    std::cout << "std::cout is defined!\n";
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Önceden Derlenmiş Üst Bilgi Dosyaları Oluşturma](../../build/reference/creating-precompiled-header-files.md)

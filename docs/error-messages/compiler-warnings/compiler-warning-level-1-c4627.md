---
title: Derleyici Uyarısı (düzey 1) C4627
ms.date: 09/09/2018
f1_keywords:
- C4627
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
ms.openlocfilehash: 06db3d7e585dfe49b2e0854973f63834648613b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221384"
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

## <a name="see-also"></a>Ayrıca bkz.

[Önceden Derlenmiş Üst Bilgi Dosyaları Oluşturma](../../build/creating-precompiled-header-files.md)

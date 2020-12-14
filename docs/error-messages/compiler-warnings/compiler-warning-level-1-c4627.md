---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4627'
title: Derleyici Uyarısı (düzey 1) C4627
ms.date: 09/09/2018
f1_keywords:
- C4627
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
ms.openlocfilehash: fc4c6c3931775b090dfd4c7c2fd5fd97441d40d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281450"
---
# <a name="compiler-warning-level-1-c4627"></a>Derleyici Uyarısı (düzey 1) C4627

> '*header_file*': ön derlenmiş üstbilgi kullanımı aranırken atlandı

Geçerli kaynak dosyasında [/yu \( ön derlenmiş üstbilgi dosyası kullan)](../../build/reference/yu-use-precompiled-header-file.md) seçenek ayarlandıysa, ön derlenmiş üstbilgi dahil etmeden önce derleyici dosyadaki her şeyi yoksayar. Uyarı **C4627** , önceden derlenmiş üstbilgi dosyasından önce *header_file* varsa ve önceden derlenmiş üst bilgi de *header_file* içermiyorsa, Visual Studio 2015 ve önceki sürümlerde uyarı oluşturulur.

## <a name="example"></a>Örnek

Bu örnek, hatanın nasıl gerçekleşebileceğini ve nasıl düzeltileceğini gösterir:

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

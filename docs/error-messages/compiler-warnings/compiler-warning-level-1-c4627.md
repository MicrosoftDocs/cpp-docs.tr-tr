---
title: Derleyici Uyarısı (düzey 1) C4627 | Microsoft Docs
ms.custom: ''
ms.date: 09/09/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4627
dev_langs:
- C++
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fef8d0ab55205d2377fc52049c40a1c50151b93e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024183"
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

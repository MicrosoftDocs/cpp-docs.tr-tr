---
title: Sonlandırma işleyicileri kısıtlamaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f35560c6f29e341b05f6b8bdf22873847644d7c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="restrictions-on-termination-handlers"></a>Sonlandırma İşleyicileri Kısıtlamaları
Kullanamazsınız bir `goto` içine atlamak için deyimi bir `__try` deyimi blok veya `__finally` deyimi bloğu. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. (Dışı ancak atlamak bir `__try` deyimi blok.) Ayrıca, bir özel durum işleyici veya sonlandırma işleyicisi içinde iç içe yerleştirilemez bir `__finally` bloğu.  
  
 Ayrıca, dikkatli olun, varsa kullanmanız gerektiği şekilde bir sonlandırma işleyicisi izin kodu bazı tür şüpheli sonuçlara yol. Biridir bir `goto` dışı atlar deyimi bir `__finally` deyimi bloğu. Blok normal sonlandırma bir parçası olarak yürütülen olağan dışı bir şey olur. Olağan dışı bir sonlandırma değilmiş gibi ancak sistem unwinding durdurur ve geçerli işlevi kazanır yığını, geriye doğru izleme olup olmadığını denetler.  
  
 A `return` deyimi içinde bir `__finally` deyimi blok de aynı durum kabaca gösterir. Sonlandırma işleyicisi içeren işlevi anında arayanlar için denetimini döndürür. Sistem yığını geriye doğru izleme oluştu, bu işlem durdurulur ve şekilde geliştirilmişse özel durum oluştu program devam eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)   
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
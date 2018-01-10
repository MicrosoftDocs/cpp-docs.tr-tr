---
title: "Sonlandırma işleyicileri kısıtlamaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 71486b167f4e9939d4913b3660ed3513dc02b8f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="restrictions-on-termination-handlers"></a>Sonlandırma İşleyicileri Kısıtlamaları
Kullanamazsınız bir `goto` içine atlamak için deyimi bir `__try` deyimi blok veya `__finally` deyimi bloğu. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. (Dışı ancak atlamak bir `__try` deyimi blok.) Ayrıca, bir özel durum işleyici veya sonlandırma işleyicisi içinde iç içe yerleştirilemez bir `__finally` bloğu.  
  
 Ayrıca, dikkatli olun, varsa kullanmanız gerektiği şekilde bir sonlandırma işleyicisi izin kodu bazı tür şüpheli sonuçlara yol. Biridir bir `goto` dışı atlar deyimi bir `__finally` deyimi bloğu. Blok normal sonlandırma bir parçası olarak yürütülen olağan dışı bir şey olur. Olağan dışı bir sonlandırma değilmiş gibi ancak sistem unwinding durdurur ve geçerli işlevi kazanır yığını, geriye doğru izleme olup olmadığını denetler.  
  
 A `return` deyimi içinde bir `__finally` deyimi blok de aynı durum kabaca gösterir. Sonlandırma işleyicisi içeren işlevi anında arayanlar için denetimini döndürür. Sistem yığını geriye doğru izleme oluştu, bu işlem durdurulur ve şekilde geliştirilmişse özel durum oluştu program devam eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)   
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
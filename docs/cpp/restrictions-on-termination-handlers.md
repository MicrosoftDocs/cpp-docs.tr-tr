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
ms.openlocfilehash: 969930c3918cdc0d2e38747796279c7135aba5a7
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941346"
---
# <a name="restrictions-on-termination-handlers"></a>Sonlandırma İşleyicileri Kısıtlamaları
Kullanamazsınız bir **goto** bloğuna atlamak için bir **__try** deyim bloğunu veya **__finally** deyim bloğu. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. (Bununla birlikte, / hızlı bir **__try** deyim bloğunu.) Ayrıca, bir özel durum işleyicisi veya sonlandırma işleyicisi içine yerleştiremezsiniz bir **__finally** blok.  
  
 Ayrıca, dikkatle varsa kullanmanız gerektiği şekilde bir sonlandırma işleyicisi izin verilen kod bazı türleri tartışmalı sonuçları üretir. Biri bir **goto** tanesi atlar deyimi bir **__finally** deyim bloğu. Bloğun sonlandırma normal bir parçası olarak yürütülüyorsa, olağan dışı hiçbir şey olmaz. Olağan dışı sonlandırma gerçekleşmez değilmiş gibi ancak sistem geriye doğru izleme durur ve geçerli işlevin kazanır yığını geriye doğru olmadığını denetler.  
  
 A **dönüş** deyimi içinde bir **__finally** deyim bloğunu aynı durum kabaca sunar. Sonlandırma işleyicisi içeren işlev şu anki çağırıcı için denetimini döndürür. Sistem yığın geriye doğru Bu işlem durdurulur ve şekilde geliştirilmişse harekete geçirilen özel durum programın devam eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)   
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
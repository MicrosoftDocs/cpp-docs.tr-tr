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
ms.openlocfilehash: 3ae16363956afc7cca853307ef2888846a02864d
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461776"
---
# <a name="restrictions-on-termination-handlers"></a>Sonlandırma İşleyicileri Kısıtlamaları
Kullanamazsınız bir **goto** bloğuna atlamak için bir **__try** deyim bloğunu veya **__finally** deyim bloğu. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. (Bununla birlikte, / hızlı bir **__try** deyim bloğunu.) Ayrıca, bir özel durum işleyicisi veya sonlandırma işleyicisi içine yerleştiremezsiniz bir **__finally** blok.  
  
 Ayrıca, dikkatle varsa kullanmanız gerektiği şekilde bir sonlandırma işleyicisi izin verilen kod bazı türleri tartışmalı sonuçları üretir. Biri bir **goto** tanesi atlar deyimi bir **__finally** deyim bloğu. Bloğun sonlandırma normal bir parçası olarak yürütülüyorsa, olağan dışı hiçbir şey olmaz. Olağan dışı sonlandırma gerçekleşmez değilmiş gibi ancak sistem geriye doğru izleme durur ve geçerli işlevin kazanır yığını geriye doğru olmadığını denetler.  
  
 A **dönüş** deyimi içinde bir **__finally** deyim bloğunu aynı durum kabaca sunar. Sonlandırma işleyicisi içeren işlev şu anki çağırıcı için denetimini döndürür. Sistem yığın geriye doğru Bu işlem durdurulur ve şekilde geliştirilmişse harekete geçirilen özel durum programın devam eder.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)   
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
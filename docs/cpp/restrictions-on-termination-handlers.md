---
title: Sonlandırma İşleyicileri Kısıtlamaları
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
ms.openlocfilehash: befe181a41ed418a4a824b131e741a9f02f90e38
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179074"
---
# <a name="restrictions-on-termination-handlers"></a>Sonlandırma İşleyicileri Kısıtlamaları

Bir **__try** deyim bloğuna veya bir **__finally** deyim bloğuna geçmek için **goto** ifadesini kullanamazsınız. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. (Ancak, **__try** deyim bloğundan atlayabilirsiniz.) Ayrıca, bir özel durum işleyicisini veya sonlandırma işleyicisini **__finally** bloğu içinde iç içe geçirilemez.

Ayrıca, sonlandırma işleyicisinde izin verilen bazı kod türleri şüpheli sonuçlar üretir. bu nedenle, hepsi de varsa dikkatli bir şekilde kullanmalısınız. Bunlardan biri, **__finally** bildiri bloğundan atlayan bir **goto** deyimidir. Blok, normal sonlandırmanın bir parçası olarak yürütülerek hiçbir şey olağan dışı olur. Ancak sistem, yığını geri taşırsa, geriye doğru izleme işlemi geri alınmaz ve geçerli işlev olağan dışı sonlandırma olmasa da denetimi kazanır.

**__Finally** bildiri bloğu içindeki bir **Return** ifadesinde kabaca aynı durum sunulmaktadır. Denetim, sonlandırma işleyicisini içeren işlevin hemen çağırana döner. Sistem yığını geri taşıdıysa, bu işlem durdurulur ve program bir özel durum oluşmamış gibi devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)

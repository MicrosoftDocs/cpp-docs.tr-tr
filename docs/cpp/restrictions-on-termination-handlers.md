---
title: Sonlandırma İşleyicileri Kısıtlamaları
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
ms.openlocfilehash: 6c39407270037756c55dc42aed80e1d04616c9ee
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246379"
---
# <a name="restrictions-on-termination-handlers"></a>Sonlandırma İşleyicileri Kısıtlamaları

Bir **__try** deyim bloğuna veya bir **__finally** deyim bloğuna geçmek için **goto** ifadesini kullanamazsınız. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. (Ancak, **__try** deyim bloğundan atlayabilirsiniz.) Ayrıca, bir özel durum işleyicisini veya sonlandırma işleyicisini **__finally** bloğu içinde iç içe geçirilemez.

Ayrıca, sonlandırma işleyicisinde izin verilen bazı kod türleri şüpheli sonuçlar üretir. bu nedenle, hepsi de varsa dikkatli bir şekilde kullanmalısınız. Bunlardan biri, **__finally** bildiri bloğundan atlayan bir **goto** deyimidir. Blok, normal sonlandırmanın bir parçası olarak yürütülerek hiçbir şey olağan dışı olur. Ancak sistem, yığını geri taşırsa, geriye doğru izleme işlemi geri alınmaz ve geçerli işlev olağan dışı sonlandırma olmasa da denetimi kazanır.

**__Finally** bildiri bloğu içindeki bir **Return** ifadesinde kabaca aynı durum sunulmaktadır. Denetim, sonlandırma işleyicisini içeren işlevin hemen çağırana döner. Sistem yığını geri taşıdıysa, bu işlem durdurulur ve program bir özel durum oluşmamış gibi devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
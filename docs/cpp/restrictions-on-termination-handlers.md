---
title: Sonlandırma İşleyicileri Kısıtlamaları
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
ms.openlocfilehash: d53792afbc3d25fb21edafa7817919b63b79ab65
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225897"
---
# <a name="restrictions-on-termination-handlers"></a>Sonlandırma İşleyicileri Kısıtlamaları

Bir **`goto`** **__try** deyim bloğuna veya deyim bloğuna geçmek için deyim kullanamazsınız **`__finally`** . Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. (Ancak, **__try** deyim bloğundan atlayabilirsiniz.) Ayrıca, bir özel durum işleyicisini veya sonlandırma işleyicisini bir blok içinde iç içe geçirilemez **`__finally`** .

Ayrıca, sonlandırma işleyicisinde izin verilen bazı kod türleri şüpheli sonuçlar üretir. bu nedenle, hepsi de varsa dikkatli bir şekilde kullanmalısınız. Bunlardan biri, **`goto`** bir ekstre bloğunun dışına atlayan bir ifadedir **`__finally`** . Blok, normal sonlandırmanın bir parçası olarak yürütülerek hiçbir şey olağan dışı olur. Ancak sistem, yığını geri taşırsa, geriye doğru izleme işlemi geri alınmaz ve geçerli işlev olağan dışı sonlandırma olmasa da denetimi kazanır.

**`return`** Bir ifade bloğu içindeki bir ifade **`__finally`** kabaca aynı durumu gösterir. Denetim, sonlandırma işleyicisini içeren işlevin hemen çağırana döner. Sistem yığını geri taşıdıysa, bu işlem durdurulur ve program bir özel durum oluşmamış gibi devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)

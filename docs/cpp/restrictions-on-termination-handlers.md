---
title: Sonlandırma işleyicileri kısıtlamaları
description: Yapılandırılmış özel durum işleme sonlandırma işleyicileriyle ilgili kısıtlamalar.
ms.date: 08/24/2020
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
ms.openlocfilehash: 60fdb4c2a105f2fce4a32f475563a04f8e7bfaf9
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898266"
---
# <a name="restrictions-on-termination-handlers"></a>Sonlandırma İşleyicileri Kısıtlamaları

Deyim **`goto`** **`__try`** bloğunu veya deyim bloğunu atlayabilmeniz için bir deyim kullanamazsınız **`__finally`** . Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. (Ancak, bir **`__try`** deyim bloğunun dışına atlayabilirsiniz.) Ayrıca, bir özel durum işleyicisini veya sonlandırma işleyicisini bir blok içinde iç içe geçirilemez **`__finally`** .

Sonlandırma işleyicisinde izin verilen bazı kod türleri şüpheli sonuçlar üretir, bu nedenle bunları, varsa dikkatli bir şekilde kullanmalısınız. Bunlardan biri, **`goto`** bir ekstre bloğunun dışına atlayan bir ifadedir **`__finally`** . Blok, normal sonlandırmanın bir parçası olarak yürütülüyorsa hiçbir şey olağan dışı olur. Ancak sistem, yığını geri taşıdıysanız, geriye doğru izleme durdu. Ardından, geçerli işlev olağan dışı sonlandırma olmadığından denetim kazanır.

**`return`** Bir ifade bloğu içindeki bir ifade **`__finally`** kabaca aynı durumu gösterir. Denetim, sonlandırma işleyicisini içeren işlevin hemen çağırana döner. Sistem yığını geri alıyorsa, bu işlem durdurulur. Ardından, program bir özel durum ortaya çıkarılmıştı gibi devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)

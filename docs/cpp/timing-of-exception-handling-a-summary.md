---
title: 'Özel durum işleme zamanlaması: Özet'
description: Microsoft C++ ' da özel durum işlemenin zaman ve yürütme sırası.
ms.date: 08/24/2020
helpviewer_keywords:
- sequence [C++]
- sequence, of handlers
- exception handling [C++], timing
- setjmpex.h
- termination handlers [C++], timing
- setjmp.h
- handlers [C++], order of exception
- structured exception handling [C++], timing
ms.assetid: 5d1da546-73fd-4673-aa1a-7ac0f776c420
ms.openlocfilehash: 2ce501d8d74b6f0f7ca92e193c39f8ce58a66053
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898354"
---
# <a name="timing-of-exception-handling-a-summary"></a>Özel durum işleme zamanlaması: Özet

Sonlandırma işleyicisi, **`__try`** Ekstre bloğunun nasıl sonlandırıldığı bağımsız olarak yürütülür. **`__try`**, Blok dışına atlama, `longjmp` denetimin blok dışına aktarımı yapan ve özel durum işleme nedeniyle yığının geri sarılı olmasına neden olur.

> [!NOTE]
> Microsoft C++ derleyicisi, ve deyimlerinin iki biçimini destekler `setjmp` `longjmp` . Hızlı sürüm sonlandırma işlemeyi atlar, ancak daha etkilidir. Bu sürümü kullanmak için dosyasını dahil edin \<setjmp.h> . Diğer sürüm, sonlandırma işlemeyi önceki paragrafta açıklandığı gibi destekler. Bu sürümü kullanmak için dosyasını dahil edin \<setjmpex.h> . Hızlı sürümün performansında artış, donanım yapılandırmasına bağlıdır.

İşletim sistemi, özel durum işleyicisinin gövdesi de dahil olmak üzere başka bir kod yürütülmeden önce tüm sonlandırma işleyicilerini uygun sırada yürütür.

Kesintinin nedeni bir özel durum olduğunda, sistem neyi sonlandıracağına karar vermeden önce bir veya daha fazla özel durum işleyicisinin filtre bölümünü yürütmelidir. Olayların sırası aşağıdaki gibidir:

1. Bir özel durum oluşturulur.

1. Sistem etkin özel durum işleyicilerinin hiyerarşisine bakar ve işleyicinin filtresini en yüksek önceliğe sahip olarak yürütür. En son yüklenen ve en derin iç içe geçmiş olan özel durum işleyicisi, bloklar ve işlev çağrılarına göre yapılır.

1. Bu filtre denetimi geçerse (0 döndürürse) işlem, denetimi geçirmeyen bir filtre bulunana kadar devam eder.

1. Bu filtre-1 döndürürse, yürütme özel durumun oluşturulduğu yerde devam eder ve sonlandırma gerçekleşmez.

1. Filtre 1 değerini döndürürse, aşağıdaki olaylar gerçekleşir:

   - Sistem yığını kaldırır: özel durumun oluşturulduğu ve özel durum işleyicisini içeren yığın çerçevesinin arasındaki tüm yığın çerçevelerini temizler.

   - Yığın geriye doğru izlenirken, yığındaki her sonlandırma işleyicisi yürütülür.

   - Özel durum işleyicisi yürütülür.

   - Denetim, bu özel durum işleyicisi sona erdikten sonra kodun satırına geçer.

## <a name="see-also"></a>Ayrıca bkz.

[Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)

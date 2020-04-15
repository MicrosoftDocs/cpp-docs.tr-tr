---
title: 'Özel durum işleme zamanlaması: Özet'
ms.date: 05/07/2019
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
ms.openlocfilehash: 17d1c250a98afc2b86c198735602df7d80118bd4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316605"
---
# <a name="timing-of-exception-handling-a-summary"></a>Özel durum işleme zamanlaması: Özet

**__try** deyimi bloğu nasıl sonlandırılırsa __try bir sonlandırma işleyicisi yürütülür. Bunun nedenleri arasında **__try** bloğundan `longjmp` atlama, denetimi blok dışına aktaran bir ifade ve özel durum işleme nedeniyle yığının gevşemesi yer alıyor.

> [!NOTE]
> Microsoft C++ derleyicisi iki `setjmp` `longjmp` form ve deyimleri destekler. Hızlı sürüm sonlandırma işlemeyi atlar, ancak daha etkilidir. Bu sürümü kullanmak için, \<dosya setjmp.h> ekleyin. Diğer sürüm, sonlandırma işlemeyi önceki paragrafta açıklandığı gibi destekler. Bu sürümü kullanmak için, \<dosya setjmpex.h> ekleyin. Hızlı sürümün performansında artış, donanım yapılandırmasına bağlıdır.

İşletim sistemi, özel durum işleyicisinin gövdesi de dahil olmak üzere başka bir kod yürütülmeden önce tüm sonlandırma işleyicilerini uygun sırada yürütür.

Kesintinin nedeni bir özel durum olduğunda, sistem neyi sonlandıracağına karar vermeden önce bir veya daha fazla özel durum işleyicisinin filtre bölümünü yürütmelidir. Olayların sırası aşağıdaki gibidir:

1. Bir özel durum oluşturulur.

1. Sistem etkin özel durum işleyicilerinin hiyerarşisini inceler ve en yüksek önceliğe sahip işleyicinin filtresini yürütür; bu, bloklar ve işlev çağrıları bakımından en son yüklenen ve en ayrıntılı olarak iç içe geçmiş olan özel durum işleyicisidir.

1. Bu filtre denetimi (0 döndürür) geçerse, işlem denetimi geçirmeyen bir filtre bulunana dek devam eder.

1. Bu filtre -1 döndürürse, özel durum yükseltildiği yerde yürütme devam ediyor ve sonlandırma gerçekleşmez.

1. Filtre 1 değerini döndürürse, aşağıdaki olaylar gerçekleşir:

   - Sistem yürütülmekte olan kod (özel durumun oluşturulduğu) ve denetimi alan özel durum işleyicisini içeren yığın çerçevesi arasındaki tüm yığın çerçevelerini temizleyerek yığını geriye doğru izler.

   - Yığın geriye doğru izlenirken, yığındaki her sonlandırma işleyicisi yürütülür.

   - Özel durum işleyicisi yürütülür.

   - Denetim, bu özel durum işleyicisi sona erdikten sonra kodun satırına geçer.

## <a name="see-also"></a>Ayrıca bkz.

[Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)

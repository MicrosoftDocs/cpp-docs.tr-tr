---
title: 'Özel durum işlemenin zamanlaması: Özet'
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
ms.openlocfilehash: 3ed2e02412bd84663674a2df2c4454d21e83575a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188122"
---
# <a name="timing-of-exception-handling-a-summary"></a>Özel durum işlemenin zamanlaması: Özet

Sonlandırma işleyicisi, **__try** deyimin bloğunun nasıl sonlandırılduğuna bakılmaksızın yürütülür. Nedenler, denetim bloğunun dışına çıkar ve özel durum işleme nedeniyle yığını geriye doğru `longjmp` bir şekilde **__try** bloğundan atlama içerir.

> [!NOTE]
>  Microsoft C++ derleyicisi `setjmp` ve `longjmp` deyimlerinin iki biçimini destekler. Hızlı sürüm sonlandırma işlemeyi atlar, ancak daha etkilidir. Bu sürümü kullanmak için \<setjmp. h > dosyasını dahil edin. Diğer sürüm, sonlandırma işlemeyi önceki paragrafta açıklandığı gibi destekler. Bu sürümü kullanmak için, \<setjmpex. h > dosyasını dahil edin. Hızlı sürümün performansında artış, donanım yapılandırmasına bağlıdır.

İşletim sistemi, özel durum işleyicisinin gövdesi de dahil olmak üzere başka bir kod yürütülmeden önce tüm sonlandırma işleyicilerini uygun sırada yürütür.

Kesintinin nedeni bir özel durum olduğunda, sistem neyi sonlandıracağına karar vermeden önce bir veya daha fazla özel durum işleyicisinin filtre bölümünü yürütmelidir. Olayların sırası aşağıdaki gibidir:

1. Bir özel durum oluşturulur.

1. Sistem etkin özel durum işleyicilerinin hiyerarşisini inceler ve en yüksek önceliğe sahip işleyicinin filtresini yürütür; bu, bloklar ve işlev çağrıları bakımından en son yüklenen ve en ayrıntılı olarak iç içe geçmiş olan özel durum işleyicisidir.

1. Bu filtre denetimi (0 döndürür) geçerse, işlem denetimi geçirmeyen bir filtre bulunana dek devam eder.

1. Bu filtre-1 döndürürse, yürütme özel durumun oluşturulduğu yerde devam eder ve sonlandırma gerçekleşmez.

1. Filtre 1 değerini döndürürse, aşağıdaki olaylar gerçekleşir:

   - Sistem yürütülmekte olan kod (özel durumun oluşturulduğu) ve denetimi alan özel durum işleyicisini içeren yığın çerçevesi arasındaki tüm yığın çerçevelerini temizleyerek yığını geriye doğru izler.

   - Yığın geriye doğru izlenirken, yığındaki her sonlandırma işleyicisi yürütülür.

   - Özel durum işleyicisi yürütülür.

   - Denetim, bu özel durum işleyicisi sona erdikten sonra kodun satırına geçer.

## <a name="see-also"></a>Ayrıca bkz.

[Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)

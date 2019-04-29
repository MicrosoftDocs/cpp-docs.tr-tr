---
title: 'Özel durum işleme zamanlaması: Özeti'
ms.date: 11/04/2016
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
ms.openlocfilehash: cbff7c4153646fcb3471e18d20a0e633fbd1307f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330459"
---
# <a name="timing-of-exception-handling-a-summary"></a>Özel durum işleme zamanlaması: Özeti

Sonlandırma işleyicisi ne olursa olsun nasıl yürütülen **__try** deyim bloğunu sonlandırılır. Nedenler tanesi atlama **__try** bloğu bir `longjmp` denetim bloğu ve özel durum işleme nedeniyle yığının geriye doğru izleme dışına aktaran deyimi.

> [!NOTE]
>  Visual C++, `setjmp` ve `longjmp` deyiminin iki biçimini destekler. Hızlı sürüm sonlandırma işlemeyi atlar, ancak daha etkilidir. Bu sürümü kullanmak için dosyayı dahil \<setjmp.h >. Diğer sürüm, sonlandırma işlemeyi önceki paragrafta açıklandığı gibi destekler. Bu sürümü kullanmak için dosyayı dahil \<setjmpex.h >. Hızlı sürümün performansında artış, donanım yapılandırmasına bağlıdır.

İşletim sistemi, özel durum işleyicisinin gövdesi de dahil olmak üzere başka bir kod yürütülmeden önce tüm sonlandırma işleyicilerini uygun sırada yürütür.

Kesintinin nedeni bir özel durum olduğunda, sistem neyi sonlandıracağına karar vermeden önce bir veya daha fazla özel durum işleyicisinin filtre bölümünü yürütmelidir. Olayların sırası aşağıdaki gibidir:

1. Bir özel durum oluşturulur.

1. Sistem etkin özel durum işleyicilerinin hiyerarşisini inceler ve en yüksek önceliğe sahip işleyicinin filtresini yürütür; bu, bloklar ve işlev çağrıları bakımından en son yüklenen ve en ayrıntılı olarak iç içe geçmiş olan özel durum işleyicisidir.

1. Bu filtre denetimi (0 döndürür) geçerse, işlem denetimi geçirmeyen bir filtre bulunana dek devam eder.

1. Bu filtre, -1 döndürür, burada özel durum oluştu ve sonlandırma gerçekleşmez gerçekleşmeden yürütme devam eder.

1. Filtre 1 değerini döndürürse, aşağıdaki olaylar gerçekleşir:

   - Sistem yürütülmekte olan kod (özel durumun oluşturulduğu) ve denetimi alan özel durum işleyicisini içeren yığın çerçevesi arasındaki tüm yığın çerçevelerini temizleyerek yığını geriye doğru izler.

   - Yığın geriye doğru izlenirken, yığındaki her sonlandırma işleyicisi yürütülür.

   - Özel durum işleyicisi yürütülür.

   - Denetim, bu özel durum işleyicisi sona erdikten sonra kodun satırına geçer.

## <a name="see-also"></a>Ayrıca bkz.

[Sonlandırma İşleyicisi Yazma](../cpp/writing-a-termination-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
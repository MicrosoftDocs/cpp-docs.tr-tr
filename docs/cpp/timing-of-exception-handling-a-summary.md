---
title: "Özel durum işleme zamanlaması: Özet | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- sequence [C++]
- sequence, of handlers
- exception handling [C++], timing
- SETJMPEX.H
- termination handlers [C++], timing
- SETJMP.H
- handlers [C++], order of exception
- structured exception handling [C++], timing
ms.assetid: 5d1da546-73fd-4673-aa1a-7ac0f776c420
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5d4b522286a727f428cd445bf67d12a1360b49b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="timing-of-exception-handling-a-summary"></a>Özel Durum İşleme Zamanlaması: Özet
Sonlandırma işleyicisi, `__try` deyim bloğu nasıl sonlandırılırsa sonlandırılsın yürütülür. Bunun nedenleri, `__try` bloğundan dışarı atlama, denetimi bloğun dışına aktaran bir `longjmp` deyimi ve özel durum işleme nedeniyle yığının geriye doğru izlenmesidir.  
  
> [!NOTE]
>  Visual C++, `setjmp` ve `longjmp` deyiminin iki biçimini destekler. Hızlı sürüm sonlandırma işlemeyi atlar, ancak daha etkilidir. Bu sürümü kullanmak için SETJMP.H dosyasını dahil edin. Diğer sürüm, sonlandırma işlemeyi önceki paragrafta açıklandığı gibi destekler. Bu sürümü kullanmak için SETJMPEX.H dosyasını dahil edin. Hızlı sürümün performansında artış, donanım yapılandırmasına bağlıdır.  
  
 İşletim sistemi, özel durum işleyicisinin gövdesi de dahil olmak üzere başka bir kod yürütülmeden önce tüm sonlandırma işleyicilerini uygun sırada yürütür.  
  
 Kesintinin nedeni bir özel durum olduğunda, sistem neyi sonlandıracağına karar vermeden önce bir veya daha fazla özel durum işleyicisinin filtre bölümünü yürütmelidir. Olayların sırası aşağıdaki gibidir:  
  
1.  Bir özel durum oluşturulur.  
  
2.  Sistem etkin özel durum işleyicilerinin hiyerarşisini inceler ve en yüksek önceliğe sahip işleyicinin filtresini yürütür; bu, bloklar ve işlev çağrıları bakımından en son yüklenen ve en ayrıntılı olarak iç içe geçmiş olan özel durum işleyicisidir.  
  
3.  Bu filtre denetimi (0 döndürür) geçerse, işlem denetimi geçirmeyen bir filtre bulunana dek devam eder.  
  
4.  Bu filtre -1 döndürürse, yürütme burada özel durumu oluştu ve hiçbir sonlandırma gerçekleşir devam eder.  
  
5.  Filtre 1 değerini döndürürse, aşağıdaki olaylar gerçekleşir:  
  
    -   Sistem yürütülmekte olan kod (özel durumun oluşturulduğu) ve denetimi alan özel durum işleyicisini içeren yığın çerçevesi arasındaki tüm yığın çerçevelerini temizleyerek yığını geriye doğru izler.  
  
    -   Yığın geriye doğru izlenirken, yığındaki her sonlandırma işleyicisi yürütülür.  
  
    -   Özel durum işleyicisi yürütülür.  
  
    -   Denetim, bu özel durum işleyicisi sona erdikten sonra kodun satırına geçer.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)   
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
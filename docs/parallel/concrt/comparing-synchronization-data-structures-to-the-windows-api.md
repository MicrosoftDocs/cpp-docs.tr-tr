---
title: "Eşitleme veri yapılarını Windows API ile karşılaştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- synchronization data structures, compared to Windows API
- event class, example
ms.assetid: 8b0b1a3a-ef80-408c-91fa-93e6af920b4e
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4590724bfc34d0ed9136e74e85b09db6a805c50c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comparing-synchronization-data-structures-to-the-windows-api"></a>Eşitleme Veri Yapılarını Windows API ile Karşılaştırma
Bu konu Windows API tarafından sağlanan için eşzamanlılık çalışma zamanı tarafından sağlanan eşitleme veri yapıları davranışını karşılaştırır.  
  
 Eşzamanlılık Çalışma zamanı tarafından sağlanan eşitleme veri yapıları izleyin *iş parçacığı modeli işbirlikçi*. İşbirlikçi iş parçacığı modeli eşitleme temelleri açıkça başka bir iş parçacığı için işlem kaynaklarını ödeme. Bu farklıdır *PreEmptive tarafından iş parçacığı modeli*, burada işlem kaynakları için başka bir iş parçacığı denetleme Zamanlayıcı veya işletim sistemi tarafından aktarılır.  
  
## <a name="criticalsection"></a>critical_section  
 [Concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) sınıfı benzer Windows `CRITICAL_SECTION` yalnızca bir işlem iş parçacığı tarafından kullanılabildiğinden yapılandırın. Windows API içinde kritik bölümler hakkında daha fazla bilgi için bkz: [kritik bölüm nesnelerin](http://msdn.microsoft.com/library/windows/desktop/ms682530).  
  
## <a name="readerwriterlock"></a>reader_writer_lock  
 [Concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) sınıfı benzer Windows ince Okuyucu/Yazıcı (SRW) kilitler. Aşağıdaki tabloda benzerlikler ve farklar açıklanmaktadır.  
  
|Özellik|`reader_writer_lock`|SRW Kilitle|  
|-------------|--------------------------|--------------|  
|Olmayan yeniden girme|Evet|Evet|  
|Yazıcı (yükseltme desteği) için bir okuyucu yükseltebilirsiniz|Hayır|Hayır|  
|Okuyucu (indirgeme desteği) için bir yazıcı indirgeyebilirsiniz|Hayır|Hayır|  
|Yazma tercih Kilitle|Evet|Hayır|  
|Yazarları FIFO erişimi|Evet|Hayır|  
  
 SRW kilitleri hakkında daha fazla bilgi için bkz: [ince Okuyucu/Yazıcı (SRW) kilitleri](http://msdn.microsoft.com/library/windows/desktop/aa904937) Platform SDK'sındaki.  
  
## <a name="event"></a>olay  
 [Concurrency::event](../../parallel/concrt/reference/event-class.md) sınıfı adlandırılmamış, Windows el ile sıfırlama olaya benzer. Ancak, bir `event` nesne davranır işbirliği ile bir Windows olayı erken önlem davranır ancak. Windows olayları hakkında daha fazla bilgi için bkz: [olay nesneleri](http://msdn.microsoft.com/library/windows/desktop/ms682655).  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Daha iyi arasındaki farkı anlamak için `event` sınıfı ve Windows olaylarını, aşağıdaki örneği göz önünde bulundurun. Bu örnek en fazla iki eş zamanlı görevleri ve ardından iki benzer işlevleri kullanan çağrıları oluşturmak Zamanlayıcı'yı etkinleştirir `event` sınıfı ve bir Windows elle sıfırlama olayı. Her işlev ilk işaret hale paylaşılan bir olayı bekle çeşitli görevleri oluşturur. Her işlev için çalışmakta olan görevlerin verir ve olay işaret eder. Her işlev sonra iş olayı için bekler.  
  
### <a name="code"></a>Kod  
 [!code-cpp[concrt-event-comparison#1](../../parallel/concrt/codesnippet/cpp/comparing-synchronization-data-structures-to-the-windows-api_1.cpp)]  
  
### <a name="comments"></a>Açıklamalar  
 Bu örnekte aşağıdaki örnek çıkışı üretir:  
  
```Output  
Cooperative event:  
    Context 0: waiting on an event.  
    Context 1: waiting on an event.  
    Context 2: waiting on an event.  
    Context 3: waiting on an event.  
    Context 4: waiting on an event.  
    Setting the event.  
    Context 5: received the event.  
    Context 6: received the event.  
    Context 7: received the event.  
    Context 8: received the event.  
    Context 9: received the event.  
Windows event:  
    Context 10: waiting on an event.  
    Context 11: waiting on an event.  
    Setting the event.  
    Context 12: received the event.  
    Context 14: waiting on an event.  
    Context 15: received the event.  
    Context 16: waiting on an event.  
    Context 17: received the event.  
    Context 18: waiting on an event.  
    Context 19: received the event.  
    Context 13: received the event.  
```  
  
 Çünkü `event` sınıfı davranır işbirliği ile bir olay iş durumu girmek için beklediği sırada Zamanlayıcı başka bir bağlam için işlem kaynakları yeniden tahsis edebilirsiniz. Bu nedenle, daha fazla iş kullanan sürümü tarafından gerçekleştirilir `event` sınıfı. Sonraki görev başlatılmadan önce Windows olayları kullanan sürümünde her bekleme görev iş durumu girmeniz gerekir.  
  
 Görevler hakkında daha fazla bilgi için bkz: [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)

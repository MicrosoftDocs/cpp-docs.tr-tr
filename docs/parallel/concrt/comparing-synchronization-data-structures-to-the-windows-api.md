---
title: Eşitleme veri yapılarını Windows API ile karşılaştırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- synchronization data structures, compared to Windows API
- event class, example
ms.assetid: 8b0b1a3a-ef80-408c-91fa-93e6af920b4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff827c326f331acae4d16381856ad4df01550524
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447056"
---
# <a name="comparing-synchronization-data-structures-to-the-windows-api"></a>Eşitleme Veri Yapılarını Windows API ile Karşılaştırma

Bu konu Windows API tarafından sağlanan için eşzamanlılık çalışma zamanı tarafından sağlanan eşitleme veri yapıları davranışını karşılaştırır.

Eşzamanlılık Çalışma zamanı tarafından sağlanan eşitleme veri yapıları izleyin *iş parçacığı modeli Guyana*. Eşitleme temellerine, işbirliği yapan iş parçacığı modelinde, işlem kaynaklarını diğer iş parçacıkları açıkça yield. Bu farklıdır *preemptive iş parçacığı modeli*, burada işlem kaynakları için diğer iş parçacıklarını denetleme Zamanlayıcı veya işletim sistemi tarafından aktarılır.

## <a name="criticalsection"></a>critical_section

[Concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) sınıfına benzer Windows `CRITICAL_SECTION` yalnızca bir işlem iş parçacıklarının engellemelerinden kullanılabildiğinden yapılandırın. Windows API kritik olarak bölümlerde hakkında daha fazla bilgi için bkz: [kritik bölüm nesneleri](/windows/desktop/Sync/critical-section-objects).

## <a name="readerwriterlock"></a>reader_writer_lock

[Concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) Windows ince Okuyucu / (SRW) yazıcı kilitleri sınıfına benzer. Aşağıdaki tabloda, benzerlikler ve farklar açıklanmaktadır.

|Özellik|`reader_writer_lock`|SRW Kilitle|
|-------------|--------------------------|--------------|
|Olmayan yeniden girme|Evet|Evet|
|Bir yazıcı (yükseltme desteği) için bir okuyucu yükseltebilirsiniz|Hayır|Hayır|
|Bir okuyucu (Sürüm Düşürme desteği) için bir yazıcı indirgeyebilirsiniz|Hayır|Hayır|
|Yazma tercih Kilitle|Evet|Hayır|
|Yazıcılar FIFO erişim|Evet|Hayır|

SRW kilitleri hakkında daha fazla bilgi için bkz: [ince Okuyucu/Yazıcı (SRW) kilitleri](https://msdn.microsoft.com/library/windows/desktop/aa904937) Platform SDK.

## <a name="event"></a>olay

[Concurrency::event](../../parallel/concrt/reference/event-class.md) sınıfına benzer bir adlandırılmamış, Windows elle sıfırlama olayı. Ancak, bir `event` nesne davranışını işbirliği ile bir Windows olayı sıd'lerde davranır ancak. Windows olayları hakkında daha fazla bilgi için bkz: [olay nesneleri](/windows/desktop/Sync/event-objects).

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Daha iyi arasındaki farkı anlamak için `event` sınıfı ve Windows olayları, aşağıdaki örneği göz önünde bulundurun. Bu örnek en fazla iki eşzamanlı görevlerini ve iki benzer işlevleri kullanan çağrıları oluşturmak Zamanlayıcı `event` sınıfı ve bir Windows elle sıfırlama olayı. Her işlevin ilk sinyal haline paylaşılan bir olay beklemek birkaç görev oluşturur. Her işlev için çalışmakta olan görevlerin ardından verir ve ardından olay sinyalini verir. Her işlev, ardından sinyal olayı için bekler.

### <a name="code"></a>Kod

[!code-cpp[concrt-event-comparison#1](../../parallel/concrt/codesnippet/cpp/comparing-synchronization-data-structures-to-the-windows-api_1.cpp)]

### <a name="comments"></a>Açıklamalar

Bu örnek, örnek aşağıdaki çıktıyı üretir:

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

Çünkü `event` sınıfı davranışını işbirliği içerisinde devamlılığı, olaya sinyal durumuna girmek için beklediği sırada Zamanlayıcı işlem kaynakları için başka bir bağlamı yeniden tahsis edebilirsiniz. Bu nedenle, daha fazla iş kullanan sürümü tarafından gerçekleştirilir `event` sınıfı. Sonraki görev başlatılmadan önce Windows olayları kullanan sürümünde her bekleyen görev sinyal verilmiş duruma dönmesine girmeniz gerekir.

Görevler hakkında daha fazla bilgi için bkz. [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)

---
title: Eşitleme Veri Yapılarını Windows API ile Karşılaştırma
ms.date: 11/04/2016
helpviewer_keywords:
- synchronization data structures, compared to Windows API
- event class, example
ms.assetid: 8b0b1a3a-ef80-408c-91fa-93e6af920b4e
ms.openlocfilehash: 16d58431ae3f9859677302010f15a75b37ebedbf
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510596"
---
# <a name="comparing-synchronization-data-structures-to-the-windows-api"></a>Eşitleme Veri Yapılarını Windows API ile Karşılaştırma

Bu konu, Eşzamanlılık Çalışma Zamanı tarafından belirtilen eşitleme verileri yapılarının davranışını Windows API tarafından sağlananlara karşılaştırır.

Eşzamanlılık Çalışma Zamanı tarafından belirtilen eşitleme verileri yapıları, *birlikte çalışırken iş parçacığı modelini*izler. Ortak iş parçacığı modelinde, eşitleme temelleri işlem kaynaklarını açıkça diğer iş parçacıklarına sağlar. Bu, işleme kaynaklarının denetim Zamanlayıcısı veya işletim sistemi tarafından diğer iş parçacığına aktarıldığı *preemptive iş parçacığı modelinden*farklıdır.

## <a name="critical_section"></a>critical_section

[Concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) sınıfı, yalnızca bir işlemin `CRITICAL_SECTION` iş parçacıkları tarafından kullanılabilmesi için Windows yapısına benzer. Windows API 'sindeki kritik bölümler hakkında daha fazla bilgi için bkz. [kritik bölüm nesneleri](/windows/win32/Sync/critical-section-objects).

## <a name="reader_writer_lock"></a>reader_writer_lock

[Concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) sınıfı Windows ince okuyucu/yazıcı (SRW) kilitlerine benzer. Aşağıdaki tabloda benzerlikler ve farklar açıklanmaktadır.

|Özellik|`reader_writer_lock`|SRW kilidi|
|-------------|--------------------------|--------------|
|Yer yok|Evet|Evet|
|Bir okuyucuyu bir yazıcıya yükseltebilir (yükseltme desteği)|Hayır|Hayır|
|Bir yazıcıyı bir okuyucuya indirgeyebilirler (desteği düşürme)|Hayır|Hayır|
|Yazma tercihi kilidi|Evet|Hayır|
|Yazıcılara FıFO erişimi|Evet|Hayır|

SRW kilitleri hakkında daha fazla bilgi için bkz. Platform SDK 'sında [Ince okuyucu/yazıcı (SRW) kilitleri](/windows/win32/sync/slim-reader-writer--srw--locks) .

## <a name="event"></a>olay

[Concurrency:: Event](../../parallel/concrt/reference/event-class.md) sınıfı adlandırılmamış, Windows el ile sıfırlama olayına benzer. Ancak, `event` bir nesnesi birlikte çalışır, ancak bir Windows olayı preemptively olarak davranır. Windows olayları hakkında daha fazla bilgi için bkz. [olay nesneleri](/windows/win32/Sync/event-objects).

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

`event` Sınıf ve Windows olayları arasındaki farkı daha iyi anlamak için aşağıdaki örneği göz önünde bulundurun. Bu örnek, Scheduler 'ın en fazla iki eş zamanlı görevi oluşturmasını ve sonra `event` sınıfını ve Windows el ile sıfırlama olayını kullanan iki benzer işlevi çağırmalarını sağlar. Her bir işlev önce, paylaşılan bir olayın sinyal vermesini bekleyen birkaç görev oluşturur. Sonra her işlev çalışan görevlere bildirir ve sonra olaya bildirir. Her işlev, sinyal verdi olayı bekler.

### <a name="code"></a>Kod

[!code-cpp[concrt-event-comparison#1](../../parallel/concrt/codesnippet/cpp/comparing-synchronization-data-structures-to-the-windows-api_1.cpp)]

### <a name="comments"></a>Açıklamalar

Bu örnek aşağıdaki örnek çıktıyı üretir:

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

`event` Sınıfı birlikte davrandığı için Zamanlayıcı, bir olay, sinyal durumunun girilmesi beklenirken, işlem kaynaklarını başka bir içeriğe yeniden tahsis edebilir. Bu nedenle, `event` sınıfını kullanan sürüm tarafından daha fazla iş gerçekleştirilir. Windows olaylarını kullanan sürümde, bekleyen her görevin bir sonraki görev başlatılmadan önce sinyal durumuna girmesi gerekir.

Görevler hakkında daha fazla bilgi için bkz. [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="see-also"></a>Ayrıca bkz.

[Eşitleme Veri Yapıları](../../parallel/concrt/synchronization-data-structures.md)

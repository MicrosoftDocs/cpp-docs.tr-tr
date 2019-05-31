---
title: Paralel Tanılama Araçları (Eşzamanlılık Çalışma Zamanı)
ms.date: 11/04/2016
helpviewer_keywords:
- Parallel Diagnostic Tools [Concurrency Runtime]
ms.assetid: b1a3f1d2-f5df-4f29-852e-906b3d8341fc
ms.openlocfilehash: 182171bfcfbaf1476cc25fe3160114bc1d96ca7e
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66449238"
---
# <a name="parallel-diagnostic-tools-concurrency-runtime"></a>Paralel Tanılama Araçları (Eşzamanlılık Çalışma Zamanı)

Visual Studio hata ayıklama ve profil oluşturma çok iş parçacıklı uygulamalar için kapsamlı destek sağlar.

## <a name="debugging"></a>Hata Ayıklama

Visual Studio hata ayıklayıcı içerir **Paralel Yığınlar** penceresinde **Paralel Görevler** penceresinde ve **paralel izleme** penceresi. Daha fazla bilgi için [izlenecek yol: Paralel uygulamada hata ayıklama](/visualstudio/debugger/walkthrough-debugging-a-parallel-application) ve [nasıl yapılır: Paralel İzleme penceresini kullanma](/visualstudio/debugger/how-to-use-the-parallel-watch-window).

## <a name="profiling"></a>Profil Oluşturma

Profil oluşturma araçları, çok iş parçacıklı bir uygulamanın kendisiyle ve diğer programları ile nasıl etkileşim kurduğu hakkında grafik, tablo ve sayısal bilgilerini gösteren üç veri görünümleri sağlar. Görünümleri sorunlu alanları hızlı bir şekilde tanımlamanıza olanak sağlar ve çağrı yığınları, için grafik görüntüler noktalarından gitmek için siteleri ve kaynak kodu çağırın. Daha fazla bilgi için [eşzamanlılık görselleştiricisi](/visualstudio/profiling/concurrency-visualizer).

## <a name="event-tracing"></a>Olay izleme

Eşzamanlılık Çalışma zamanı kullanan [olay izleme için Windows](/windows/desktop/ETW/event-tracing-portal) izleme araçları, profil oluşturucular gibi çeşitli olaylar meydana geldiğinde bildirmek için (ETW). Bir paralel algoritma başladığı ve bittiği zaman bir zamanlayıcı etkinleştirilmiş veya devre dışı bir bağlam başlar, sona erer, engeller, engellemesini kaldırır veya oluşturur ve bu olayları dahil.

Araçlar [eşzamanlılık görselleştiricisi](/visualstudio/profiling/concurrency-visualizer) bu işlevselliğini kullanır; bu nedenle, genellikle bu olayları ile doğrudan çalışmak zorunda değilsiniz. Bu olayları, özel bir profil oluşturucu geliştirme veya olay izleme araçları gibi kullandığınızda, ancak kullanışlıdır [Xperf](https://go.microsoft.com/fwlink/p/?linkid=160628).

Eşzamanlılık Çalışma zamanı, bu olaylar yalnızca izleme etkinleştirildiğinde başlatır. Çağrı [concurrency::EnableTracing](reference/concurrency-namespace-functions.md#enabletracing) olay izlemeyi etkinleştirmek için işlevi ve [concurrency::DisableTracing](reference/concurrency-namespace-functions.md#disabletracing) izlemeyi devre dışı bırakmak için işlevi.

Aşağıdaki tablo, çalışma zamanı olay izleme etkin olduğunda oluşturan olayları anlatmaktadır:

|Olay|Açıklama|Değer|
|-----------|-----------------|-----------|
|[CONCURRENCY::ConcRT_ProviderGuid](reference/concurrency-namespace-constants1.md#concrt_providerguid)|Eşzamanlılık Çalışma zamanı ETW sağlayıcısı tanımlayıcısı.|`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|
|[CONCURRENCY::ContextEventGuid](reference/concurrency-namespace-constants1.md#contexteventguid)|İçerikleri ilgili olayları işaretler.|`5727a00f-50be-4519-8256-f7699871fecb`|
|[CONCURRENCY::PPLParallelForEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeventguid)|Giriş ve çıkış için çağrıları işaretler [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması.|`31c8da6b-6165-4042-8b92-949e315f4d84`|
|[CONCURRENCY::PPLParallelForeachEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeacheventguid)|Giriş ve çıkış için çağrıları işaretler [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritması.|`5cb7d785-9d66-465d-bae1-4611061b5434`|
|[CONCURRENCY::PPLParallelInvokeEventGuid](reference/concurrency-namespace-constants1.md#pplparallelinvokeeventguid)|Giriş ve çıkış için çağrıları işaretler [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritması.|`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|
|[CONCURRENCY::SchedulerEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)|İlgili olayları işaretler [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).|`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|
|[CONCURRENCY::VirtualProcessorEventGuid](reference/concurrency-namespace-constants1.md#virtualprocessoreventguid)|Sanal işlemci için ilgili olayları işaretler.|`2f27805f-1676-4ecc-96fa-7eb09d44302f`|

Eşzamanlılık Çalışma zamanı tanımlar, ancak değil şu anda, aşağıdaki olayları oluşturma. Çalışma zamanı gelecekte kullanım için bu olayları ayırır:

- [CONCURRENCY::ConcRTEventGuid](reference/concurrency-namespace-constants1.md#concrteventguid)

- [CONCURRENCY::ScheduleGroupEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)

- [CONCURRENCY::ChoreEventGuid](reference/concurrency-namespace-constants1.md#choreeventguid)

- [CONCURRENCY::LockEventGuid](reference/concurrency-namespace-constants1.md#lockeventguid)

- [CONCURRENCY::ResourceManagerEventGuid](reference/concurrency-namespace-constants1.md#resourcemanagereventguid)

[Concurrency::ConcRT_EventType](reference/concurrency-namespace-enums.md#concrt_eventtype) numaralandırması bir olayı izleyen olası işlemler belirtir. Örneğin, girişinde `parallel_for` algoritması, çalışma zamanı oluşturur `PPLParallelForEventGuid` olay ve sağlar `CONCRT_EVENT_START` işlemi olarak. Önce `parallel_for` algoritması döndürür, çalışma zamanı yeniden başlatır `PPLParallelForEventGuid` olay ve sağlar `CONCRT_EVENT_END` işlemi olarak.

Aşağıdaki örnekte bir çağrı için izlemenin nasıl etkinleştirileceği gösterilmektedir `parallel_for`. Çalışma zamanı yapılan ilk çağrı izlemez `parallel_for` izleme etkin değil, çünkü. Çağrı `EnableTracing` için yapılan ikinci çağrı izleme çalışma zamanının `parallel_for`.

[!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/cpp/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]

Çalışma zamanı, çağrı sayısını izler `EnableTracing` ve `DisableTracing`. Bu nedenle, eğer `EnableTracing` birden çok kez çağırmanız gerekir `DisableTracing` izlemeyi devre dışı bırakmak için aynı sayısı.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)

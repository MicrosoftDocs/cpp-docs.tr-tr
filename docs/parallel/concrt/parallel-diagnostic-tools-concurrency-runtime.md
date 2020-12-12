---
description: 'Daha fazla bilgi edinin: paralel Tanılama Araçları (Eşzamanlılık Çalışma Zamanı)'
title: Paralel Tanılama Araçları (Eşzamanlılık Çalışma Zamanı)
ms.date: 11/04/2016
helpviewer_keywords:
- Parallel Diagnostic Tools [Concurrency Runtime]
ms.assetid: b1a3f1d2-f5df-4f29-852e-906b3d8341fc
ms.openlocfilehash: 44d885e8e6c7529bd15fa0aa2e7930773400361f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172433"
---
# <a name="parallel-diagnostic-tools-concurrency-runtime"></a>Paralel Tanılama Araçları (Eşzamanlılık Çalışma Zamanı)

Visual Studio, çok iş parçacıklı uygulamalarda hata ayıklama ve profil oluşturma için kapsamlı destek sağlar.

## <a name="debugging"></a>Hata Ayıklama

Visual Studio hata ayıklayıcı **Paralel Yığınlar** penceresini, **paralel görevler** penceresini ve **paralel izleme** penceresini içerir. Daha fazla bilgi için bkz. [Izlenecek yol: paralel uygulamada hata ayıklama](/visualstudio/debugger/walkthrough-debugging-a-parallel-application) ve [nasıl yapılır: Paralel İzleme penceresini kullanma](/visualstudio/debugger/how-to-use-the-parallel-watch-window).

## <a name="profiling"></a>Profil Oluşturma

Profil oluşturma araçları, çok iş parçacıklı bir uygulamanın kendisiyle ve diğer programlarla nasıl etkileştiğini gösteren grafik, tablo ve sayısal bilgileri görüntüleyen üç veri görünümü sağlar. Görünümler, sorun alanlarını hızlıca tanımlamanızı ve yığın, çağrı siteleri ve kaynak kodu çağırmak için grafik ekranların noktalarından gezinebilmenizi sağlar. Daha fazla bilgi için bkz. [Eşzamanlılık görselleştiricisi](/visualstudio/profiling/concurrency-visualizer).

## <a name="event-tracing"></a>Olay Izleme

Eşzamanlılık Çalışma Zamanı, çeşitli olaylar meydana geldiğinde profil oluşturucular gibi izleme araçlarına bildirmek için [Windows Için olay izleme](/windows/win32/ETW/event-tracing-portal) (ETW) kullanır. Bu olaylar, bir Scheduler 'ın ne zaman etkinleştirildiğini veya devre dışı bırakıldığını, bir bağlamın başladığı, bittiği, blokların, kaldırmaların veya ne zaman, ne zaman bir paralel algoritma başladığı veya bittiğini içerir.

[Eşzamanlılık görselleştiricisi](/visualstudio/profiling/concurrency-visualizer) gibi araçlar bu işlevselliği kullanır; Bu nedenle, genellikle bu olaylarla doğrudan çalışmanız gerekmez. Ancak, bu olaylar özel bir profil oluşturucu geliştirirken veya [XPerf](https://go.microsoft.com/fwlink/p/?linkid=160628)gibi olay izleme araçlarını kullanırken faydalıdır.

Eşzamanlılık Çalışma Zamanı, bu olayları yalnızca izleme etkinleştirildiğinde oluşturur. İzlemeyi devre dışı bırakmak için olay izlemeyi ve [eşzamanlılık::D isableTracing](reference/concurrency-namespace-functions.md#disabletracing) işlevini etkinleştirmek üzere [concurrency:: EnableTracing](reference/concurrency-namespace-functions.md#enabletracing) işlevini çağırın.

Aşağıdaki tabloda, olay izleme etkinleştirildiğinde çalışma zamanının harekete geçirme olayları açıklanmaktadır:

|Olay|Açıklama|Değer|
|-----------|-----------------|-----------|
|[Eşzamanlılık:: ConcRT_ProviderGuid](reference/concurrency-namespace-constants1.md#concrt_providerguid)|Eşzamanlılık Çalışma Zamanı için ETW sağlayıcısı tanımlayıcısı.|`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|
|[concurrency:: ContextEventGuid](reference/concurrency-namespace-constants1.md#contexteventguid)|Bağlamlarla ilgili olayları işaretler.|`5727a00f-50be-4519-8256-f7699871fecb`|
|[Eşzamanlılık::P PLParallelForEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeventguid)|[Concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasına çağrı yapmak için Entrance ve Exit işaretlerini işaretler.|`31c8da6b-6165-4042-8b92-949e315f4d84`|
|[Eşzamanlılık::P PLParallelForeachEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeacheventguid)|[Concurrency::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasına çağrı yapmak için Entrance ve Exit işaretlerini işaretler.|`5cb7d785-9d66-465d-bae1-4611061b5434`|
|[Eşzamanlılık::P PLParallelInvokeEventGuid](reference/concurrency-namespace-constants1.md#pplparallelinvokeeventguid)|[Concurrency::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmasına çağrı yapmak için Entrance ve Exit işaretlerini işaretler.|`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|
|[Eşzamanlılık:: SchedulerEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)|[Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)ilgili olayları işaretler.|`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|
|[Eşzamanlılık:: VirtualProcessorEventGuid](reference/concurrency-namespace-constants1.md#virtualprocessoreventguid)|Sanal işlemcilerle ilgili olayları işaretler.|`2f27805f-1676-4ecc-96fa-7eb09d44302f`|

Eşzamanlılık Çalışma Zamanı, aşağıdaki olayları tanımlar, ancak şu anda yükseltmez. Çalışma zamanı, daha sonra kullanılmak üzere bu olayları ayırır:

- [concurrency:: ConcRTEventGuid](reference/concurrency-namespace-constants1.md#concrteventguid)

- [concurrency:: ScheduleGroupEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)

- [concurrency:: ChoreEventGuid](reference/concurrency-namespace-constants1.md#choreeventguid)

- [Eşzamanlılık:: LockEventGuid](reference/concurrency-namespace-constants1.md#lockeventguid)

- [Eşzamanlılık:: ResourceManagerEventGuid](reference/concurrency-namespace-constants1.md#resourcemanagereventguid)

[Concurrency:: ConcRT_EventType](reference/concurrency-namespace-enums.md#concrt_eventtype) numaralandırması bir olayın izlediği olası işlemleri belirtir. Örneğin, `parallel_for` algoritma girişinde, çalışma zamanı `PPLParallelForEventGuid` olayı oluşturur ve `CONCRT_EVENT_START` işlem olarak sağlar. Algoritma döndürülmadan önce, `parallel_for` çalışma zamanı `PPLParallelForEventGuid` olayı oluşturur ve `CONCRT_EVENT_END` işlem olarak sağlar.

Aşağıdaki örnek için bir çağrısı için izlemenin nasıl etkinleştirileceği gösterilmektedir `parallel_for` . Çalışma zamanı, izleme etkinleştirilmediği için ilk çağrıyı izlemez `parallel_for` . ' A yapılan çağrı, `EnableTracing` çalışma zamanının ikinci çağrıyı izlemesini sağlar `parallel_for` .

[!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/cpp/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]

Çalışma zamanı, ve ' i çağırdığınız sürelerin sayısını `EnableTracing` izler `DisableTracing` . Bu nedenle, `EnableTracing` birden çok kez çağrı yaparsanız, `DisableTracing` izlemeyi devre dışı bırakmak için aynı sayıda kez çağrı yapmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)

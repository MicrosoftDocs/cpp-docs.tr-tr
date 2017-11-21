---
title: "Paralel Tanılama Araçları (eşzamanlılık çalışma zamanı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Parallel Diagnostic Tools [Concurrency Runtime]
ms.assetid: b1a3f1d2-f5df-4f29-852e-906b3d8341fc
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2e85ee1a0c250cf67f2a379ccad8c11a99b96f76
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="parallel-diagnostic-tools-concurrency-runtime"></a>Paralel Tanılama Araçları (Eşzamanlılık Çalışma Zamanı)
[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]hata ayıklama ve profil çok iş parçacıklı uygulamalar için kapsamlı destek sağlar.  
  
## <a name="debugging"></a>Hata Ayıklama  
 Visual Studio hata ayıklayıcısı içeren **Paralel Yığınlar** penceresinde **Paralel Görevler** penceresinde ve **paralel Gözcü** penceresi. Daha fazla bilgi için bkz: [izlenecek yol: paralel uygulamada hata ayıklama](/visualstudio/debugger/walkthrough-debugging-a-parallel-application) ve [nasıl yapılır: paralel İzleme penceresini kullanma](/visualstudio/debugger/how-to-use-the-parallel-watch-window).  
  
## <a name="profiling"></a>Profil Oluşturma  
 Profil oluşturma araçları çok iş parçacıklı uygulama kendisiyle ve diğer programları ile nasıl etkileşim kurduğu hakkında grafik, tablo ve sayısal bilgileri görüntüleyen üç veri görünümleri sağlar. Görünümleri sorun alanlarını hızla tanımlamanıza olanak sağlar ve çağrı yığınları, grafik görüntüler noktalarından gitmek için siteleri ve kaynak kodunu çağırın. Daha fazla bilgi için bkz: [eşzamanlılık görselleştiricisi](/visualstudio/profiling/concurrency-visualizer).  
  
## <a name="event-tracing"></a>Olay izleme  
 Eşzamanlılık Çalışma zamanı kullanan [Windows için olay izleme](http://msdn.microsoft.com/library/windows/desktop/bb968803) çeşitli olaylar meydana geldiğinde profil oluşturucular gibi izleme araçları bildirmek için (ETW). Paralel bir algoritma başlıyor veya bitiyorsa, bu olayları bir zamanlayıcı etkinleştirilmiş veya devre dışı bırakıldığında, bir bağlam başlar, sona erer, engeller, kaldırır veya verir ve içerir.  
  
 Gibi araçları [eşzamanlılık görselleştiricisi](/visualstudio/profiling/concurrency-visualizer) bu işlevselliğini kullanır; bu nedenle, genellikle bu olayları ile doğrudan çalışmak zorunda değilsiniz. Ancak, bu olayların ne zaman özel bir profil oluşturucu geliştirme kullandığınızda veya olay izleme araçları gibi yararlı [XPerf'in](http://go.microsoft.com/fwlink/linkid=160628).  
  
 Eşzamanlılık Çalışma zamanı yalnızca izleme etkinleştirildiğinde bu olayları başlatır. Çağrı [concurrency::EnableTracing](reference/concurrency-namespace-functions.md#enabletracing) olayı izlemeyi etkinleştirmek için işlev ve [concurrency::DisableTracing](reference/concurrency-namespace-functions.md#disabletracing) izlemeyi devre dışı bırakmak işlevi.  
  
 Aşağıdaki tabloda, olay izleme etkin olduğunda, çalışma zamanı başlatır olaylarını açıklar:  
  
|Olay|Açıklama|Değer|  
|-----------|-----------------|-----------|  

|[CONCURRENCY::ConcRT_ProviderGuid](reference/concurrency-namespace-constants1.md#concrt_providerguid)| Eşzamanlılık Çalışma zamanı için ETW sağlayıcı tanımlayıcısı. |`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|  
|[CONCURRENCY::ContextEventGuid](reference/concurrency-namespace-constants1.md#contexteventguid)| İçerikleri ilgili olayları işaretler. |`5727a00f-50be-4519-8256-f7699871fecb`|  
|[CONCURRENCY::PPLParallelForEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeventguid)| Giriş ve çıkış çağrıları için işaretler [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması. |`31c8da6b-6165-4042-8b92-949e315f4d84`|  
|[CONCURRENCY::PPLParallelForeachEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeacheventguid)| Giriş ve çıkış çağrıları için işaretler [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritması. |`5cb7d785-9d66-465d-bae1-4611061b5434`|  
|[CONCURRENCY::PPLParallelInvokeEventGuid](reference/concurrency-namespace-constants1.md#pplparallelinvokeeventguid)| Giriş ve çıkış çağrıları için işaretler [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritması. |`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|  
|[CONCURRENCY::SchedulerEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)| İlgili olayları işaretler [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md). |`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|  
|[CONCURRENCY::VirtualProcessorEventGuid](reference/concurrency-namespace-constants1.md#virtualprocessoreventguid)| Sanal işlemciler ilgili olayları işaretler. |`2f27805f-1676-4ecc-96fa-7eb09d44302f`|  
  
 Eşzamanlılık Çalışma zamanı tanımlar, ancak değil şu anda, aşağıdaki olaylar oluşturma. Çalışma zamanı gelecekte kullanım için bu olayları ayırır:  
  
-   [CONCURRENCY::ConcRTEventGuid](reference/concurrency-namespace-constants1.md#concrteventguid)  
  
-   [CONCURRENCY::ScheduleGroupEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)  
  
-   [CONCURRENCY::ChoreEventGuid](reference/concurrency-namespace-constants1.md#choreeventguid)  
  
-   [CONCURRENCY::LockEventGuid](reference/concurrency-namespace-constants1.md#lockeventguid)  
  
-   [CONCURRENCY::ResourceManagerEventGuid](reference/concurrency-namespace-constants1.md#resourcemanagereventguid)  
  
 [Concurrency::ConcRT_EventType](reference/concurrency-namespace-enums.md#concrt_eventtype) numaralandırma olaya izler olası işlemleri belirtir. Örneğin, girişinin en `parallel_for` algoritması, çalışma zamanı başlatır `PPLParallelForEventGuid` olay ve sağlar `CONCRT_EVENT_START` işlemi olarak. Önce `parallel_for` algoritması döndürür, çalışma zamanı yeniden başlatır `PPLParallelForEventGuid` olay ve sağlar `CONCRT_EVENT_END` işlemi olarak.  
  
 Aşağıdaki örnek bir çağrı izlemeyi etkinleştirmek nasıl gösterilmektedir `parallel_for`. Çalışma zamanı ilk çağrıda izlemez `parallel_for` etkin değil, izleme için. Çağrı `EnableTracing` için ikinci çağrı izlemek çalışma zamanı etkinleştirir `parallel_for`.  
  
 [!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/cpp/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]  
  
 Çalışma zamanı, çağrı sayısı izler `EnableTracing` ve `DisableTracing`. Bu nedenle, çağırırsanız `EnableTracing` birden çok kez çağırmalısınız `DisableTracing` izlemeyi devre dışı bırakmak için aynı sayısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma zamanı](../../parallel/concrt/concurrency-runtime.md)


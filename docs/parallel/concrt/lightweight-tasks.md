---
title: "Basit görevler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- lightweight tasks
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 010f5fd443271bec1d28b6760f0c17f4e17d803b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="lightweight-tasks"></a>Basit Görevler
Bu belge rolü eşzamanlılık çalışma zamanındaki Basit görevler açıklanmaktadır. A *basit görev* doğrudan zamanlama bir görevdir bir `concurrency::Scheduler` veya `concurrency::ScheduleGroup` nesnesi. Windows API için sağladığınız işlevi basit bir görev benzer [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) işlevi. Bu nedenle, Basit görevler eşzamanlılık çalışma zamanı zamanlama işlevselliğini kullanmak için var olan kodu uyum olduğunda yararlıdır. Eşzamanlılık Çalışma Basit görevler zaman uyumsuz aracılar zamanlamak ve zaman uyumsuz ileti blokları arasındaki iletileri göndermek için kullanır.  
  
> [!TIP]
>  Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağlar ve bu nedenle, uygulamanızda oluşturmak için gerekli değildir. Görev Zamanlayıcısı'nı, uygulamalarınızın performansını ince ayar yardımcı olduğundan, ile başlamanızı öneririz [paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanıyorsanız Eşzamanlılık Çalışma zamanı için yeni.  
  
 Basit görevler zaman uyumsuz aracılar ve görev grupları daha az yüke taşır. Örneğin, çalışma zamanı, basit bir görev tamamlandığında bildirin değil. Ayrıca, çalışma zamanı catch ya da basit bir görevden oluşturulan özel durumları işleme. Özel durum işleme ve Basit görevler hakkında daha fazla bilgi için bkz: [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Görevlerin çoğunda, görev grupları gibi daha sağlam işlevselliği kullanmak ve bunlar daha kolay izin çünkü paralel algoritmalar karmaşık görevleri daha temel parçalara bölün. öneririz. Görev grupları hakkında daha fazla bilgi için bkz: [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md). Paralel algoritmalar hakkında daha fazla bilgi için bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).  
  
 Basit bir görev oluşturmak için çağrı [concurrency::ScheduleGroup::ScheduleTask](reference/schedulegroup-class.md#scheduletask), [concurrency::CurrentScheduler::ScheduleTask](reference/currentscheduler-class.md#scheduletask), veya [concurrency::Scheduler::ScheduleTask ](reference/scheduler-class.md#scheduletask) yöntemi. Bir basit bir görevi tamamlamak için beklenecek kapatıldı veya eşitleme mekanizması gibi kullanmak için üst Zamanlayıcı için bekleyin bir [concurrency::event](../../parallel/concrt/reference/event-class.md) nesnesi.  
  
## <a name="example"></a>Örnek  
 Mevcut kodu hafif bir görev kullanmaya uyarlama yapmayı gösteren bir örnek için bkz [izlenecek yol: Basit görevler kullanmak için var olan kodu uyarlama](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [İzlenecek Yol: Mevcut Kodu Hafif Görevleri Kullanmaya Uyarlama](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)


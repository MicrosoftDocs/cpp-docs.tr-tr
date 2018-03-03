---
title: "İzlenecek yol: Mevcut kodu hafif görevleri kullanmaya uyarlama | Microsoft Docs"
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
- using lightweight tasks [Concurrency Runtime]
- lightweight tasks, using [Concurrency Runtime]
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8a50ad04421d7b4bcdc4a2c98de8f5a57b255c75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-adapting-existing-code-to-use-lightweight-tasks"></a>İzlenecek yol: Mevcut Kodu Hafif Görevleri Kullanmaya Uyarlama
Bu konu, Windows API'si oluşturmak ve basit bir görev kullanmak için bir iş parçacığını yürütmek için kullanılan var olan kodu uyum gösterilmektedir.  
  
 A *basit görev* doğrudan zamanlama bir görevdir bir [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) veya [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) nesnesi. Basit görevler eşzamanlılık çalışma zamanı zamanlama işlevselliğini kullanmak için var olan kodu uyum olduğunda yararlıdır.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuza başlamadan önce bu konuyu okuyun [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek oluşturmak ve bir iş parçacığını yürütmek için Windows API'ın tipik kullanım gösterilmektedir. Bu örnekte [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) çağrılacak işlevi `MyThreadFunction` ayrı bir iş parçacığı üzerinde.  
  
### <a name="code"></a>Kod  
 [!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]  
  
### <a name="comments"></a>Açıklamalar  
 Bu örnek şu çıkışı üretir.  
  
```Output  
Parameters = 50, 100  
```  
  
 Aşağıdaki adımlar, kod örneğini aynı görevi gerçekleştirmenin eşzamanlılık çalışma zamanı kullanmak için uyum gösterilmektedir.  
  
### <a name="to-adapt-the-example-to-use-a-lightweight-task"></a>Örneği basit bir görev kullanacak şekilde uyarlamak için  
  
1.  Ekleme bir `#include` üstbilgi dosyası concrt.h için yönerge.  
  
 [!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]  
  
2.  Ekleme bir `using` için yönerge `concurrency` ad alanı.  
  
 [!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]  
  
3.  Bildirimi değiştirme `MyThreadFunction` kullanmak için `__cdecl` çağırma ve döndürülecek `void`.  
  
 [!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]  
  
4.  Değiştirme `MyData` içerecek şekilde yapısı bir [concurrency::event](../../parallel/concrt/reference/event-class.md) görevi tamamlandı ana uygulama sinyalleri nesnesi.  
  
 [!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]  
  
5.  Çağrı Değiştir `CreateThread` çağrısıyla [concurrency::CurrentScheduler::ScheduleTask](reference/currentscheduler-class.md#scheduletask) yöntemi.  

  
 [!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]  
  

6.  Çağrı Değiştir `WaitForSingleObject` çağrısıyla [concurrency::event::wait](reference/event-class.md#wait) yöntemi görevin tamamlanmasını bekleyin.  

 [!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]  
  
7.  Çağrı kaldırmak `CloseHandle`.  
  
8.  Tanımını imzayı değiştirme `MyThreadFunction` 3. adım eşleşecek şekilde.  
  
 [!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]  
  
9. Sonunda `MyThreadFunction` işlev, çağrı [concurrency::event::set](reference/event-class.md#set) görevi tamamlandı ana uygulama sinyal yöntemi.  
  
 [!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]  
  
10. Kaldırma `return` from deyimi `MyThreadFunction`.  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki tamamlanan örnek çağırmak için basit bir görev kullanan kodu gösterir `MyThreadFunction` işlevi.  
  
### <a name="code"></a>Kod  
 [!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]  
  
### <a name="comments"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Zamanlayıcı Sınıfı](../../parallel/concrt/reference/scheduler-class.md)

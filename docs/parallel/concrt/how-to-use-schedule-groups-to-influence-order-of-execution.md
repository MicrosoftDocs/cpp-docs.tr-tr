---
title: "Nasıl yapılır: yürütme sırasını etkilemek için zamanlama grupları kullanma | Microsoft Docs"
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
- schedule groups, using [Concurrency Runtime]
- using schedule groups [Concurrency Runtime]
ms.assetid: 73124194-fc3a-491e-a23f-fbd7b5a4455c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fcb37c1c14a9d09230bfa5d4fdce1da5eddfb4f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-schedule-groups-to-influence-order-of-execution"></a>Nasıl yapılır: Yürütme Sırasını Etkilemek için Zamanlama Grupları Kullanma
Eşzamanlılık Çalışma Zamanı'nda görevler zamanlanmış sipariş belirleyici değildir. Ancak, görevleri çalıştırdığınız sırasını etkilemek için zamanlama ilkelerini kullanabilirsiniz. Bu konuda zamanlama grupları ile birlikte kullanmayı gösterir [concurrency::SchedulingProtocol](reference/concurrency-namespace-enums.md#policyelementkey) görevlerin çalıştığı sırasını etkilemek için Zamanlayıcı ilkesi.  

  
 Örnek bir dizi görevi iki kez, her farklı bir zamanlama ilkesi ile çalışır. Her iki ilkeyi iki işlem kaynakları sayısı üst sınırını. İlk çalıştırma kullanır `EnhanceScheduleGroupLocality` ilke, varsayılan ve ikinci çalıştırın kullanır `EnhanceForwardProgress` ilkesi. Altında `EnhanceScheduleGroupLocality` İlkesi, Zamanlayıcı çalışan tüm görevler bir zamanlama grubunda her görev tamamlandıktan veya verir kadar. Altında `EnhanceForwardProgress` İlkesi, Zamanlayıcı taşır sonraki zamanlama grubuna bir hepsini şekilde tek bir görev sonlandığında veya verir.  
  
 Her bir zamanlama grubu ilgili görevleri içerdiğinde `EnhanceScheduleGroupLocality` ilke önbellek yerleşim yeri görevleri arasında korunduğu için performansın genellikle sonuçlanır. `EnhanceForwardProgress` İlkesi ilerleme gerçekleştirmek görevleri sağlar ve zamanlama grupları arasında eşitliği zamanlama gerektiren durumlarda faydalıdır.  
  
## <a name="example"></a>Örnek  
 Bu örnek tanımlar `work_yield_agent` türeyen sınıf [concurrency::agent](../../parallel/concrt/reference/agent-class.md). `work_yield_agent` Sınıfı bir iş birimine gerçekleştirir, geçerli bağlam verir ve ardından başka bir iş birimine gerçekleştirir. Aracısı'nın kullandığı [concurrency::wait](reference/concurrency-namespace-functions.md#wait) işbirliği ile diğer bağlamlarda çalıştırabilmeniz için geçerli bağlamı elde etmek üzere işlevi.  
  
 Bu örnek, dört oluşturur `work_yield_agent` nesneleri. Aracıları çalıştırdığınız sırasını etkilemek için Zamanlayıcı ilkeleri ayarlamak nasıl göstermek için örnek ilk iki aracı bir zamanlama grubu ve diğer iki aracı başka bir zamanlama grubu ile ilişkilendirir. Örnek kullanır [concurrency::CurrentScheduler::CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) oluşturmak için yöntemi [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) nesneleri. Örneğin tüm dört aracıları iki kez, her zaman farklı bir zamanlama ilkesi ile çalışır.  
  
 [!code-cpp[concrt-scheduling-protocol#1](../../parallel/concrt/codesnippet/cpp/how-to-use-schedule-groups-to-influence-order-of-execution_1.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
```Output  
Using EnhanceScheduleGroupLocality...  
group 0,
    task 0: first loop...  
group 0,
    task 1: first loop...  
group 0,
    task 0: waiting...  
group 1,
    task 0: first loop...  
group 0,
    task 1: waiting...  
group 1,
    task 1: first loop...  
group 1,
    task 0: waiting...  
group 0,
    task 0: second loop...  
group 1,
    task 1: waiting...  
group 0,
    task 1: second loop...  
group 0,
    task 0: finished...  
group 1,
    task 0: second loop...  
group 0,
    task 1: finished...  
group 1,
    task 1: second loop...  
group 1,
    task 0: finished...  
group 1,
    task 1: finished...  
 
Using EnhanceForwardProgress...  
group 0,
    task 0: first loop...  
group 1,
    task 0: first loop...  
group 0,
    task 0: waiting...  
group 0,
    task 1: first loop...  
group 1,
    task 0: waiting...  
group 1,
    task 1: first loop...  
group 0,
    task 1: waiting...  
group 0,
    task 0: second loop...  
group 1,
    task 1: waiting...  
group 1,
    task 0: second loop...  
group 0,
    task 0: finished...  
group 0,
    task 1: second loop...  
group 1,
    task 0: finished...  
group 1,
    task 1: second loop...  
group 0,
    task 1: finished...  
group 1,
    task 1: finished...  
```  
  
 Her iki ilkeyi aynı olaylar dizisi üretir. Ancak, ilkeyi kullanan `EnhanceScheduleGroupLocality` ikinci grubunun parçası olan aracıları başlamadan önce ilk zamanlama grubunun parçası olan her iki aracıları başlatır. Kullanan ilke `EnhanceForwardProgress` ilk gruptan bir Aracısı başlatır ve ardından ikinci grubunda ilk Aracısı'nı başlatır.  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `scheduling-protocol.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **zamanlama cl.exe /EHsc-protocol.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zamanlama grupları](../../parallel/concrt/schedule-groups.md)   
 [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)


---
title: 'Nasıl yapılır: Yürütme sırasını etkilemek için zamanlama grupları kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- schedule groups, using [Concurrency Runtime]
- using schedule groups [Concurrency Runtime]
ms.assetid: 73124194-fc3a-491e-a23f-fbd7b5a4455c
ms.openlocfilehash: 99e0383fc8d16f3eeb6e43e59424ab0984ee5c14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367050"
---
# <a name="how-to-use-schedule-groups-to-influence-order-of-execution"></a>Nasıl yapılır: Yürütme sırasını etkilemek için zamanlama grupları kullanma

Eşzamanlılık Çalışma zamanı içinde hangi görevlerin zamanlandığı sırasını belirleyici değildir. Ancak, görevleri çalışma sırasını etkilemek için zamanlama ilkelerini kullanabilirsiniz. Bu konu ile birlikte zamanlama grupları kullanma işlemi gösterilmektedir [concurrency::SchedulingProtocol](reference/concurrency-namespace-enums.md#policyelementkey) görevleri çalıştırarak sırasını etkilemek için Zamanlayıcı ilkesini.

Örneğin, bir dizi görevi iki kez, her biri farklı bir zamanlama ilkesi çalıştırır. Her iki ilkeyi iki işlem kaynakları en fazla sayısını sınırlayın. İlk çalıştırma kullandığı `EnhanceScheduleGroupLocality` ilke, varsayılan değer olan ve ikinci çalıştırın kullandığı `EnhanceForwardProgress` ilkesi. Altında `EnhanceScheduleGroupLocality` İlkesi, Zamanlayıcı çalışan tüm görevler bir zamanlama grubundaki kadar her görev tamamlandığında veya verir. Altında `EnhanceForwardProgress` İlkesi, Zamanlayıcı taşır sonraki zamanlama grubu için bir hepsini bir kez deneme şekilde sonra yalnızca bir görev tamamlandığında veya verir.

Her zamanlama grubu ilgili görevleri içerdiğinde `EnhanceScheduleGroupLocality` İlkesi önbellek yerleşim yeri görevler arasında korunduğundan performansın genellikle sonuçlanır. `EnhanceForwardProgress` İlkesi görevlerin ilerlemesini sağlar ve zamanlama grupları arasında eşitliği zamanlama gerektiren durumlarda kullanışlıdır.

## <a name="example"></a>Örnek

Bu örnek tanımlar `work_yield_agent` türetilen sınıf [concurrency::agent](../../parallel/concrt/reference/agent-class.md). `work_yield_agent` İş birimini, geçerli bağlam verir ve ardından başka bir iş birimini sınıfı. Aracısı'nın kullandığı [concurrency::wait](reference/concurrency-namespace-functions.md#wait) işbirliği ile diğer bağlamlarda çalıştırabilmeniz için geçerli bağlam elde etmek üzere işlevi.

Bu örnekte dört oluşturur `work_yield_agent` nesneleri. Aracıları çalıştırıldığı sırasını etkilemek için Zamanlayıcı ilkeleri ayarlama işlemini göstermek için örnek ilk iki aracı bir zamanlama grubu ve diğer iki aracı başka bir zamanlama grubu ile ilişkilendirir. Örnekte [concurrency::CurrentScheduler::CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) yöntemini [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) nesneleri. Örnek, tüm dört aracılar iki kez, her zaman farklı bir zamanlama ilkesi ile çalışır.

[!code-cpp[concrt-scheduling-protocol#1](../../parallel/concrt/codesnippet/cpp/how-to-use-schedule-groups-to-influence-order-of-execution_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

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

Her iki ilkeyi aynı olayları dizisi üretir. Ancak, ilkeyi kullanan `EnhanceScheduleGroupLocality` ikinci grubunun parçası olan aracıları başlamadan önce ilk zamanlama grubu parçası olan her iki aracı başlar. Kullanan İlkesi `EnhanceForwardProgress` bir aracı ilk gruptan başlar ve ardından ikinci gruptaki ilk Aracısı'nı başlatır.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `scheduling-protocol.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**zamanlama cl.exe/ehsc-protocol.cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zamanlama Grupları](../../parallel/concrt/schedule-groups.md)<br/>
[Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)

---
title: 'Nasıl yapılır: Yürütme Sırasını Etkilemek için Zamanlama Grupları Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- schedule groups, using [Concurrency Runtime]
- using schedule groups [Concurrency Runtime]
ms.assetid: 73124194-fc3a-491e-a23f-fbd7b5a4455c
ms.openlocfilehash: 84829664603999893f32caab39af250059bf9788
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141910"
---
# <a name="how-to-use-schedule-groups-to-influence-order-of-execution"></a>Nasıl yapılır: Yürütme Sırasını Etkilemek için Zamanlama Grupları Kullanma

Eşzamanlılık Çalışma Zamanı, görevlerin zamanlandığı sıra belirleyici değildir. Ancak, görevlerin çalışma sırasını etkilemek için zamanlama ilkeleri kullanabilirsiniz. Bu konuda, görevlerin çalışma sırasını etkilemek için [concurrency:: SchedulingProtocol](reference/concurrency-namespace-enums.md#policyelementkey) Scheduler ilkesiyle birlikte zamanlama gruplarının nasıl kullanılacağı gösterilmektedir.

Örnek, her biri farklı bir zamanlama ilkesiyle iki kez bir görev kümesi çalıştırır. Her iki ilke de en fazla işlem kaynağı sayısını iki olarak sınırlar. İlk çalıştırma, varsayılan olan `EnhanceScheduleGroupLocality` ilkesini kullanır ve ikinci çalıştırma `EnhanceForwardProgress` ilkesini kullanır. `EnhanceScheduleGroupLocality` ilkesi altında Zamanlayıcı, her görev bitene veya gerçekleşene kadar bir zamanlama grubundaki tüm görevleri çalıştırır. `EnhanceForwardProgress` ilkesi altında, Zamanlayıcı bir sonraki zamanlama grubuna yalnızca bir görev bittikten veya bu şekilde bir kez daha sonra döner.

Her bir zamanlama grubu ilgili görevleri içerdiğinde `EnhanceScheduleGroupLocality` ilkesi genellikle performans artmasına neden olur çünkü önbellek konumu görevler arasında korunur. `EnhanceForwardProgress` ilkesi, görevlerin ilerleme durumuna girmesini sağlar ve zamanlama grupları arasında zamanlama eşitliği istediğinizde faydalıdır.

## <a name="example"></a>Örnek

Bu örnek, [concurrency:: Agent](../../parallel/concrt/reference/agent-class.md)öğesinden türetilen `work_yield_agent` sınıfını tanımlar. `work_yield_agent` sınıfı bir iş birimi gerçekleştirir, geçerli bağlamı verir ve sonra başka bir iş birimi gerçekleştirir. Aracı, diğer bağlamların çalıştırılabilmesi için geçerli bağlamı birlikte çalıştırmak için [concurrency:: wait](reference/concurrency-namespace-functions.md#wait) işlevini kullanır.

Bu örnek dört `work_yield_agent` nesnesi oluşturur. Zamanlayıcı ilkelerinin aracıların çalıştırıldığı sırayı etkilemek üzere nasıl ayarlanacağını göstermek için örnek, ilk iki aracıyı bir zamanlama grubuyla ve diğer iki aracıyı başka bir zamanlama grubuyla ilişkilendirir. Örnek, concurrency:: [ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) nesnelerini oluşturmak için [concurrency:: CurrentScheduler:: CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) metodunu kullanır. Örnek, her seferinde farklı bir zamanlama ilkesiyle birlikte dört aracıyı iki kez çalıştırır.

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

Her iki ilke de aynı olay dizisini üretir. Ancak `EnhanceScheduleGroupLocality` kullanan ilke, ikinci grubun parçası olan aracıları başlamadan önce ilk Zamanlama grubunun parçası olan her iki aracıyı de başlatır. `EnhanceForwardProgress` kullanan ilke ilk grubundan bir aracı başlatır ve ardından ikinci gruptaki ilk Aracıyı başlatır.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `scheduling-protocol.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc Scheduling-Protocol. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zamanlama Grupları](../../parallel/concrt/schedule-groups.md)<br/>
[Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)

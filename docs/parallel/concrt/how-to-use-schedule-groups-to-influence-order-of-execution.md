---
description: 'Daha fazla bilgi: nasıl yapılır: yürütme sırasını etkilemek için zamanlama grupları kullanma'
title: 'Nasıl yapılır: Yürütme Sırasını Etkilemek için Zamanlama Grupları Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- schedule groups, using [Concurrency Runtime]
- using schedule groups [Concurrency Runtime]
ms.assetid: 73124194-fc3a-491e-a23f-fbd7b5a4455c
ms.openlocfilehash: 28bf3e1c302e2aafe05f6670571c1f07c2f0136d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205687"
---
# <a name="how-to-use-schedule-groups-to-influence-order-of-execution"></a>Nasıl yapılır: Yürütme Sırasını Etkilemek için Zamanlama Grupları Kullanma

Eşzamanlılık Çalışma Zamanı, görevlerin zamanlandığı sıra belirleyici değildir. Ancak, görevlerin çalışma sırasını etkilemek için zamanlama ilkeleri kullanabilirsiniz. Bu konuda, görevlerin çalışma sırasını etkilemek için [concurrency:: SchedulingProtocol](reference/concurrency-namespace-enums.md#policyelementkey) Scheduler ilkesiyle birlikte zamanlama gruplarının nasıl kullanılacağı gösterilmektedir.

Örnek, her biri farklı bir zamanlama ilkesiyle iki kez bir görev kümesi çalıştırır. Her iki ilke de en fazla işlem kaynağı sayısını iki olarak sınırlar. İlk çalıştırma, `EnhanceScheduleGroupLocality` varsayılan olan ilkeyi kullanır ve ikinci çalıştırma `EnhanceForwardProgress` ilkeyi kullanır. İlke altında `EnhanceScheduleGroupLocality` Zamanlayıcı, her görev bitene veya gerçekleşene kadar bir zamanlama grubundaki tüm görevleri çalıştırır. İlke altında `EnhanceForwardProgress` , Zamanlayıcı bir sonraki zamanlama grubuna yalnızca bir görev bittikten veya bu şekilde bir kez daha sonra döner.

Her bir zamanlama grubu ilgili görevleri içerdiğinde, `EnhanceScheduleGroupLocality` Görevler arasında önbellek konumu korunduğu için ilke genellikle performansın artmasına neden olur. `EnhanceForwardProgress`İlke, görevlerin ilerleme durumuna girmesini sağlar ve zamanlama grupları arasında zamanlama eşitliği istediğinizde faydalıdır.

## <a name="example"></a>Örnek

Bu örnek `work_yield_agent` , [concurrency:: Agent](../../parallel/concrt/reference/agent-class.md)öğesinden türetilen sınıfı tanımlar. `work_yield_agent`Sınıfı bir iş birimi gerçekleştirir, geçerli bağlamı verir ve sonra başka bir iş birimi gerçekleştirir. Aracı, diğer bağlamların çalıştırılabilmesi için geçerli bağlamı birlikte çalıştırmak için [concurrency:: wait](reference/concurrency-namespace-functions.md#wait) işlevini kullanır.

Bu örnek dört `work_yield_agent` nesne oluşturur. Zamanlayıcı ilkelerinin aracıların çalıştırıldığı sırayı etkilemek üzere nasıl ayarlanacağını göstermek için örnek, ilk iki aracıyı bir zamanlama grubuyla ve diğer iki aracıyı başka bir zamanlama grubuyla ilişkilendirir. Örnek, concurrency:: [ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) nesnelerini oluşturmak için [concurrency:: CurrentScheduler:: CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) metodunu kullanır. Örnek, her seferinde farklı bir zamanlama ilkesiyle birlikte dört aracıyı iki kez çalıştırır.

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

Her iki ilke de aynı olay dizisini üretir. Ancak, kullanan ilke `EnhanceScheduleGroupLocality` ikinci grubun parçası olan aracıları başlamadan önce ilk Zamanlama grubunun parçası olan aracıları başlatır. Tarafından kullanılan ilke `EnhanceForwardProgress` ilk grubundan bir aracı başlatır ve ardından ikinci gruptaki ilk Aracıyı başlatır.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `scheduling-protocol.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Scheduling-Protocol. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zamanlama grupları](../../parallel/concrt/schedule-groups.md)<br/>
[Zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)

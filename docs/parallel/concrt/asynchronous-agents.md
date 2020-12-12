---
description: 'Daha fazla bilgi edinin: zaman uyumsuz aracılar'
title: Zaman Uyumsuz Aracılar
ms.date: 11/19/2018
helpviewer_keywords:
- asynchronous agents
- agents [Concurrency Runtime]
ms.assetid: 6cf6ccc6-87f1-4e14-af15-ea8ba58fef1a
ms.openlocfilehash: 38d2325404d83443ed0bd054793ca200a562359f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338289"
---
# <a name="asynchronous-agents"></a>Zaman Uyumsuz Aracılar

*Zaman uyumsuz bir aracı* (veya yalnızca *Aracı*), daha büyük bilgi işlem görevlerini çözümlemek için diğer aracılarla zaman uyumsuz olarak çalışan bir uygulama bileşenidir. Bir aracıyı, belirlenen yaşam döngüsü olan bir görev olarak düşünün. Örneğin, bir aracı bir giriş/çıkış cihazından (klavye, diskteki bir dosya veya ağ bağlantısı gibi) verileri okuyabilir ve başka bir aracı, kullanılabilir olduğunda bu veriler üzerinde işlem gerçekleştirebilir. İlk aracı ikinci aracıya daha fazla veri kullanılabildiğini bildirmek için ileti geçirme kullanır. Eşzamanlılık Çalışma Zamanı Görev Zamanlayıcı, aracıların daha az verimli önalım gerekmeden, aracıları engellemesini ve kullanmasını sağlamak için verimli bir mekanizma sağlar.

Aracılar Kitaplığı, zaman uyumsuz bir aracıyı temsil etmek için [concurrency:: Agent](../../parallel/concrt/reference/agent-class.md) sınıfını tanımlar. `agent` , [concurrency:: Agent:: Run](reference/agent-class.md#run)sanal metodunu bildiren soyut bir sınıftır. `run`Yöntemi, aracı tarafından gerçekleştirilen görevi yürütür. `run`Soyut olduğundan, bu yöntemi içinden türettiğiniz her sınıfta uygulamanız gerekir `agent` .

## <a name="agent-life-cycle"></a>Aracı yaşam döngüsü

Aracıların ayarlanmış bir yaşam döngüsü vardır. [Concurrency:: agent_status](reference/concurrency-namespace-enums.md#agent_status) numaralandırması bir aracının çeşitli durumlarını tanımlar. Aşağıdaki çizim, aracıların bir durumdan diğerine ilerleme durumunu gösteren bir durum diyagramıdır. Bu çizimde, düz çizgiler uygulamanızdan çağırdığınız yöntemleri temsil eder; noktalı çizgiler, çalışma zamanından çağrılan yöntemleri temsil eder.

![Aracı durumu diyagramı](../../parallel/concrt/media/agentstate.png "Aracı durumu diyagramı")

Aşağıdaki tabloda, Numaralandırmadaki her durum açıklanmaktadır `agent_status` .

|Aracı durumu|Açıklama|
|-----------------|-----------------|
|`agent_created`|Aracı yürütme için zamanlanmamış.|
|`agent_runnable`|Çalışma zamanı aracıyı yürütme için zamanlıyor.|
|`agent_started`|Aracı başlatıldı ve çalışıyor.|
|`agent_done`|Aracı bitti.|
|`agent_canceled`|Aracı, durumu girmeden önce iptal edildi `started` .|

`agent_created` , bir aracının başlangıç durumudur `agent_runnable` ve `agent_started` etkin durumlardır ve, `agent_done` `agent_canceled` Terminal durumlarıdır.

Bir nesnenin geçerli durumunu almak için [concurrency:: Agent:: Status](reference/agent-class.md#status) metodunu kullanın `agent` . `status`Yöntemi eşzamanlılık açısından güvenli olsa da, aracının durumu yöntemin döndürdüğü zamana göre değişebilir `status` . Örneğin, `agent_started` yöntemini çağırdığınızda bir aracı durumunda olabilir `status` , ancak `agent_done` yöntemin döndürdüğü hemen sonra duruma taşınır `status` .

## <a name="methods-and-features"></a>Yöntemler ve Özellikler

Aşağıdaki tabloda sınıfına ait olan önemli yöntemlerin bazıları gösterilmektedir `agent` . Tüm sınıf yöntemleri hakkında daha fazla bilgi için `agent` bkz. [Aracı sınıfı](../../parallel/concrt/reference/agent-class.md).

|Yöntem|Açıklama|
|------------|-----------------|
|[başından](reference/agent-class.md#start)|`agent`Yürütmek için nesneyi zamanlar ve durumu olarak ayarlar `agent_runnable` .|
|[çalışmaz](reference/agent-class.md#run)|Nesnesi tarafından gerçekleştirilecek görevi yürütür `agent` .|
|[bitti](reference/agent-class.md#done)|Bir aracıyı `agent_done` duruma kaydırır.|
|[İptal](../../parallel/concrt/cancellation-in-the-ppl.md#cancel)|Aracı başlatılmamışsa, bu yöntem aracının yürütülmesini iptal eder ve `agent_canceled` duruma getirir.|
|[durumlarına](reference/agent-class.md#status)|Nesnenin geçerli durumunu alır `agent` .|
|[bekleneceğini](reference/agent-class.md#wait)|`agent`Nesnenin veya durumunun girilmesi için bekler `agent_done` `agent_canceled` .|
|[wait_for_all](reference/agent-class.md#wait_for_all)|Tüm sağlanmış `agent` nesnelerin `agent_done` veya durumunu girmesini bekler `agent_canceled` .|
|[wait_for_one](reference/agent-class.md#wait_for_one)|Belirtilen nesnelerden en az birinin `agent` veya durumun girilmesi için bekler `agent_done` `agent_canceled` .|

Bir aracı nesnesi oluşturduktan sonra, yürütme için zamanlamak üzere [concurrency:: Agent:: Start](reference/agent-class.md#start) metodunu çağırın. Çalışma zamanı `run` aracıyı zamanladıktan sonra yöntemi çağırır ve durumu olarak ayarlar `agent_runnable` .

Çalışma zamanı, zaman uyumsuz aracılar tarafından oluşturulan özel durumları yönetmez. Özel durum işleme ve aracıları hakkında daha fazla bilgi için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

## <a name="example"></a>Örnek

Temel aracı tabanlı bir uygulamanın nasıl oluşturulacağını gösteren bir örnek için bkz. [Izlenecek yol: Agent-Based uygulama oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)

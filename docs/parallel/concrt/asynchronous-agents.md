---
title: Zaman Uyumsuz Aracılar
ms.date: 11/04/2016
helpviewer_keywords:
- asynchronous agents
- agents [Concurrency Runtime]
ms.assetid: 6cf6ccc6-87f1-4e14-af15-ea8ba58fef1a
ms.openlocfilehash: 949074981d77702fd23ee3ff70f219c013fa6543
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467606"
---
# <a name="asynchronous-agents"></a>Zaman Uyumsuz Aracılar

Bir *zaman uyumsuz aracılar* (veya yalnızca *aracı*) daha büyük bilgi işlem görevlerini çözümlemek için diğer aracıları ile zaman uyumsuz olarak çalışan bir uygulama bileşeni. Bir aracının ayarlanmış bir ömrü olan bir görev olarak düşünün. Örneğin, bir aracı kullanılabilir olduğunda (örneğin, klavye, disk üzerindeki bir dosya veya bir ağ bağlantısı) bir giriş/çıkış cihaz ve başka bir aracı verilerini bu veriler üzerinde eylem gerçekleştirebilir okuyabilir. İlk aracı ileti geçirme ikinci aracı daha fazla veri kullanılabilir olduğunu bildirmek için kullanır. Eşzamanlılık Çalışma zamanı Görev Zamanlayıcısı'nı engelleyin ve işbirliği içerisinde devamlılığı yield aracıları etkinleştirmek üzere etkili bir mekanizma sağlar. daha az verimli önalım gerektirmeden.

Agents kitaplığı tanımlar [concurrency::agent](../../parallel/concrt/reference/agent-class.md) zaman uyumsuz bir Aracıdan temsil eden sınıf. `agent` bildiren sanal yöntemi soyut bir sınıf olan [concurrency::agent::run](reference/agent-class.md#run). `run` Aracı tarafından gerçekleştirilen görevin yöntemini yürütür. Çünkü `run` olan soyut, bu yöntem, türetilen her bir sınıf içinde uygulamanız gerekir `agent`.

## <a name="agent-life-cycle"></a>Aracı yaşam döngüsü

Aracıları ayarlanmış bir yaşam döngüsü vardır. [Concurrency::agent_status](reference/concurrency-namespace-enums.md#agent_status) numaralandırması bir aracının çeşitli durumları tanımlar. Aşağıdaki resimde, nasıl aracıları bir durumdan diğerine ilerleme durumu gösteren bir durum diyagramı verilmiştir. Bu çizimde, düz çizgiler uygulamanızdan çağıran yöntemleri gösterir; noktalı çizgiler çalışma zamanını şuradan çağıran yöntemleri gösterir.

![Aracı durumu diyagramını](../../parallel/concrt/media/agentstate.png "agentstate")

Aşağıdaki tabloda her durumda açıklanmaktadır `agent_status` sabit listesi.

|Aracı durumu|Açıklama|
|-----------------|-----------------|
|`agent_created`|Aracı yürütme için zamanlanan değil.|
|`agent_runnable`|Çalışma zamanı aracı yürütme için zamanlama olduğu.|
|`agent_started`|Aracıyı başlatıldı ve çalışıyor.|
|`agent_done`|Aracı işlemi tamamlandı.|
|`agent_canceled`|Aracıyı girdiği önce iptal edildi `started` durumu.|

`agent_created` bir aracı ilk durumu `agent_runnable` ve `agent_started` etkin durumlar ve `agent_done` ve `agent_canceled` terminal durumlarıdır.

Kullanım [concurrency::agent::status](reference/agent-class.md#status) yönteminin geçerli durumunu almak için bir `agent` nesne. Ancak `status` yöntemidir, eşzamanlılık açısından güvenli, aracının durumunu zaman değiştirebilirsiniz `status` yöntemi döndürür. Örneğin, içinde bir aracı olabilir `agent_started` çağırdığınızda durumu `status` yöntemi, ancak taşınabilir `agent_done` hemen sonrasına durum `status` yöntemi döndürür.

## <a name="methods-and-features"></a>Yöntemleri ve özellikleri

Aşağıdaki tabloda ait önemli yöntemlerden bazıları gösterilmektedir `agent` sınıfı. Tüm hakkında daha fazla bilgi için `agent` sınıfı yöntemleri [agent sınıfı](../../parallel/concrt/reference/agent-class.md).

|Yöntem|Açıklama|
|------------|-----------------|
|[Başlangıç](reference/agent-class.md#start)|Zamanlamalar `agent` yürütme için nesne ve ayarlar `agent_runnable` durumu.|
|[Çalıştırma](reference/agent-class.md#run)|Tarafından gerçekleştirilmesi gereken görev yürütülmeden `agent` nesne.|
|[Bitti](reference/agent-class.md#done)|Aracıya taşır `agent_done` durumu.|
|[İptal](../../parallel/concrt/cancellation-in-the-ppl.md#cancel)|Aracı başlatılmadıysa, bu yöntem aracısının yürütme iptal eder ve ayarlar `agent_canceled` durumu.|
|[Durumu](reference/agent-class.md#status)|Geçerli durumunu alır `agent` nesne.|
|[bekleme](reference/agent-class.md#wait)|Bekler `agent` girmek için nesne `agent_done` veya `agent_canceled` durumu.|
|[wait_for_all](reference/agent-class.md#wait_for_all)|Sağlanan tüm bekler `agent` girmek için nesneleri `agent_done` veya `agent_canceled` durumu.|
|[wait_for_one](reference/agent-class.md#wait_for_one)|En az biri sağlanan için bekleyeceği `agent` girmek için nesneleri `agent_done` veya `agent_canceled` durumu.|

Bir aracı nesnesi oluşturduktan sonra çağrı [concurrency::agent::start](reference/agent-class.md#start) yürütme için zamanlamak için yöntemi. Çalışma zamanı çağrıları `run` aracı zamanlar ve ayarlar sonra yöntemi `agent_runnable` durumu.

Çalışma zamanı zaman uyumsuz aracılar tarafından oluşturulan özel durumları yönetmez. Aracıları ve özel durum işleme hakkında daha fazla bilgi için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

## <a name="example"></a>Örnek

Temel bir aracı tabanlı uygulamanın nasıl oluşturulacağını gösteren bir örnek için bkz: [izlenecek yol: aracı temelli uygulama oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)


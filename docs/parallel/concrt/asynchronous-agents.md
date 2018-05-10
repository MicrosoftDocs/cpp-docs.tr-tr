---
title: Zaman uyumsuz aracılar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- asynchronous agents
- agents [Concurrency Runtime]
ms.assetid: 6cf6ccc6-87f1-4e14-af15-ea8ba58fef1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8649ebe0451e4352b27989563a1a0918afcb5a01
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="asynchronous-agents"></a>Zaman Uyumsuz Aracılar
Bir *zaman uyumsuz Aracısı* (veya yalnızca *Aracısı*) zaman uyumsuz olarak daha büyük hesaplama görevlerini çözümlemek için diğer aracıları ile çalışan bir uygulama bileşenidir. Bir aracı olarak ayarlanmış bir yaşam döngüsü sahip bir görev olarak düşünün. Örneğin, bir aracı kullanılabilir olduğunda (örneğin, klavye, disk üzerindeki bir dosya veya bir ağ bağlantısı) bir giriş/çıkış aygıtı ve başka bir aracı veri eylem bu veriler üzerinde gerçekleştirebileceğiniz okuyabilir. İlk aracı ileti geçirme ikinci Aracısı daha fazla veri kullanılabilir olduğunu bildirmek üzere kullanır. Eşzamanlılık Çalışma zamanı Görev Zamanlayıcısı'nı engellemek ve işbirliği ile elde etmek aracıları etkinleştirmek için etkili bir mekanizma sağlar daha az verimli önalım gerektirmeden.  
  

 Aracılar Kitaplığı tanımlar [concurrency::agent](../../parallel/concrt/reference/agent-class.md) zaman uyumsuz bir aracı temsil eden sınıf. `agent` sanal bir yöntem bildiren bir Özet sınıf [concurrency::agent::run](reference/agent-class.md#run). `run` Yöntemi aracı tarafından gerçekleştirilen görevin yürütür. Çünkü `run` olan Özet, bu yöntem öğesinden türetilen her sınıfında uygulamanız gereken `agent`.  
  
## <a name="agent-life-cycle"></a>Aracı yaşam döngüsü  
 Aracıları ayarlanmış bir ömrü vardır. [Concurrency::agent_status](reference/concurrency-namespace-enums.md#agent_status) numaralandırma bir aracı çeşitli durumlarını tanımlar. Aşağıdaki çizimde nasıl aracıları bir durumdan diğerine ilerleme gösteren bir durum diyagramıdır. Bu çizimde, Kesiksiz çizgi uygulamanızdan çağıran yöntemlerini temsil eder; noktalı çizgiler çalışma zamanını şuradan adlı yöntemleri temsil eder.  
  
 ![Aracı durumu diyagramı](../../parallel/concrt/media/agentstate.png "agentstate")  
  
 Aşağıdaki tabloda her durumda açıklanmaktadır `agent_status` numaralandırması.  
  
|Aracı durumu|Açıklama|  
|-----------------|-----------------|  
|`agent_created`|Aracı yürütme için zamanlanmadı.|  
|`agent_runnable`|Çalışma zamanı aracı yürütme için planlama.|  
|`agent_started`|Aracı başlatıldı ve çalışıyor.|  
|`agent_done`|Aracı işlemi bitti.|  
|`agent_canceled`|Aracı girdiği önce iptal edildi `started` durumu.|  
  
 `agent_created` bir aracı ilk durumda `agent_runnable` ve `agent_started` etkin durum ve `agent_done` ve `agent_canceled` terminal durumlarıdır.  
  
 Kullanım [concurrency::agent::status](reference/agent-class.md#status) yöntemi geçerli durumunu almak için bir `agent` nesnesi. Ancak `status` eşzamanlılık güvenli yöntemdir, aracının durumunu zamanına göre değiştirebilirsiniz `status` yöntemi döndürür. Örneğin, bir aracı olabilir. `agent_started` çağırdığınızda durumu `status` yöntemi, ancak taşınabilir `agent_done` hemen sonra durum `status` yöntemi döndürür.  

  
## <a name="methods-and-features"></a>Yöntemleri ve özellikleri  
 Aşağıdaki tabloda ait önemli yöntemlerin bazıları gösterilmektedir `agent` sınıfı. Tüm hakkında daha fazla bilgi için `agent` sınıfı yöntemlerinin, bkz: [Aracısı sınıfı](../../parallel/concrt/reference/agent-class.md).  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Başlat](reference/agent-class.md#start)|Zamanlamalar `agent` yürütmenin nesne ve ayarlar `agent_runnable` durumu.|  
|[çalıştırma](reference/agent-class.md#run)|Tarafından gerçekleştirilmesi gereken görevi yürütür `agent` nesnesi.|  
|[Bitti](reference/agent-class.md#done)|Bir aracı taşır `agent_done` durumu.|  
|[İptal](../../parallel/concrt/cancellation-in-the-ppl.md#cancel)|Aracıya başlatılmamışsa, bu yöntem Yürütme Aracısı'nın iptal eder ve ayarlar `agent_canceled` durumu.|  
|[Durumu](reference/agent-class.md#status)|Geçerli durumunu alır `agent` nesnesi.|  
|[bekleme](reference/agent-class.md#wait)|Bekler `agent` girmek için nesne `agent_done` veya `agent_canceled` durumu.|  
|[wait_for_all](reference/agent-class.md#wait_for_all)|Sağlanan tüm bekler `agent` girmek için nesneleri `agent_done` veya `agent_canceled` durumu.|  
|[wait_for_one](reference/agent-class.md#wait_for_one)|En az biri sağlanan için bekleyeceği `agent` girmek için nesneleri `agent_done` veya `agent_canceled` durumu.|  
  
 Bir aracı nesne oluşturduktan sonra arama [concurrency::agent::start](reference/agent-class.md#start) çalıştırılmak üzere zamanlamak için yöntem. Çalışma zamanı çağrıları `run` aracı zamanlar ve ayarlar sonra yöntemi `agent_runnable` durumu.  
  
 Çalışma zamanı zaman uyumsuz aracılar tarafından oluşturulan özel durumları yönetmez. Aracıları ve özel durum işleme hakkında daha fazla bilgi için bkz: [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
## <a name="example"></a>Örnek  
 Temel bir aracı temelli uygulama oluşturmayı gösteren bir örnek için bkz: [izlenecek yol: aracı temelli uygulama oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)


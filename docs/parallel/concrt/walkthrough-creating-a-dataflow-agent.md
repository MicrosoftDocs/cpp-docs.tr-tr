---
title: 'İzlenecek yol: bir veri akışı Aracısı oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- creating dataflow agents [Concurrency Runtime]
- dataflow agents, creating [Concurrency Runtime]
ms.assetid: 9db5ce3f-c51b-4de1-b79b-9ac2a0cbd130
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33f7c7cf5e64d2ddf751bb97ee1b617d09df6af3
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693100"
---
# <a name="walkthrough-creating-a-dataflow-agent"></a>İzlenecek Yol: Veri Akışı Aracısı Oluşturma
Bu belgede denetim akışı yerine veri akışı dayalı tabanlı aracı uygulamalarının nasıl oluşturulacağını gösterir.  
  
 *Denetim akışı* işlem bir program yürütme sırasını başvuruyor. Denetim akışı denetim yapıları koşullu deyimler, döngüler vb. gibi kullanılarak düzenlenir. Alternatif olarak, *veri akışı* içinde hesaplamalar yapılma yalnızca gerekli tüm verileri kullanılabilir olmadığında bir programlama modeli başvuruyor. Veri akışı programlama modeli ileti geçirme, kavramı, bağımsız bir program bileşenlerinin iletileri göndererek birbirleriyle ilişkilidir.  
  
 Zaman uyumsuz aracılar akış denetimi ve veri akışı modellerini programlama destekler. Denetim akışı modeli çoğu durumda uygun olsa da, bir aracı verileri alır ve bu verileri yükü üzerinde temel bir eylem gerçekleştirir veri akışı bazı durumlarda, örneğin, uygun modelidir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuza başlamadan önce aşağıdaki belgeleri okuyun:  
  
- [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)  
  
- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)  
  
- [Nasıl yapılır: İleti Bloğu Filtresini Kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
##  <a name="top"></a> Bölümler  
 Bu kılavuz aşağıdaki bölümleri içerir:  
  
- [Temel denetim akışı Aracısı oluşturma](#control-flow)  
  
- [Temel veri akışı Aracısı oluşturma](#dataflow)  
  
- [İleti günlüğe kaydetme aracı oluşturma](#logging)  
  
##  <a name="control-flow"></a> Temel denetim akışı Aracısı oluşturma  
 Tanımlar aşağıdaki örneği göz önünde bulundurun `control_flow_agent` sınıfı. `control_flow_agent` Üç ileti arabellek sınıfı davranır: bir giriş arabelleği ve iki arabellekleri çıktı. `run` Yöntemi döngü kaynak ileti arabelleği okur ve program yürütme akışını yönlendirmek için bir koşullu ifade kullanır. Aracı sıfır, negatif değerleri için bir sayaç artırılır ve sıfır olmayan pozitif değerler için başka bir sayaç artırılır. Aracı sentinel değerin sıfır aldıktan sonra çıktı ileti arabelleklerinin sayaçların değerleri gönderir. `negatives` Ve `positives` yöntemleri pozitif ve negatif değerleri sayar Aracıdan okumak uygulama etkinleştir.  
  
 [!code-cpp[concrt-dataflow-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_1.cpp)]  
  
 Bu örnek bir aracıyı denetim akışı temel kullanımını yapar ancak denetim akış tabanlı programlama seri yapısını gösterir. Birden çok ileti giriş iletisi arabellekte kullanılabilir olsa bile her ileti ardışık olarak işlenmesi gerekir. Veri akışı modelini hem dalları eşzamanlı olarak değerlendirmek için koşullu deyiminin sağlar. Veri akışı modelini kullanılabilir hale geldiğinde, verilerde işlem yapmak daha karmaşık Mesajlaşma ağlar oluşturmanızı sağlar.  
  
 [[Üst](#top)]  
  
##  <a name="dataflow"></a> Temel veri akışı Aracısı oluşturma  
 Bu bölümde nasıl dönüştürüleceğini gösterir `control_flow_agent` aynı görevi gerçekleştirmek için veri akışı modelini kullanmak için sınıf.  
  
 Veri akışı Aracısı her biri belirli bir amaca hizmet eder ağ ileti arabelleklerinin oluşturarak çalışır. Belirli ileti blokları kabul edin veya reddedin yük temel alınarak bir ileti için bir filtre işlevini kullanın. Filter işlevi bir ileti bloğu yalnızca belirli değerlerin almasını sağlar.  
  
#### <a name="to-convert-the-control-flow-agent-to-a-dataflow-agent"></a>Denetim akışı aracısını bir veri akışı aracısına dönüştürmek için  
  
1.  Gövdesini kopyalama `control_flow_agent` başka bir sınıf sınıfına `dataflow_agent`. Alternatif olarak, adlandırabilirsiniz `control_flow_agent` sınıfı.  
  
2.  Çağıran döngü gövdesine kaldırmak `receive` gelen `run` yöntemi.  
  
 [!code-cpp[concrt-dataflow-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_2.cpp)]  
  
3.  İçinde `run` değişkenleri başlatma sonrasında yöntemi `negative_count` ve `positive_count`, ekleme bir `countdown_event` etkin işlemleri sayısını izler nesnesi.  
  
 [!code-cpp[concrt-dataflow-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_3.cpp)]  
  
     `countdown_event` Sınıfı, bu konunun devamında gösterilir.  
  
4.  İleti alacak arabellek nesneleri veri akışı ağ oluşturun.  
  
 [!code-cpp[concrt-dataflow-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_4.cpp)]  
  
5.  Bir ağ oluşturmak için ileti arabelleklerinin bağlayın.  
  
 [!code-cpp[concrt-dataflow-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_5.cpp)]  
  
6.  Bekle `event` ve `countdown event` ayarlanacak nesneleri. Bu olaylar, aracı sentinel değer aldı ve tüm işlemlerin tamamlandığından emin işaret eder.  
  
 [!code-cpp[concrt-dataflow-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_6.cpp)]  
  
 Aşağıdaki diyagramda tam veri akışı ağ gösterilmektedir `dataflow_agent` sınıfı:  
  
 ![Veri akışı ağ](../../parallel/concrt/media/concrt_dataflow.png "concrt_dataflow")  
  
 Aşağıdaki tabloda ağ üyeleri açıklanmaktadır.  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`increment_active`|A [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) etkin olay sayaç artırılır ve ağın geri kalanı için giriş değeri aktaran nesnesi.|  
|`negatives`, `positives`|[CONCURRENCY::call](../../parallel/concrt/reference/call-class.md) etkin olay sayaç numaraları ve azaltır sayısı Artır nesneleri. Negatif sayılar veya pozitif sayıları kabul etmek için bir filtre her nesneleri kullanın.|  
|`sentinel`|A [concurrency::call](../../parallel/concrt/reference/call-class.md) yalnızca sentinel değeri sıfır azaltır ve etkin olay sayaç kabul eden nesne.|  
|`connector`|A [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) kaynak ileti arabelleği iç ağa bağlanır nesnesi.|  
  
 Çünkü `run` yöntemi, ayrı bir iş parçacığı üzerinde çağrılır, ağın tam olarak bağlı önce başka bir iş parçacığı ağa iletileri gönderebilir. `_source` Veri üyesi olan bir `unbounded_buffer` aracı uygulamaya gönderilen tüm giriş arabelleği nesnesi. Tüm giriş iletileri ağ işler, aracı öncelikle iç ağ düğümlerinin bağlar ve o ağ başlangıcı bağlar emin olmak için `connector`, `_source` veri üyesi. Bu ağ biçimlendirilmiş olarak iletileri işlenmedi olduğunu güvence altına alır.  
  
 Bu örnekte ağ üzerinde veri akışı dayandığından, yerine denetim akışı üzerinde ağ aracıya her giriş değeri işleme sona erdi ve sentinel düğüm değerini aldı iletişim kurması gerekir. Bu örnekte bir `countdown_event` tüm giriş değerlerini işlenen sinyal nesnesine ve [concurrency::event](../../parallel/concrt/reference/event-class.md) sentinel düğüm değerini aldığını gösteren nesne. `countdown_event` Sınıfını kullanan bir `event` bir sayaç değeri sıfır ulaştığında sinyal nesnesi. Olan bir değer alışında veri akışı ağ head sayaç artırılır. Ağ azaltır terminal her düğümünün giriş değeri işledikten sonra sayacı. Veri akışı ağ aracısı oluşturur sonra ayarlamak sentinel düğümü için bekleyeceği `event` nesne ve `countdown_event` kendi sayaç sıfır ulaştı sinyal nesne.  
  
 Aşağıdaki örnekte gösterildiği `control_flow_agent`, `dataflow_agent`, ve `countdown_event` sınıfları. `wmain` İşlev oluşturur bir `control_flow_agent` ve `dataflow_agent` nesne ve kullandığı `send_values` aracılara rastgele değerler dizisini göndermek için işlevi.  
  
 [!code-cpp[concrt-dataflow-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_7.cpp)]  
  
 Bu örnekte aşağıdaki örnek çıkışı üretir:  
  
```Output  
Control-flow agent:  
There are 500523 negative numbers.  
There are 499477 positive numbers.  
Dataflow agent:  
There are 500523 negative numbers.  
There are 499477 positive numbers.  
```  
  
### <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `dataflow-agent.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc veri akışı-agent.cpp**  
  
 [[Üst](#top)]  
  
##  <a name="logging"></a> İleti günlüğe kaydetme aracı oluşturma  
 Aşağıdaki örnekte gösterildiği `log_agent` benzer sınıfı `dataflow_agent` sınıfı. `log_agent` Sınıfı zaman uyumsuz günlük aracıyı yazma iletiler bir dosyaya ve konsola oturum uygular. `log_agent` Sınıfı olarak bilgi, uyarı veya hata kategorilere ayırmak uygulama sağlar. Ayrıca, her günlük kategori bir dosya, konsol veya her ikisini de mi yazılacağını belirtmek uygulama sağlar. Bu örnekte tüm günlük iletileri bir dosyaya ve yalnızca hata iletilerini konsola yazar.  
  
 [!code-cpp[concrt-log-filter#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_8.cpp)]  
  
 Bu örnekte aşağıdaki çıktıyı konsola yazar.  
  
```Output  
error: This is a sample error message.  
```  
  
 Bu örnek ayrıca aşağıdaki metni içeren log.txt dosyasını üretir.  
  
```Output  
info: ===Logging started.=== 
warning: This is a sample warning message.  
error: This is a sample error message.  
info: ===Logging finished.=== 
```  
  
### <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `log-filter.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc günlük-filter.cpp**  
  
 [[Üst](#top)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)


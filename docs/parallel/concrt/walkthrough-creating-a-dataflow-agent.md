---
title: 'İzlenecek yol: Bir veri akışı Aracısı oluşturma'
ms.date: 04/25/2019
helpviewer_keywords:
- creating dataflow agents [Concurrency Runtime]
- dataflow agents, creating [Concurrency Runtime]
ms.assetid: 9db5ce3f-c51b-4de1-b79b-9ac2a0cbd130
ms.openlocfilehash: bba72404b1c39ef1835b0c96883154b385181b6a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378285"
---
# <a name="walkthrough-creating-a-dataflow-agent"></a>İzlenecek yol: Bir veri akışı Aracısı oluşturma

Bu belgede denetim akışı yerine veri akışı temel alan aracı tabanlı uygulamalarının nasıl oluşturulacağını gösterir.

*Denetim akışı* işlemleri bir programda uygulanma sırası ifade eder. Denetim akışı koşullu deyimleri, döngüler ve benzeri gibi denetim yapıları kullanarak düzenlenir. Alternatif olarak, *veri akışı* içinde hesaplamalar yapılan yalnızca, tüm gerekli veriler kullanılabilir bir programlama modeli ifade eder. Veri akışı programlama modeli içinde bir program bağımsız bileşenlerinin birbirleriyle iletiler göndererek iletişim kurması kavramı, ileti geçirme, ilişkilidir.

Zaman uyumsuz aracılar denetim akışı ve veri akışı programlama modellerini destekler. Denetim akışı modeli çoğu durumda uygun olsa da, bir aracı verileri alır ve bu verilerin yükünü bağlı bir eylem gerçekleştiren veri akışı modelini bazı durumlarda, örneğin, uygundur.

## <a name="prerequisites"></a>Önkoşullar

Bu kılavuza başlamadan önce aşağıdaki belgeleri okuyun:

- [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [Nasıl yapılır: İleti Bloğu Filtresini Kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)

##  <a name="top"></a> Bölümleri

Bu izlenecek yol aşağıdaki bölümleri içerir:

- [Temel denetim akışı Aracısı oluşturma](#control-flow)

- [Temel bir veri akışı Aracısı oluşturma](#dataflow)

- [İleti günlüğü Aracısı oluşturma](#logging)

##  <a name="control-flow"></a> Temel denetim akışı Aracısı oluşturma

Tanımlar aşağıdaki örneği inceleyin `control_flow_agent` sınıfı. `control_flow_agent` Üç ileti arabellek sınıfı davranır: bir giriş arabellek ve iki arabellek çıktı. `run` Yöntemi döngü içinde kaynak ileti arabelleği okur ve, program yürütmenin akışını yönlendirmek için bir koşullu ifade kullanır. Aracı, sıfır olmayan, negatif değerler için bir sayaç artırılır ve sıfır olmayan pozitif değerler için başka bir sayaç artırılır. Aracısı sentinel değeri sıfır aldıktan sonra çıkış ileti arabellekleri için sayaç değerlerini gönderir. `negatives` Ve `positives` yöntemleri aracı sayısı negatif ve pozitif değerleri okumak uygulamayı etkinleştirin.

[!code-cpp[concrt-dataflow-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_1.cpp)]

Bu örnek bir aracıyı denetim akışı temel kullanımını yapar ancak denetim akış tabanlı programlama seri yapısını gösterir. Birden çok ileti giriş iletisi arabellekteki kullanılabilir olsa bile her ileti ardışık olarak işlenmesi gerekir. Veri akışı modelini, her iki dalda eşzamanlı olarak değerlendirmek için koşullu deyimin sağlar. Veri akışı modelini, kullanılabilir olduğunda, veri üzerinde oynama yapmak daha karmaşık bir Mesajlaşma ağlar oluşturmanıza olanak sağlar.

[[Üst](#top)]

##  <a name="dataflow"></a> Temel bir veri akışı Aracısı oluşturma

Bu bölümde nasıl dönüştürüleceğini gösterir `control_flow_agent` aynı görevi gerçekleştirmek için veri akışı modelini kullanmak için sınıf.

Veri akışı Aracısı, her biri belirli bir amaca hizmet veren bir ağ ileti arabelleklerinin oluşturarak çalışır. Belirli bir ileti blokları, kabul etme veya reddetme yük boyutuna göre bir ileti için bir filtre işlevi kullanın. Bir filtre işlevi, bir ileti bloğu yalnızca belirli değerleri almasını sağlar.

#### <a name="to-convert-the-control-flow-agent-to-a-dataflow-agent"></a>Denetim akışı aracısını bir veri akışı aracısına dönüştürmek için

1. Gövdesi kopyalama `control_flow_agent` başka bir sınıf sınıfına `dataflow_agent`. Alternatif olarak, adlandırabilirsiniz `control_flow_agent` sınıfı.

1. Çağıran döngünün gövdesini kaldırın `receive` gelen `run` yöntemi.

[!code-cpp[concrt-dataflow-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_2.cpp)]

1. İçinde `run` değişkenlerin başlatmadan sonra bir yöntem `negative_count` ve `positive_count`, ekleme bir `countdown_event` etkin işlemleri sayısı izleyen bir nesne.

[!code-cpp[concrt-dataflow-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_3.cpp)]

   `countdown_event` Sınıfı bu konunun ilerleyen bölümlerinde gösterilmektedir.

1. İleti veri akışı ağdaki katılacak olan bir arabellek nesneleri oluşturun.

[!code-cpp[concrt-dataflow-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_4.cpp)]

1. Bir ağ oluşturmak için mesaj arabellekleri bağlanın.

[!code-cpp[concrt-dataflow-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_5.cpp)]

1. Bekle `event` ve `countdown event` nesneleri ayarlanmalıdır. Bu olaylar Aracısı sentinel değeri aldığını ve tüm işlemlerini tamamladıktan sinyal.

[!code-cpp[concrt-dataflow-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_6.cpp)]

Eksiksiz bir veri akışı ağı için aşağıdaki diyagramda gösterilmiştir `dataflow_agent` sınıfı:

![Veri akışı ağ](../../parallel/concrt/media/concrt_dataflow.png "veri akışı ağ")

Aşağıdaki tabloda, ağ üyelerini açıklar.

|Üye|Açıklama|
|------------|-----------------|
|`increment_active`|A [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) nesnesini active olay sayacını artırır ve ağın geri kalanı için giriş değeri geçirir.|
|`negatives`, `positives`|[CONCURRENCY::call](../../parallel/concrt/reference/call-class.md) etkin olay sayaç numaraları ve azaltır sayısı artan nesneleri. Her nesne bir filtre negatif sayılar ya da pozitif sayıları kabul etmek için kullanın.|
|`sentinel`|A [concurrency::call](../../parallel/concrt/reference/call-class.md) sentinel değeri sıfır azaltır ve yalnızca bir etkin olay sayacı kabul eden bir nesne.|
|`connector`|A [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) kaynak ileti arabelleği iç ağa bağlanan bir nesne.|

Çünkü `run` yöntemi, ayrı bir iş parçacığında çağrıldığında, tam olarak bir ağa bağlı önce diğer iş parçacıklarını ağa iletileri gönderebilir. `_source` Veri üyesi olan bir `unbounded_buffer` aracıya bir uygulamadan gönderilen tüm giriş arabelleği nesne. Ağ giriş tüm iletileri işlediğinden, aracı öncelikle iç ağ düğümlerine bağlantılar ve daha sonra bu ağ başlangıcını bağlar emin olmak için `connector`, `_source` veri üyesi. Bu, ağ biçimlendirilmiş olarak'ın iletileri işlenmez garanti eder.

Bu örnekte ağ veri akışı üzerinde olduğundan, yerine denetim akışı üzerinde ağ aracıya her giriş değeri işlem sona erdi ve sentinel düğümün değerini aldığını iletişim kurması gerekir. Bu örnekte bir `countdown_event` tüm giriş değerlerini işlendikten sinyal nesnesine ve [concurrency::event](../../parallel/concrt/reference/event-class.md) sentinel düğümün değerini aldığını gösteren nesne. `countdown_event` Sınıfını kullanan bir `event` sayaç değeri sıfır ulaştığında göstermek için nesne. BT'nin bir değer alır. her zaman veri akışı ağ Başkanı sayaç artırılır. Terminal her düğüm ağ azaltır, giriş değeri işledikten sonra sayacı. Aracı veri akışı ağ forms sonra ayarlanacak sentinel düğümünü bekler `event` nesne ve `countdown_event` kendi sayaç sıfır ulaştı göstermek için nesne.

Aşağıdaki örnekte gösterildiği `control_flow_agent`, `dataflow_agent`, ve `countdown_event` sınıfları. `wmain` İşlevi oluşturur bir `control_flow_agent` ve `dataflow_agent` nesne ve kullandığı `send_values` aracıları için rastgele değerler bir dizi göndermek için işlevi.

[!code-cpp[concrt-dataflow-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_7.cpp)]

Bu örnek, örnek aşağıdaki çıktıyı üretir:

```Output
Control-flow agent:
There are 500523 negative numbers.
There are 499477 positive numbers.
Dataflow agent:
There are 500523 negative numbers.
There are 499477 positive numbers.
```

### <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `dataflow-agent.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc veri akışı-agent.cpp**

[[Üst](#top)]

##  <a name="logging"></a> İleti günlüğü Aracısı oluşturma

Aşağıdaki örnekte gösterildiği `log_agent` benzer sınıfı `dataflow_agent` sınıfı. `log_agent` Sınıfı zaman uyumsuz günlük kaydı aracıyı, bir dosyaya ve konsola yazar iletileri günlüğe uygular. `log_agent` Sınıfı olarak bilgilendirme iletileri, uyarı veya hata kategorilere ayırmak bir uygulama sağlar. Ayrıca, her günlük kategorisi bir dosya, konsolu veya her ikisi de yazılmış belirtmek bir uygulama sağlar. Bu örnekte, tüm günlük iletileri bir dosyaya ve yalnızca hata iletileri konsola yazar.

[!code-cpp[concrt-log-filter#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_8.cpp)]

Bu örnek aşağıdaki çıktıyı konsola yazar.

```Output
error: This is a sample error message.
```

Bu örnek ayrıca şu metni içeren log.txt dosyası üretir.

```Output
info: ===Logging started.===
warning: This is a sample warning message.
error: This is a sample error message.
info: ===Logging finished.===
```

### <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `log-filter.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe /EHsc log-filter.cpp**

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

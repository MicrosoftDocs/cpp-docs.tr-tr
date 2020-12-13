---
description: 'Daha fazla bilgi edinin: Izlenecek yol: veri akışı Aracısı oluşturma'
title: 'İzlenecek Yol: Veri Akışı Aracısı Oluşturma'
ms.date: 04/25/2019
helpviewer_keywords:
- creating dataflow agents [Concurrency Runtime]
- dataflow agents, creating [Concurrency Runtime]
ms.assetid: 9db5ce3f-c51b-4de1-b79b-9ac2a0cbd130
ms.openlocfilehash: 2f7f2435d5a4ede1dd48a4dee672ed7affbdfd9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163866"
---
# <a name="walkthrough-creating-a-dataflow-agent"></a>İzlenecek Yol: Veri Akışı Aracısı Oluşturma

Bu belge, denetim akışı yerine veri akışını temel alan aracı tabanlı uygulamalar oluşturmayı gösterir.

*Denetim akışı* , bir programdaki işlemlerin yürütme sırasını ifade eder. Denetim akışı koşullu deyimler, döngüler vb. gibi denetim yapıları kullanılarak düzenlenebilir. Alternatif olarak, veri *akışı* yalnızca gerekli tüm veriler kullanılabilir olduğunda hesaplamaların yapıldığı bir programlama modeli anlamına gelir. Veri akışı programlama modeli, bir programın bağımsız bileşenlerinin ileti göndererek birbirleriyle iletişim kurduğu ileti geçirme kavramı ile ilgilidir.

Zaman uyumsuz aracılar hem denetim akışı hem de veri akışı programlama modellerini destekler. Denetim akışı modeli birçok durumda uygun olsa da, veri akışı modeli, örneğin, bir aracı verileri aldığında ve bu verilerin yükünü temel alan bir eylem gerçekleştirdiğinde, diğerleri için uygun olur.

## <a name="prerequisites"></a>Önkoşullar

Bu yönergeyi başlamadan önce aşağıdaki belgeleri okuyun:

- [Zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)

- [Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [Nasıl yapılır: Ileti bloğu filtresini kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)

## <a name="sections"></a><a name="top"></a> Başlıklı

Bu izlenecek yol aşağıdaki bölümleri içerir:

- [Temel bir Control-Flow Aracısı oluşturma](#control-flow)

- [Temel veri akışı Aracısı oluşturma](#dataflow)

- [Message-Logging Aracısı oluşturma](#logging)

## <a name="creating-a-basic-control-flow-agent"></a><a name="control-flow"></a> Temel bir Control-Flow Aracısı oluşturma

Sınıfını tanımlayan aşağıdaki örneği göz önünde bulundurun `control_flow_agent` . `control_flow_agent`Sınıfı üç ileti arabelleği üzerinde davranır: bir giriş arabelleği ve iki çıkış arabelleği. `run`Yöntemi bir döngüdeki kaynak ileti arabelleğinden okur ve program yürütme akışını yönlendirmek için bir koşullu ifade kullanır. Aracı sıfır olmayan, negatif değerler için bir sayacı artırır ve sıfır olmayan pozitif değerler için başka bir sayacı artırır. Aracı, Sentinel değerini sıfır aldıktan sonra, sayaçların değerlerini çıkış iletisi arabelleklerine gönderir. `negatives`Ve `positives` yöntemleri, uygulamanın, aracıdan gelen negatif ve pozitif değerlerin sayısını okumasına olanak tanır.

[!code-cpp[concrt-dataflow-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_1.cpp)]

Bu örnek, bir aracıdaki denetim akışının temel kullanımını sağlar, ancak denetim akışı tabanlı programlamanın seri yapısını gösterir. Giriş iletisi arabelleğinde birden çok ileti bulunabilir olmasına rağmen her ileti sırayla işlenmelidir. Veri akışı modeli, her iki koşullu deyimin dalını aynı anda değerlendirmeye olanak sağlar. Veri akışı modeli Ayrıca, kullanılabilir hale geldiğinde veriler üzerinde işlem gören daha karmaşık mesajlaşma ağları oluşturmanıza da olanak sağlar.

[[Üst](#top)]

## <a name="creating-a-basic-dataflow-agent"></a><a name="dataflow"></a> Temel veri akışı Aracısı oluşturma

Bu bölümde, `control_flow_agent` sınıfının aynı görevi gerçekleştirmek için veri akışı modelini kullanmak üzere nasıl dönüştürüleceği gösterilmektedir.

Veri akışı Aracısı, her biri belirli bir amaca hizmet eden bir ileti arabellekleri ağı oluşturarak çalışır. Belirli ileti blokları yük temelinde bir iletiyi kabul etmek veya reddetmek için bir filtre işlevi kullanır. Filtre işlevi bir ileti bloğunun yalnızca belirli değerleri almasını sağlar.

#### <a name="to-convert-the-control-flow-agent-to-a-dataflow-agent"></a>Denetim akışı aracısını bir veri akışı aracısına dönüştürmek için

1. `control_flow_agent`Sınıfın gövdesini başka bir sınıfa (örneğin,) kopyalayın `dataflow_agent` . Alternatif olarak, sınıfını yeniden adlandırabilirsiniz `control_flow_agent` .

1. Yönteminden çağıran döngünün gövdesini kaldırın `receive` `run` .

[!code-cpp[concrt-dataflow-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_2.cpp)]

1. `run`Yönteminde, değişkenlerin başlatılmasından sonra `negative_count` `positive_count` , `countdown_event` etkin işlemlerin sayısını izleyen bir nesne ekleyin.

[!code-cpp[concrt-dataflow-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_3.cpp)]

   `countdown_event`Sınıfı bu konunun ilerleyen kısımlarında gösterilmektedir.

1. Veri akışı ağına katılacak ileti arabelleği nesneleri oluşturun.

[!code-cpp[concrt-dataflow-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_4.cpp)]

1. Ağ oluşturmak için ileti arabelleklerini bağlayın.

[!code-cpp[concrt-dataflow-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_5.cpp)]

1. `event`Ve `countdown event` nesnelerinin ayarlanması için bekleyin. Bu olaylar, aracının Sentinel değerini aldığını ve tüm işlemlerin tamamlandığını işaret etti.

[!code-cpp[concrt-dataflow-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_6.cpp)]

Aşağıdaki diyagramda, sınıfının tüm veri akışı ağı gösterilmektedir `dataflow_agent` :

![Veri akışı ağı](../../parallel/concrt/media/concrt_dataflow.png "Veri akışı ağı")

Aşağıdaki tablo, ağın üyelerini açıklar.

|Üye|Açıklama|
|------------|-----------------|
|`increment_active`|Etkin olay sayacını artıran ve giriş değerini ağın geri kalanına ileten bir [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) nesnesi.|
|`negatives`, `positives`|[concurrency::](../../parallel/concrt/reference/call-class.md) sayı sayısını artıran ve etkin olay sayacını azaltır nesneleri çağırın. Nesnelerin her biri negatif sayıları veya pozitif sayıları kabul etmek için bir filtre kullanır.|
|`sentinel`|Bir [concurrency:: Call](../../parallel/concrt/reference/call-class.md) nesnesi yalnızca sıfır Sentinel değerini kabul eder ve etkin olay sayacını azaltır.|
|`connector`|Kaynak ileti arabelleğini iç ağa bağlayan bir [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) nesnesi.|

`run`Yöntemi ayrı bir iş parçacığında çağrıldığı için, diğer iş parçacıkları ağ tam olarak bağlanmadan önce ağa ileti gönderebilir. `_source`Veri üyesi, `unbounded_buffer` uygulamadan aracıya gönderilen tüm girişleri arabelleğe alan bir nesnedir. Ağın tüm giriş iletilerini işlediğinden emin olmak için, aracı ilk olarak ağın iç düğümlerini bağlar ve bu ağın başlangıcını `connector` `_source` veri üyesine bağlar. Bu, ağın oluşturulduğu sürece iletilerin işlenmesini güvence altına alır.

Bu örnekteki ağ denetim akışı yerine veri akışını temel aldığından, ağ, her giriş değerini işlemeyi tamamladığında ve Sentinel düğümünün değerini aldığından, aracıya iletişim kurmalıdır. Bu örnek `countdown_event` , Sentinel düğümünün değerini aldığını göstermek için tüm giriş değerlerinin işlenmiş olduğunu ve bir [eşzamanlılık:: Event](../../parallel/concrt/reference/event-class.md) nesnesini işaret etmek için bir nesnesi kullanır. `countdown_event`Sınıfı, `event` bir sayaç değeri sıfıra ulaştığında sinyal almak için bir nesne kullanır. Veri akışı ağının kafa değeri her seferinde bir değer aldığında sayacı artırır. Ağın her bir Terminal düğümü, giriş değerini tamamladıktan sonra sayacı azaltır. Aracı veri akışı ağını ayarladıktan sonra, Sentinel düğümünün `event` nesnesini ayarlaması ve `countdown_event` nesnesi için sayacın sıfıra ulaşmış olduğunu işaret etmek için bekler.

Aşağıdaki örnek `control_flow_agent` , `dataflow_agent` ve `countdown_event` sınıflarını gösterir. `wmain`İşlevi bir `control_flow_agent` ve `dataflow_agent` nesnesi oluşturur ve `send_values` aracılara rastgele değerler serisi göndermek için işlevini kullanır.

[!code-cpp[concrt-dataflow-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_7.cpp)]

Bu örnek aşağıdaki örnek çıktıyı üretir:

```Output
Control-flow agent:
There are 500523 negative numbers.
There are 499477 positive numbers.
Dataflow agent:
There are 500523 negative numbers.
There are 499477 positive numbers.
```

### <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `dataflow-agent.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/EHsc dataflow-Agent. cpp**

[[Üst](#top)]

## <a name="creating-a-message-logging-agent"></a><a name="logging"></a> Message-Logging Aracısı oluşturma

Aşağıdaki örnek, sınıfına `log_agent` benzeyen sınıfını gösterir `dataflow_agent` . `log_agent`Sınıfı, günlük iletilerini bir dosyaya ve konsoluna yazan bir zaman uyumsuz günlüğe kaydetme Aracısı uygular. `log_agent`Sınıfı, uygulamanın iletileri bilgilendirme, uyarı veya hata olarak sınıflandırmalarını sağlar. Ayrıca, uygulamanın her bir günlük kategorisinin bir dosyaya, konsola veya her ikisine de yazılıp yazılmadığını belirtmesini sağlar. Bu örnek, tüm günlük iletilerini bir dosyaya ve yalnızca konsola yönelik hata iletilerini yazar.

[!code-cpp[concrt-log-filter#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_8.cpp)]

Bu örnek konsola aşağıdaki çıktıyı yazar.

```Output
error: This is a sample error message.
```

Bu örnek, aşağıdaki metni içeren log.txt dosyasını da üretir.

```Output
info: ===Logging started.===
warning: This is a sample warning message.
error: This is a sample error message.
info: ===Logging finished.===
```

### <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `log-filter.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/EHsc log-Filter. cpp**

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı Izlenecek yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

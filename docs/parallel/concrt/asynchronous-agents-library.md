---
title: Zaman Uyumsuz Aracılar Kitaplığı
ms.date: 11/19/2018
helpviewer_keywords:
- Agents Library
- Asynchronous Agents Library
ms.assetid: d2a72a31-8ba6-4220-ad7a-e403a6acaa42
ms.openlocfilehash: 8b4e8e6489e98aadb6ea41d32d5a9ba14efe2668
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175866"
---
# <a name="asynchronous-agents-library"></a>Zaman Uyumsuz Aracılar Kitaplığı

Zaman uyumsuz aracılar kitaplığı (veya yalnızca *Aracılar Kitaplığı*) eşzamanlılık kullanan uygulama geliştirme'ların sağlamlığını artırmak olanak sağlayan bir programlama modeli sağlar. Agents kitaplığı, bir aktör tabanlı programlama modeli ve işlem içi ileti geçirme için parçalı veri akışı ve ardışık düzen oluşturma görevleri yükseltir bir C++ Şablon Kitaplığı ' dir. Agents kitaplığı, zamanlama ve kaynak yönetimi bileşenlerine eşzamanlılık çalışma zamanı oluşturur.

## <a name="programming-model"></a>Programlama Modeli

Agents kitaplığı, denetim akışı yerine veri akışı temel alan bir zaman uyumsuz iletişim modeli aracılığıyla yalıtılmış bileşenleri bağlanmanıza izin vererek paylaşılan durum alternatifleri sağlar. *Veri akışı* başvuran bir programlama için kullanılabilir; burada hesaplamalar yapılan tüm verileri gerektiğinde modeli *denetim akışı* hesaplamalar önceden belirlenmiş bir sırada yapılan burada bir programlama modelini ifade eder.

Veri akışı programlama modelini kavramıyla ilişkilidir *ileti geçirme*, bir program bağımsız bileşenlerinin birbirleriyle iletiler göndererek iletişim kurduğu.

Agents kitaplığı, üç bileşenden oluşur: *zaman uyumsuz aracılar*, *zaman uyumsuz ileti blokları*, ve *ileti geçirme işlevleri*. Aracıların durumunu korumak ve birbirleriyle ve dış bileşenler ile iletişim kurmak için ileti blokları ve ileti geçirme işlevleri kullanın. İleti geçirme işlevleri dış bileşenler gelen ve giden iletiler gönderip almak üzere aracı etkinleştiren. Zaman uyumsuz ileti blokları ileti tutun ve eşitlenmiş bir şekilde iletişim kurmak üzere aracı etkinleştiren.

Aşağıdaki çizimde, ileti blokları kullanın ve iletişim kurmak için ileti geçirme işlevleri nasıl iki aracı gösterir. Bu çizimde, `agent1` bir ileti gönderir `agent2` kullanarak [concurrency::send](reference/concurrency-namespace-functions.md#send) işlevi ve bir [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) nesne. `agent2` kullanan [concurrency::receive](reference/concurrency-namespace-functions.md#receive) ileti okumak için işlev. `agent2` ileti göndermek için aynı yöntemi kullanan `agent1`. Kesik çizgili oklar aracılar arasındaki veri akışını temsil eder. Düz bir ok, yazma veya okuma ileti blokları aracıları bağlanın.

![Agents kitaplığı bileşenlerinin](../../parallel/concrt/media/agent_librarycomp.png "bileşenlerini Aracılar Kitaplığı")

Bu çizim uygulayan bir kod örneği, bu konunun ilerleyen bölümlerinde gösterilmektedir.

Aracı programlama modeli, diğer eşzamanlılık ve eşitleme mekanizmaları için örneğin olaylar üzerinde çeşitli avantajları vardır. İleti geçirme nesneler arasında durum değişikliklerini iletmek için kullanarak tarafından paylaşılan kaynaklara erişimi ayırmak ve böylece ölçeklenebilirliği geliştirmek, avantajlarından biri. İleti geçirme için yerine bir dış eşitleme nesneye tümleştirilerek veri eşitlemeyi bölümlere avantajlıdır. Bu bileşenler arasındaki veri aktarımını kolaylaştırır ve uygulamalarınızda programlama hatalarını ortadan kaldırabilirsiniz.

## <a name="when-to-use-the-agents-library"></a>Aracılar Kitaplığı Kullanılacağı Zaman

Agents kitaplığı, birbirleriyle zaman uyumsuz olarak iletişim kurması gereken birden çok işlem olduğunda kullanın. İleti blokları ve ileti geçirme işlevleri kilitler gibi eşitleme mekanizmaları gerek kalmadan paralel uygulamaları yazmanıza olanak sağlar. Uygulama mantığına odaklanabilir olanak sağlar.

Aracı programlama modeli oluşturmak için genellikle kullanılan *veri komut zincirlerini* veya *ağları*. Veri işlem hattı, her biri, daha büyük bir hedefe katkıda bulunan belirli bir görevi gerçekleştiren bir dizi Bileşenler ' dir. Başka bir bileşenden bir ileti aldığında, her bir veri akışı işlem hattı bileşeni çalışma gerçekleştirir. Bu iş sonucu ardışık düzen veya ağda içindeki diğer bileşenlere geçirilir. Bileşenleri daha fazla ayrıntılı eşzamanlılık işlevsellik diğer kitaplıklarından örneğin kullanabilirsiniz, [paralel desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bu konuda daha önce gösterilen resimde uygular.

[!code-cpp[concrt-basic-agents#1](../../parallel/concrt/codesnippet/cpp/asynchronous-agents-library_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
agent1: sending request...
agent2: received 'request'.
agent2: sending response...
agent1: received '42'.
```

Aşağıdaki konularda, bu örnekte kullanılan işlevler açıklanmaktadır.

## <a name="related-topics"></a>İlgili Konular

[Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)<br/>
Daha büyük bilgi işlem görevlerini çözümünde zaman uyumsuz aracılar rolünü açıklar.

[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
Aracılar Kitaplığı tarafından sağlanan çeşitli ileti blok türleri açıklanmaktadır.

[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
Aracılar Kitaplığı tarafından sağlanan çeşitli ileti geçirme yordamları açıklar.

[Nasıl yapılır: Çeşitli Üretici-Tüketici Desenlerini Uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)<br/>
Üretici-tüketici düzeni uygulamanıza açıklar.

[Nasıl yapılır: call ve transformer Sınıflarına İş İşlevleri Sağlama](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)<br/>
İş işlevleri sağlama için çeşitli yollar gösterir [concurrency::call](../../parallel/concrt/reference/call-class.md) ve [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) sınıfları.

[Nasıl yapılır: Veri İşlem Hattında transformer Kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br/>
Nasıl kullanılacağını gösterir [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) veri ardışık düzeninde sınıfı.

[Nasıl yapılır: Tamamlanan Görevler Arasında Seçim Yapma](../../parallel/concrt/how-to-select-among-completed-tasks.md)<br/>
Nasıl kullanılacağını gösterir [concurrency::choice](../../parallel/concrt/reference/choice-class.md) ve [concurrency::join](../../parallel/concrt/reference/join-class.md) sınıflar arama algoritması tamamlamak için ilk görevi seçin.

[Nasıl yapılır: Düzenli Aralıkla İleti Gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)<br/>
Nasıl kullanılacağını gösterir [concurrency::timer](../../parallel/concrt/reference/timer-class.md) düzenli aralıkla ileti göndermek için sınıf.

[Nasıl yapılır: İleti Bloğu Filtresini Kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)<br/>
Kabul etme veya reddetme iletileri için bir zaman uyumsuz ileti bloğu etkinleştirmek için bir filtre nasıl yapılacağı açıklanır.

[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
Paralel algoritmalar gibi çeşitli paralel desenler uygulamalarınızda kullanmayı açıklar.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)<br/>
Eşzamanlılık paralel programlama basitleştirir ve ilgili konulara bağlantılar içeren çalışma zamanı, açıklar.


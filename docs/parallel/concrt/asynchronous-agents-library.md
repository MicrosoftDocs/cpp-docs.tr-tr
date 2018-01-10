---
title: "Zaman uyumsuz aracılar kitaplığı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Agents Library
- Asynchronous Agents Library
ms.assetid: d2a72a31-8ba6-4220-ad7a-e403a6acaa42
caps.latest.revision: "33"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: be12f47a6fb33350137a8f9b1c78ff75519c8af7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="asynchronous-agents-library"></a>Zaman Uyumsuz Aracılar Kitaplığı
Zaman uyumsuz aracılar kitaplığı (veya yalnızca *Aracılar Kitaplığı*) eşzamanlılık etkin uygulama geliştirme'ların sağlamlığını artırmak olanak sağlayan bir programlama modelidir. Aktör tabanlı programlama modeli ve görevleri ardışık düzen ve parçalı veri akışı için geçirme işlemi iletisi yükseltir C++ Şablon kitaplığı aracıları kitaplığıdır. Aracılar Kitaplığı zamanlama ve kaynak yönetimi bileşenlerine eşzamanlılık çalışma zamanı oluşturur.  
  
## <a name="programming-model"></a>Programlama Modeli  
 Aracılar Kitaplığı veri akışı denetim akışı yerine dayalı bir zaman uyumsuz iletişim modeli aracılığıyla yalıtılmış bileşenleri bağlanmanıza izin vererek paylaşılan durum alternatifleri sağlar. *Veri akışı* başvuran bir programlama modeli burada hesaplamalar yapılan tüm veri gerektiğinde kullanılabilir; *kontrol akışı* hesaplamalar önceden belirlenmiş bir sırayla yapılan burada bir programlama modeli başvuruyor.  
  
 Veri akışı programlama modeli kavramı, ilgili *ileti geçirme*, bağımsız bir program bileşenlerinin başka bir işlemle iletileri göndererek iletişim kurduğu.  
  
 Aracılar Kitaplığı üç bileşenlerden oluşur: *zaman uyumsuz aracılar*, *zaman uyumsuz ileti blokları*, ve *ileti geçirme işlevleri*. Aracıları durumunu korumak ve birbiriyle ve dış bileşenler ile iletişim kurmak için ileti blokları ve ileti geçirme işlevleri kullanın. İleti geçirme işlevleri ve dış bileşenlere gelen ileti gönderme ve alma için aracıları etkinleştirin. Zaman uyumsuz ileti blokları iletileri tutun ve eşitlenmiş bir şekilde iletişim kurmak aracıları etkinleştirin.  
  
 Aşağıdaki çizimde, kullanım ileti blokları ve iletişim kurmak için ileti geçirme işlevleri nasıl iki aracı gösterir. Bu çizimde, `agent1` bir ileti gönderir `agent2` kullanarak [concurrency::send](reference/concurrency-namespace-functions.md#send) işlevi ve [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) nesnesi. `agent2`kullanan [concurrency::receive](reference/concurrency-namespace-functions.md#receive) ileti okumak için işlev. `agent2`bir ileti göndermek için aynı yöntemi kullanan `agent1`. Kesikli oklar aracılar arasındaki veri akışını temsil eder. Düz oklar, yazma veya okuma ileti blokları aracıları bağlayın.  
  
 ![Aracılar Kitaplığı bileşenlerinin](../../parallel/concrt/media/agent_librarycomp.png "agent_librarycomp")  
  
 Bu çizim uygulayan bir kod örneği, bu konunun devamında gösterilir.  
  
 Aracı programlama modeli diğer eşzamanlılık ve eşitleme mekanizmaları, örneğin, olaylar üzerinde çeşitli avantajları vardır. İleti geçirme nesneler arasındaki durum değişikliklerini iletmek için kullanarak tarafından paylaşılan kaynaklara erişimi ayırmak ve böylece ölçeklenebilirliğini geliştirmek, avantajlarından biri. İleti geçirme için dış eşitleme nesneye bağlamadan yerine veri eşitlemeye bağlar avantajlıdır. Bu bileşenler arasındaki veri aktarımını basitleştirir ve uygulamalarınızda programlama hataları ortadan kaldırabilirsiniz.  
  
## <a name="when-to-use-the-agents-library"></a>Aracılar Kitaplığı Kullanılacağı Zaman  
 Zaman uyumsuz olarak birbirleriyle gerekir birden çok operations varsa aracılar kitaplığı kullanın. İleti blokları ve ileti geçirme işlevleri eşitleme mekanizmaları kilitleri gibi gerek kalmadan paralel uygulamalar yazmanıza olanak tanır. Bu uygulama mantığına odaklanmanıza olanak sağlar.  
  
 Aracı programlama modeli genellikle oluşturmak için kullanılan *veri ardışık* veya *ağlar*. Veri ardışık her biri daha büyük bir hedefe katkıda bulunan belirli bir görevi gerçekleştiren bir bileşenleri dizisidir. Başka bir bileşenden bir ileti aldığında, her bileşen veri akışı ardışık düzeninde çalışma gerçekleştirir. Bu iş sonucunu ardışık düzen veya ağ içindeki diğer bileşenlere geçirilir. Bileşenleri daha fazla hassas eşzamanlılık işlevsellik diğer kitaplıklarından örneğin kullanabilirsiniz, [paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu konunun önceki bölümlerinde gösterilen çizim uygular.  
  
 [!code-cpp[concrt-basic-agents#1](../../parallel/concrt/codesnippet/cpp/asynchronous-agents-library_1.cpp)]  
  
 Bu örnek şu çıkışı üretir:  
  
```Output  
agent1: sending request...  
agent2: received 'request'.  
agent2: sending response...  
agent1: received '42'.  
```  
  
 Aşağıdaki konularda bu örnekte kullanılan işlevler açıklanmaktadır.  
  
## <a name="related-topics"></a>İlgili Konular  
 [Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)  
 Daha büyük hesaplama görevleri çözümünde zaman uyumsuz aracılar rolü açıklanmaktadır.  
  
 [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)  
 Aracılar Kitaplığı tarafından sağlanan çeşitli ileti bloğu türleri açıklanmaktadır.  
  
 [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)  
 Aracılar Kitaplığı tarafından sağlanan çeşitli ileti geçirme yordamları açıklar.  
  
 [Nasıl yapılır: Çeşitli Üretici-Tüketici Desenlerini Uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)  
 Uygulamanızda üretici-tüketici düzeni uygulama açıklar.  
  
 [Nasıl yapılır: call ve transformer Sınıflarına İş İşlevleri Sağlama](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)  
 İş işlevleri sağlamak için çeşitli yollar gösterilmektedir [concurrency::call](../../parallel/concrt/reference/call-class.md) ve [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) sınıfları.  
  
 [Nasıl yapılır: Veri İşlem Hattında transformer Kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)  
 Nasıl kullanılacağını gösterir [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) veri ardışık düzeninde sınıfı.  
  
 [Nasıl yapılır: Tamamlanan Görevler Arasında Seçim Yapma](../../parallel/concrt/how-to-select-among-completed-tasks.md)  
 Nasıl kullanılacağını gösterir [concurrency::choice](../../parallel/concrt/reference/choice-class.md) ve [concurrency::join](../../parallel/concrt/reference/join-class.md) sınıfları arama algoritması tamamlamak için ilk görevi seçin.  
  
 [Nasıl yapılır: Düzenli Aralıkla İleti Gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)  
 Nasıl kullanılacağını gösterir [concurrency::timer](../../parallel/concrt/reference/timer-class.md) düzenli aralıklarla ileti göndermek için sınıf.  
  
 [Nasıl yapılır: İleti Bloğu Filtresini Kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
 Bir filtre kabul edin veya iletileri reddetmek için bir zaman uyumsuz ileti bloğu etkinleştirmek için nasıl kullanılacağını gösterir.  
  
 [Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)  
 Paralel algoritmalar gibi çeşitli paralel desen uygulamalarınızda kullanmayı açıklar.  
  
 [Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)  
 Paralel Programlama basitleştiren ve ilgili konulara bağlantılar içerir eşzamanlılık çalışma, açıklar.


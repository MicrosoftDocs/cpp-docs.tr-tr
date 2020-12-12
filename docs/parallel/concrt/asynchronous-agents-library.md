---
description: 'Daha fazla bilgi edinin: zaman uyumsuz aracılar Kitaplığı'
title: Zaman Uyumsuz Aracılar Kitaplığı
ms.date: 11/19/2018
helpviewer_keywords:
- Agents Library
- Asynchronous Agents Library
ms.assetid: d2a72a31-8ba6-4220-ad7a-e403a6acaa42
ms.openlocfilehash: 5d56bd84078d4c1a89fc489fba37edeb03b3739f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338299"
---
# <a name="asynchronous-agents-library"></a>Zaman Uyumsuz Aracılar Kitaplığı

Zaman uyumsuz aracılar Kitaplığı (veya yalnızca *aracılar Kitaplığı*) eşzamanlılık özellikli uygulama geliştirmenin sağlamlığını artırmanıza imkan tanıyan bir programlama modeli sağlar. Aracılar Kitaplığı, aktör temelli bir programlama modelini ve işlem içi iletileri, kaba veri akışı ve ardışık düzen oluşturma görevleri için geçen bir C++ şablon kitaplığıdır. Aracılar Kitaplığı, Eşzamanlılık Çalışma Zamanı zamanlama ve kaynak yönetimi bileşenleri üzerinde oluşturulur.

## <a name="programming-model"></a>Programlama Modeli

Aracılar Kitaplığı, yalıtılmış bileşenleri denetim akışı yerine veri akışına dayalı bir zaman uyumsuz iletişim modeli aracılığıyla bağlamanıza izin vererek paylaşılan duruma yönelik alternatifler sağlar. Veri *akışı* , gerekli tüm veriler kullanılabilir olduğunda hesaplamaların yapıldığı bir programlama modelini ifade eder; *Denetim akışı* , hesaplamaların önceden belirlenmiş bir sırada yapıldığı bir programlama modelini ifade eder.

Veri akışı programlama modeli, *ileti geçirme* kavramı ile ilgilidir. Bu, bir programın bağımsız bileşenlerinin iletiler göndererek birbirleriyle iletişim kuracağı kavramdır.

Aracılar Kitaplığı üç bileşenden oluşur: *zaman uyumsuz aracılar*, *zaman uyumsuz ileti blokları* ve *ileti geçirme işlevleri*. Aracılar durumu korur ve ileti blokları ile ileti geçirme işlevlerini kullanarak birbirleriyle ve harici bileşenlerle iletişim kurar. İleti geçirme işlevleri, aracıların dış bileşenlere gelen ve olmayan iletileri göndermesini ve almasını sağlar. Zaman uyumsuz ileti blokları iletileri tutar ve aracıları eşitlenmiş bir şekilde iletişim kuracak şekilde etkinleştirir.

Aşağıdaki çizimde, iki aracısının ileti bloklarını ve iletişim kurmak için ileti geçirme işlevlerini nasıl kullandığını gösterilmektedir. Bu çizimde `agent1` `agent2` [eşzamanlılık:: Send](reference/concurrency-namespace-functions.md#send) işlevini ve bir [eşzamanlılık:: unbounded_buffer](reference/unbounded-buffer-class.md) nesnesini kullanarak öğesine bir ileti gönderir. `agent2` iletiyi okumak için [concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) işlevini kullanır. `agent2` , ' a ileti göndermek için aynı yöntemi kullanır `agent1` . Kesik ok, aracılar arasındaki veri akışını temsil eder. Düz oklar, aracıları yazdıkları veya okudukları ileti bloklarına bağlayın.

![Aracılar kitaplığının bileşenleri](../../parallel/concrt/media/agent_librarycomp.png "Aracılar kitaplığının bileşenleri")

Bu çizimi uygulayan bir kod örneği, bu konunun ilerleyen kısımlarında gösterilmektedir.

Aracı programlama modelinin diğer eşzamanlılık ve eşitleme mekanizmalarına (örneğin, olaylar) göre çeşitli avantajları vardır. Bir avantajı, nesneler arasında durum değişikliklerini iletmek için ileti geçirme kullanarak, paylaşılan kaynaklara erişimi yalıtabilir ve böylece ölçeklenebilirliği geliştirebilirsiniz. İleti geçirme avantajı, bir dış eşitleme nesnesine bağlamak yerine verileri eşitlemeye bağladır. Bu, bileşenler arasında veri aktarımını basitleştirir ve uygulamalarınızda programlama hatalarını ortadan kaldırabilir.

## <a name="when-to-use-the-agents-library"></a>Aracılar Kitaplığı Kullanılacağı Zaman

Başka bir zaman uyumsuz ile iletişim kurması gereken birden çok işlem varsa aracılar kitaplığını kullanın. İleti blokları ve ileti geçirme işlevleri, kilitler gibi eşitleme mekanizmalarına gerek kalmadan paralel uygulamalar yazmanızı sağlar. Bu, uygulama mantığına odaklanmanızı sağlar.

Aracı programlama modeli, genellikle *veri işlem hatları* veya *ağları* oluşturmak için kullanılır. Veri işlem hattı, her biri daha büyük bir hedefe katkıda bulunan belirli bir görevi gerçekleştiren bir dizi bileşendir. Bir veri akışı ardışık düzeninde bulunan her bileşen, başka bir bileşenden bir ileti aldığında iş gerçekleştirir. Bu çalışmanın sonucu, işlem hattının veya ağdaki diğer bileşenlere geçirilir. Bileşenler, diğer kitaplıklardan daha ayrıntılı eşzamanlılık işlevlerini (örneğin, [paralel Desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)kullanabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bu konunun önceki kısımlarında gösterilen çizimi uygular.

[!code-cpp[concrt-basic-agents#1](../../parallel/concrt/codesnippet/cpp/asynchronous-agents-library_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
agent1: sending request...
agent2: received 'request'.
agent2: sending response...
agent1: received '42'.
```

Aşağıdaki konularda, bu örnekte kullanılan işlevsellik açıklanır.

## <a name="related-topics"></a>İlgili Konular

[Zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)<br/>
Daha büyük bilgi işlem görevlerini çözmede zaman uyumsuz aracıların rolünü açıklar.

[Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
Aracılar Kitaplığı tarafından sunulan çeşitli ileti bloğu türlerini açıklar.

[İleti geçirme Işlevleri](../../parallel/concrt/message-passing-functions.md)<br/>
Aracılar Kitaplığı tarafından sunulan çeşitli ileti geçirme yordamlarını açıklar.

[Nasıl yapılır: çeşitli Producer-Consumer desenleri uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)<br/>
Uygulamanızdaki üretici tüketicisi deseninin nasıl uygulanacağını açıklar.

[Nasıl yapılır: çağrıya ve transformatör sınıflarına çalışma Işlevleri sağlama](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)<br/>
[Concurrency:: Call](../../parallel/concrt/reference/call-class.md) ve [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) sınıflarına çalışma işlevleri sağlamanın çeşitli yollarını gösterir.

[Nasıl yapılır: bir veri ardışık düzeninde transformatör kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br/>
Bir veri işlem hattında [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) sınıfının nasıl kullanılacağını gösterir.

[Nasıl yapılır: tamamlanan görevler arasında seçim yapma](../../parallel/concrt/how-to-select-among-completed-tasks.md)<br/>
Bir arama algoritmasını tamamlamaya yönelik ilk görevi seçmek için [concurrency:: Choice](../../parallel/concrt/reference/choice-class.md) ve [concurrency:: JOIN](../../parallel/concrt/reference/join-class.md) sınıflarının nasıl kullanılacağını gösterir.

[Nasıl yapılır: düzenli bir aralıkta Ileti gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)<br/>
Düzenli aralıklarla bir ileti göndermek için [concurrency:: Timer](../../parallel/concrt/reference/timer-class.md) sınıfının nasıl kullanılacağını gösterir.

[Nasıl yapılır: Ileti bloğu filtresini kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)<br/>
Zaman uyumsuz ileti bloğunun iletileri kabul etmesini veya reddetmesini sağlamak için bir filtrenin nasıl kullanılacağını gösterir.

[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
Uygulamalarınızda paralel algoritmalar gibi çeşitli paralel desenlerin nasıl kullanılacağını açıklar.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)<br/>
Paralel programlamayı kolaylaştıran ve ilgili konuların bağlantılarını içeren Eşzamanlılık Çalışma Zamanı açıklar.

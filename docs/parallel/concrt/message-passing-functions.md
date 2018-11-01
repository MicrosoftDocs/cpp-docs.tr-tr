---
title: İleti Geçirme İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
ms.openlocfilehash: e258a73723e78090f61230555748e109c28cf01c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476030"
---
# <a name="message-passing-functions"></a>İleti Geçirme İşlevleri

Zaman uyumsuz aracılar Kitaplığı bileşenleri arasında iletileri geçirmenize olanak tanıyan çeşitli işlevler sağlar.

Bu ileti geçirme işlevleri, çeşitli ileti bloğu türleri ile kullanılır. Eşzamanlılık Çalışma zamanı tarafından tanımlanan ileti bloğu türleri hakkında daha fazla bilgi için bkz. [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

##  <a name="top"></a> Bölümleri

Bu konuda, aşağıdaki ileti geçirme işlevleri açıklanmaktadır:

- [Gönder ve asend](#send)

- [Alma ve try_receive](#receive)

- [Örnekler](#examples)

##  <a name="send"></a> Gönder ve asend

[Concurrency::send](reference/concurrency-namespace-functions.md#send) işlevi bir ileti zaman uyumlu olarak belirtilen hedefe gönderir ve [concurrency::asend](reference/concurrency-namespace-functions.md#asend) işlevi bir ileti zaman uyumsuz olarak belirtilen hedefe gönderir. Hem `send` ve `asend` işlevleri, hedef, sonunda kabul edin veya iletiyi reddedebilir gösterir kadar bekleyin.

`send` İşlevi hedef kabul eder ya da döndürülmeden önce iletiyi reddettiğinde kadar bekler. `send` İşlevinin döndürdükleriyle **true** ileti teslim varsa ve **false** Aksi takdirde. Çünkü `send` işlev çalışır eş `send` işlevi hedef döndürülmeden önce ileti almak bekler.

Buna karşılık, `asend` işlevi kabul etmesini ya da döndürülmeden önce iletiyi reddedebilir hedefi için bekleyin değil. Bunun yerine, `asend` işlevinin döndürdükleriyle **true** hedef iletiyi kabul eder ve sonunda sürer. Aksi takdirde, `asend` döndürür **false** hedef iletiyi reddetti veya iletisi olup olmadığı hakkında karar Ertelenen belirtmek için.

[[Üst](#top)]

##  <a name="receive"></a> Alma ve try_receive

[Concurrency::receive](reference/concurrency-namespace-functions.md#receive) ve [concurrency::try_receive](reference/concurrency-namespace-functions.md#try_receive) işlevleri, belirli bir kaynaktan verileri okur. `receive` İşlevi için verileri kullanıma hazır olmasını bekler ancak `try_receive` işlevi hemen döndürür.

Kullanım `receive` çalışmaya devam etmek için veri sahip olmalıdır. Kullanım `try_receive` işlevinin geçerli bağlam engellemelisiniz değil ya da devam etmek için veri yok.

[[Üst](#top)]

##  <a name="examples"></a> Örnekleri

Kullanan örnekler `send` ve `asend`, ve `receive` işlevleri, aşağıdaki konulara bakın:

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [Nasıl yapılır: Çeşitli Üretici-Tüketici Desenlerini Uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)

- [Nasıl yapılır: call ve transformer Sınıflarına İş İşlevleri Sağlama](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)

- [Nasıl yapılır: Veri İşlem Hattında transformer Kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)

- [Nasıl yapılır: Tamamlanan Görevler Arasında Seçim Yapma](../../parallel/concrt/how-to-select-among-completed-tasks.md)

- [Nasıl yapılır: Düzenli Aralıkla İleti Gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)

- [Nasıl yapılır: İleti Bloğu Filtresini Kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca Bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[send işlevi](reference/concurrency-namespace-functions.md#send)<br/>
[asend işlevi](reference/concurrency-namespace-functions.md#asend)<br/>
[receive işlevi](reference/concurrency-namespace-functions.md#receive)<br/>
[try_receive işlevi](reference/concurrency-namespace-functions.md#try_receive)


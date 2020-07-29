---
title: İleti Geçirme İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
ms.openlocfilehash: 3709e7b5280b96b2b77ec850a06ed15d0e42a7e5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87194634"
---
# <a name="message-passing-functions"></a>İleti Geçirme İşlevleri

Zaman uyumsuz aracılar Kitaplığı, bileşenler arasında ileti iletmenizi sağlayan çeşitli işlevler sağlar.

Bu ileti geçirme işlevleri çeşitli ileti bloğu türleriyle kullanılır. Eşzamanlılık Çalışma Zamanı tarafından tanımlanan ileti bloğu türleri hakkında daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="sections"></a><a name="top"></a>Başlıklı

Bu konuda aşağıdaki ileti geçirme işlevleri açıklanmaktadır:

- [gönderme ve asend](#send)

- [alma ve try_receive](#receive)

- [Örnekler](#examples)

## <a name="send-and-asend"></a><a name="send"></a>gönderme ve asend

[Concurrency:: Send](reference/concurrency-namespace-functions.md#send) işlevi belirtilen hedefe zaman uyumlu bir ileti gönderir ve [concurrency:: asend](reference/concurrency-namespace-functions.md#asend) işlevi belirtilen hedefe zaman uyumsuz bir ileti gönderir. Hem `send` hem de `asend` işlevleri, hedefin iletiyi kabul edeceğini veya reddetmesi gerektiğini belirten bir süre kadar bekler.

`send`İşlev, döndürülünceye kadar iletiyi kabul edip reddetene kadar bekler. `send`İşlev **`true`** , ileti teslim edildiğinde ve **`false`** Aksi takdirde döndürür. `send`İşlev eşzamanlı olarak çalıştığından, işlev, `send` döndürülbaşlamadan önce hedefin iletiyi almasını bekler.

Buna karşılık, `asend` işlev, hedefin döndürülmeden önce iletiyi kabul etmesini veya reddetmesi için beklemez. Bunun yerine, `asend` işlev, **`true`** hedef iletiyi kabul ediyorsa ve sonunda zaman alıyorsa, döndürür. Aksi takdirde `asend` , **`false`** hedefin iletiyi reddettiğini veya iletiyi alıp almayacağı kararı ertelemesini belirten döndürür.

[[Üst](#top)]

## <a name="receive-and-try_receive"></a><a name="receive"></a>alma ve try_receive

[Concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) ve [concurrency:: try_receive](reference/concurrency-namespace-functions.md#try_receive) işlevleri belirli bir kaynaktaki verileri okur. İşlev, `receive` verilerin kullanılabilir hale gelmesini bekler, ancak `try_receive` işlev hemen döndürülür.

`receive`Devam etmek için verilerin olması gereken durumlarda işlevini kullanın. `try_receive`Geçerli bağlamı engellemeniz gerekiyorsa veya devam etmek için verilere sahip olmanız gerekmez işlevini kullanın.

[[Üst](#top)]

## <a name="examples"></a><a name="examples"></a>Örnekler

Ve işlevlerini kullanan örnekler için `send` `asend` `receive` aşağıdaki konulara bakın:

- [Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [Nasıl yapılır: çeşitli üretici tüketicisi desenleri uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)

- [Nasıl yapılır: çağrıya ve transformatör sınıflarına çalışma Işlevleri sağlama](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)

- [Nasıl yapılır: bir veri ardışık düzeninde transformatör kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)

- [Nasıl yapılır: tamamlanan görevler arasında seçim yapma](../../parallel/concrt/how-to-select-among-completed-tasks.md)

- [Nasıl yapılır: düzenli bir aralıkta Ileti gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)

- [Nasıl yapılır: Ileti bloğu filtresini kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Send Işlevi](reference/concurrency-namespace-functions.md#send)<br/>
[asend Işlevi](reference/concurrency-namespace-functions.md#asend)<br/>
[Receive Işlevi](reference/concurrency-namespace-functions.md#receive)<br/>
[try_receive Işlevi](reference/concurrency-namespace-functions.md#try_receive)

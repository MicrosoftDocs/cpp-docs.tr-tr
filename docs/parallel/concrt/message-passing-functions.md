---
title: İleti Geçirme İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
ms.openlocfilehash: 4e1052a59f355c4ad5a7c6b57724268c24a209b4
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143291"
---
# <a name="message-passing-functions"></a>İleti Geçirme İşlevleri

Zaman uyumsuz aracılar Kitaplığı, bileşenler arasında ileti iletmenizi sağlayan çeşitli işlevler sağlar.

Bu ileti geçirme işlevleri çeşitli ileti bloğu türleriyle kullanılır. Eşzamanlılık Çalışma Zamanı tarafından tanımlanan ileti bloğu türleri hakkında daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="top"></a>Başlıklı

Bu konuda aşağıdaki ileti geçirme işlevleri açıklanmaktadır:

- [gönderme ve asend](#send)

- [alma ve try_receive](#receive)

- [Örnekler](#examples)

## <a name="send"></a>gönderme ve asend

[Concurrency:: Send](reference/concurrency-namespace-functions.md#send) işlevi belirtilen hedefe zaman uyumlu bir ileti gönderir ve [concurrency:: asend](reference/concurrency-namespace-functions.md#asend) işlevi belirtilen hedefe zaman uyumsuz bir ileti gönderir. `send` ve `asend` işlevleri, hedef son olarak iletiyi kabul edeceğini veya reddetmesi gerektiğini belirtir.

`send` işlevi, hedefin döndürülünceye kadar iletiyi kabul etmesini veya reddetmesini bekler. `send` işlevi, ileti teslim edildiğinde **true** , aksi durumda **false** değerini döndürür. `send` işlevi zaman uyumlu olarak çalıştığından, `send` işlevi hedefin döndürülmadan önce iletiyi almasını bekler.

Buna karşılık `asend` işlevi, hedefin döndürülmeden önce iletiyi kabul etmesini veya reddetmesi için beklemez. Bunun yerine, hedef iletiyi kabul ettiğinde `asend` işlevi **true** değerini döndürür ve sonuç olarak alır. Aksi takdirde `asend`, hedefin iletiyi reddettiğini veya iletiyi alıp almayacağı kararı ertelemesini belirtmek için **false** döndürür.

[[Üst](#top)]

## <a name="receive"></a>alma ve try_receive

[Concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) ve [concurrency:: try_receive](reference/concurrency-namespace-functions.md#try_receive) işlevleri belirli bir kaynaktaki verileri okur. `receive` işlevi, verilerin kullanılabilir hale gelmesini bekler, ancak `try_receive` işlevi hemen döndürülür.

Devam etmek için verilerin olması gereken `receive` işlevini kullanın. Geçerli bağlam engellenmemelidir veya devam etmek için verilere sahip olmanız gerekmez `try_receive` işlevini kullanın.

[[Üst](#top)]

## <a name="examples"></a>Örnekler

`send` ve `asend`ve `receive` işlevleri kullanan örnekler için aşağıdaki konulara bakın:

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [Nasıl yapılır: Çeşitli Üretici-Tüketici Desenlerini Uygulama](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)

- [Nasıl yapılır: call ve transformer Sınıflarına İş İşlevleri Sağlama](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)

- [Nasıl yapılır: Veri İşlem Hattında transformer Kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)

- [Nasıl yapılır: Tamamlanan Görevler Arasında Seçim Yapma](../../parallel/concrt/how-to-select-among-completed-tasks.md)

- [Nasıl yapılır: Düzenli Aralıkla İleti Gönderme](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)

- [Nasıl yapılır: İleti Bloğu Filtresini Kullanma](../../parallel/concrt/how-to-use-a-message-block-filter.md)

[[Üst](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Send Işlevi](reference/concurrency-namespace-functions.md#send)<br/>
[asend Işlevi](reference/concurrency-namespace-functions.md#asend)<br/>
[Receive Işlevi](reference/concurrency-namespace-functions.md#receive)<br/>
[try_receive Işlevi](reference/concurrency-namespace-functions.md#try_receive)

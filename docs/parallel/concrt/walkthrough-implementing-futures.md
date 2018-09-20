---
title: 'İzlenecek yol: Vadeli işlemleri uygulama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- implementing futures [Concurrency Runtime]
- futures, implementing [Concurrency Runtime]
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a3131e785c134f2e4875612f2d8a994f19ac766
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447082"
---
# <a name="walkthrough-implementing-futures"></a>İzlenecek yol: Vadeli İşlemleri Uygulama

Bu konuda, uygulamanıza vadeli gösterilmektedir. Konu nasıl daha fazlasını yapan varolan işlevsellikte eşzamanlılık çalışma zamanı değerlerinizden birleştirileceğini gösterir.

> [!IMPORTANT]
>  Bu konuda vadeli tanıtım amacıyla kavramı gösterir. Kullanmanızı öneririz [std::future](../../standard-library/future-class.md) veya [concurrency::task](../../parallel/concrt/reference/task-class.md) gerekli olduğunda daha sonra kullanmak için bir değer hesaplayan zaman uyumsuz bir görev.

A *görev* ek, daha ayrıntılı hesaplamalar içinde ayrılmış bir hesaplama olduğu. A *gelecekteki* daha sonra kullanmak için bir değer hesaplayan zaman uyumsuz bir görevdir.

İleri tarihli işleri uygulamak için bu konuda tanımlar `async_future` sınıfı. `async_future` Sınıfı bu eşzamanlılık çalışma zamanı bileşenlerini kullanır: [concurrency::task_group](reference/task-group-class.md) sınıfı ve [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) sınıfı. `async_future` Sınıfının kullandığı `task_group` zaman uyumsuz olarak bir değeri hesaplamak için sınıf ve `single_assignment` biri hesaplama sonucunu depolamak için sınıf. Oluşturucusuna `async_future` sınıfı sonuç hesaplayan bir iş işlevi alır ve `get` yöntemi sonucu alır.

### <a name="to-implement-the-asyncfuture-class"></a>Async_future sınıfı uygulamak için

1. Adlandırılmış bir şablon sınıfı bildirmek `async_future` elde edilen hesaplama türüne göre parametreli. Ekleme `public` ve `private` Bu sınıf için bölümler.

[!code-cpp[concrt-futures#2](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_1.cpp)]

1. İçinde `private` bölümünü `async_future` sınıfı, bildirmek bir `task_group` ve `single_assignment` veri üyesi.

[!code-cpp[concrt-futures#3](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_2.cpp)]

1. İçinde `public` bölümünü `async_future` sınıfı, yapıcısını uygular. Oluşturucu sonucu hesaplar iş işlevi parametreli bir şablonudur. Oluşturucu çalışma işlevi içindeki zaman uyumsuz olarak yürütür `task_group` veri üyesi ve kullanımları [concurrency::send](reference/concurrency-namespace-functions.md#send) sonucu yazılacak işlev `single_assignment` veri üyesi.

[!code-cpp[concrt-futures#4](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_3.cpp)]

1. İçinde `public` bölümünü `async_future` sınıfı, yok edici uygulayın. Yok edici görevin tamamlanmasını bekler.

[!code-cpp[concrt-futures#5](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_4.cpp)]

1. İçinde `public` bölümünü `async_future` sınıfı, uygulama `get` yöntemi. Bu yöntemde [concurrency::receive](reference/concurrency-namespace-functions.md#receive) iş işlevin sonucu almak için işlevi.

[!code-cpp[concrt-futures#6](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_5.cpp)]

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, tam gösterir `async_future` sınıfı ve alt kullanım örneği. `wmain` İşlevi oluşturur bir std::[vektör](../../standard-library/vector-class.md) 10.000 rastgele tamsayı değerleri içeren nesne. Ardından kullanır `async_future` bulunan küçük ve en büyük değerleri bulmak için nesneleri `vector` nesne.

### <a name="code"></a>Kod

[!code-cpp[concrt-futures#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_6.cpp)]

### <a name="comments"></a>Açıklamalar

Bu örnek aşağıdaki çıktıyı üretir:

```Output
smallest: 0
largest:  9999
average:  4981
```

Örnekte `async_future::get` hesaplamanın sonuçlarını almak için yöntemi. `async_future::get` Yöntemi hesaplama Hesaplama hala etkinse bitmesini bekler.

## <a name="robust-programming"></a>Güçlü Programlama

Genişletmek için `async_future` iş işlevi tarafından oluşturulan özel durumları işlemek için değiştirme sınıfı `async_future::get` çağrılacak yöntem [CONCURRENCY::task_group:: wait](reference/task-group-class.md#wait) yöntemi. `task_group::wait` Yöntemi iş işlevi tarafından oluşturulan özel durumları oluşturur.

Aşağıdaki örnek, uygulamanın değiştirilmiş sürümünü gösterir. `async_future` sınıfı. `wmain` İşlevini kullanan bir `try` - `catch` sonucu yazdırmaya blok `async_future` nesne veya iş işlevi tarafından oluşturulan özel durum değerini yazdırmak için.

[!code-cpp[concrt-futures-with-eh#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_7.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
caught exception: error
```

Eşzamanlılık Çalışma zamanı özel durum işleme modeli hakkında daha fazla bilgi için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `futures.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc futures.cpp**

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[task_group sınıfı](reference/task-group-class.md)<br/>
[single_assignment Sınıfı](../../parallel/concrt/reference/single-assignment-class.md)

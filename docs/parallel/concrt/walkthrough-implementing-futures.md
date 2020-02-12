---
title: 'İzlenecek yol: Vadeli İşlemleri Uygulama'
ms.date: 04/25/2019
helpviewer_keywords:
- implementing futures [Concurrency Runtime]
- futures, implementing [Concurrency Runtime]
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
ms.openlocfilehash: 2b9d889dac195bb60651cbb76110d54b6231a5fd
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141987"
---
# <a name="walkthrough-implementing-futures"></a>İzlenecek yol: Vadeli İşlemleri Uygulama

Bu konuda, uygulamanızda Futures nasıl uygulanacağı gösterilmektedir. Konu başlığında, Eşzamanlılık Çalışma Zamanı var olan işlevselliğin daha fazlasını yapan bir şekilde nasıl birleştirileceğini gösterilmektedir.

> [!IMPORTANT]
> Bu konuda, tanıtım amaçlı olarak vadeli işlem kavramı gösterilmektedir. Daha sonra kullanmak üzere bir değer hesaplayan zaman uyumsuz bir görev gerektirdiğinde [std:: Future](../../standard-library/future-class.md) veya [concurrency:: Task](../../parallel/concrt/reference/task-class.md) kullanmanızı öneririz.

*Görev* , daha ayrıntılı, daha ayrıntılı, hesaplamalar halinde olabilecek bir hesaplamadır. *Gelecekte* , daha sonra kullanılmak üzere bir değeri hesaplayan zaman uyumsuz bir görevdir.

Bu konu, Futures uygulamak için `async_future` sınıfını tanımlar. `async_future` sınıfı Eşzamanlılık Çalışma Zamanı şu bileşenleri kullanır: [concurrency:: task_group](reference/task-group-class.md) Class ve [concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) sınıfı. `async_future` sınıfı, bir değeri zaman uyumsuz olarak hesaplamak için `task_group` sınıfını ve hesaplama sonucunu depolamak için `single_assignment` sınıfını kullanır. `async_future` sınıfının Oluşturucusu sonucu hesaplayan bir çalışma işlevi alır ve `get` yöntemi sonucu alır.

### <a name="to-implement-the-async_future-class"></a>Async_future sınıfı uygulamak için

1. Sonuç hesaplamasının türü üzerinde parametreli olan `async_future` adlı bir şablon sınıfı bildirin. Bu sınıfa `public` ve `private` bölümleri ekleyin.

[!code-cpp[concrt-futures#2](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_1.cpp)]

1. `async_future` sınıfının `private` bölümünde, bir `task_group` ve `single_assignment` veri üyesi bildirin.

[!code-cpp[concrt-futures#3](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_2.cpp)]

1. `async_future` sınıfının `public` bölümünde oluşturucuyu uygulayın. Oluşturucu, sonucu hesaplayan iş işlevinde parametreli bir şablondur. Oluşturucu, `task_group` veri üyesinde iş işlevini zaman uyumsuz olarak yürütür ve sonucu `single_assignment` veri üyesine yazmak için [concurrency:: Send](reference/concurrency-namespace-functions.md#send) işlevini kullanır.

[!code-cpp[concrt-futures#4](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_3.cpp)]

1. `async_future` sınıfının `public` bölümünde yıkıcıyı uygulayın. Yıkıcı görevin bitmesini bekler.

[!code-cpp[concrt-futures#5](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_4.cpp)]

1. `async_future` sınıfının `public` bölümünde `get` yöntemini uygulayın. Bu yöntem, iş işlevinin sonucunu almak için [concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) işlevini kullanır.

[!code-cpp[concrt-futures#6](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_5.cpp)]

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, tüm `async_future` sınıfını ve kullanım örneğini göstermektedir. `wmain` işlevi, 10.000 rastgele tamsayı değeri içeren bir std::[Vector](../../standard-library/vector-class.md) nesnesi oluşturur. Daha sonra, `vector` nesnesinde bulunan en küçük ve en büyük değerleri bulmak için `async_future` nesneleri kullanır.

### <a name="code"></a>Kod

[!code-cpp[concrt-futures#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_6.cpp)]

### <a name="comments"></a>Açıklamalar

Bu örnek aşağıdaki çıktıyı üretir:

```Output
smallest: 0
largest:  9999
average:  4981
```

Örnek, hesaplamanın sonuçlarını almak için `async_future::get` yöntemini kullanır. `async_future::get` yöntemi hesaplamanın hala etkin olması durumunda hesaplamanın bitmesini bekler.

## <a name="robust-programming"></a>Güçlü Programlama

`async_future` sınıfını iş işlevi tarafından oluşturulan özel durumları işleyecek şekilde genişletmek için, `async_future::get` metodunu [concurrency:: task_group:: wait](reference/task-group-class.md#wait) metodunu çağırmak üzere değiştirin. `task_group::wait` yöntemi, iş işlevi tarafından oluşturulan tüm özel durumları oluşturur.

Aşağıdaki örnekte `async_future` sınıfının değiştirilmiş sürümü gösterilmektedir. `wmain` işlevi, `async_future` nesnesinin sonucunu yazdırmak için veya çalışma işlevi tarafından oluşturulan özel durumun değerini yazdırmak için bir `try`-`catch` bloğunu kullanır.

[!code-cpp[concrt-futures-with-eh#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_7.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
caught exception: error
```

Eşzamanlılık Çalışma Zamanı özel durum işleme modeli hakkında daha fazla bilgi için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `futures.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

**CL. exe/EHsc Futures. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[task_group Sınıfı](reference/task-group-class.md)<br/>
[single_assignment Sınıfı](../../parallel/concrt/reference/single-assignment-class.md)

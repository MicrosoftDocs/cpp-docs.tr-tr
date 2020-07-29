---
title: 'İzlenecek yol: Vadeli İşlemleri Uygulama'
ms.date: 04/25/2019
helpviewer_keywords:
- implementing futures [Concurrency Runtime]
- futures, implementing [Concurrency Runtime]
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
ms.openlocfilehash: 9bf46b7f2a761aaf0c07e1017524c8ddf533aca6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230304"
---
# <a name="walkthrough-implementing-futures"></a>İzlenecek yol: Vadeli İşlemleri Uygulama

Bu konuda, uygulamanızda Futures nasıl uygulanacağı gösterilmektedir. Konu başlığında, Eşzamanlılık Çalışma Zamanı var olan işlevselliğin daha fazlasını yapan bir şekilde nasıl birleştirileceğini gösterilmektedir.

> [!IMPORTANT]
> Bu konuda, tanıtım amaçlı olarak vadeli işlem kavramı gösterilmektedir. Daha sonra kullanmak üzere bir değer hesaplayan zaman uyumsuz bir görev gerektirdiğinde [std:: Future](../../standard-library/future-class.md) veya [concurrency:: Task](../../parallel/concrt/reference/task-class.md) kullanmanızı öneririz.

*Görev* , daha ayrıntılı, daha ayrıntılı, hesaplamalar halinde olabilecek bir hesaplamadır. *Gelecekte* , daha sonra kullanılmak üzere bir değeri hesaplayan zaman uyumsuz bir görevdir.

Bu konu, Futures uygulamak için sınıfını tanımlar `async_future` . `async_future`Sınıfı eşzamanlılık çalışma zamanı: [concurrency:: task_group](reference/task-group-class.md) Class ve [concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) sınıfının bu bileşenlerini kullanır. `async_future`Sınıfı, `task_group` bir değeri zaman uyumsuz olarak hesaplamak için sınıfını ve `single_assignment` Hesaplama sonucunu depolamak için sınıfını kullanır. `async_future`Sınıfının Oluşturucusu sonucu hesaplayan bir çalışma işlevi alır ve `get` Yöntem sonucu alır.

### <a name="to-implement-the-async_future-class"></a>Async_future sınıfı uygulamak için

1. `async_future`Elde edilen hesaplamanın türü üzerinde parametreli olan adlı bir şablon sınıfı bildirin. **`public`** **`private`** Bu sınıfa bölüm ekleyin.

[!code-cpp[concrt-futures#2](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_1.cpp)]

1. **`private`** `async_future` Sınıfının bölümünde, bir `task_group` ve bir `single_assignment` veri üyesi bildirin.

[!code-cpp[concrt-futures#3](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_2.cpp)]

1. **`public`** `async_future` Sınıfının bölümünde, oluşturucuyu uygulayın. Oluşturucu, sonucu hesaplayan iş işlevinde parametreli bir şablondur. Oluşturucu veri üyesinde iş işlevini zaman uyumsuz olarak yürütür `task_group` ve sonucu veri üyesine yazmak için [concurrency:: Send](reference/concurrency-namespace-functions.md#send) işlevini kullanır `single_assignment` .

[!code-cpp[concrt-futures#4](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_3.cpp)]

1. **`public`** `async_future` Sınıfının bölümünde yıkıcıyı uygulayın. Yıkıcı görevin bitmesini bekler.

[!code-cpp[concrt-futures#5](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_4.cpp)]

1. **`public`** `async_future` Sınıfının bölümünde `get` yöntemini uygulayın. Bu yöntem, iş işlevinin sonucunu almak için [concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) işlevini kullanır.

[!code-cpp[concrt-futures#6](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_5.cpp)]

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, `async_future` bir bütün sınıfı ve kullanım örneğini göstermektedir. `wmain`İşlevi, 10.000 rastgele tamsayı değerleri içeren bir std::[Vector](../../standard-library/vector-class.md) nesnesi oluşturur. Ardından `async_future` nesne içinde bulunan en küçük ve en büyük değerleri bulmak için nesneleri kullanır `vector` .

### <a name="code"></a>Kod

[!code-cpp[concrt-futures#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_6.cpp)]

### <a name="comments"></a>Yorumlar

Bu örnek aşağıdaki çıktıyı üretir:

```Output
smallest: 0
largest:  9999
average:  4981
```

Örnek, `async_future::get` hesaplamanın sonuçlarını almak için yöntemini kullanır. `async_future::get`Yöntemi, hesaplamanın hala etkin olması durumunda hesaplamanın bitmesini bekler.

## <a name="robust-programming"></a>Güçlü Programlama

`async_future`Sınıfı, iş işlevi tarafından oluşturulan özel durumları işleyecek şekilde genişletmek için, `async_future::get` yöntemini [concurrency:: task_group:: wait](reference/task-group-class.md#wait) yöntemini çağıracak şekilde değiştirin. `task_group::wait`Yöntemi, iş işlevi tarafından oluşturulan tüm özel durumları atar.

Aşağıdaki örnekte, sınıfının değiştirilmiş sürümü gösterilmektedir `async_future` . `wmain`İşlevi **`try`** - **`catch`** nesnenin sonucunu yazdırmak için `async_future` veya çalışma işlevi tarafından oluşturulan özel durumun değerini yazdırmak için bir blok kullanır.

[!code-cpp[concrt-futures-with-eh#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_7.cpp)]

Bu örnek aşağıdaki çıktıyı üretir:

```Output
caught exception: error
```

Eşzamanlılık Çalışma Zamanı özel durum işleme modeli hakkında daha fazla bilgi için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `futures.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/EHsc Futures. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı Izlenecek yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[task_group sınıfı](reference/task-group-class.md)<br/>
[single_assignment sınıfı](../../parallel/concrt/reference/single-assignment-class.md)

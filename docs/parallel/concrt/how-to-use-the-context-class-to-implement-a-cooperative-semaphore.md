---
title: 'Nasıl yapılır: Bağlam Sınıfını İşbirlikçi Semafor Uygulamak için Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- cooperative semaphore implementing
- context class
ms.assetid: 22f4b9c0-ca22-4a68-90ba-39e99ea76696
ms.openlocfilehash: 77cf33288761c75d056649ebe27f9d74c6fa62dc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230395"
---
# <a name="how-to-use-the-context-class-to-implement-a-cooperative-semaphore"></a>Nasıl yapılır: Bağlam Sınıfını İşbirlikçi Semafor Uygulamak için Kullanma

Bu konu, ortak bir semafor sınıfı uygulamak için concurrency:: Context sınıfının nasıl kullanılacağını gösterir.

## <a name="remarks"></a>Açıklamalar

`Context`Sınıfı geçerli yürütme bağlamını engellemenize veya yapmanızı sağlar. Bir kaynak kullanılamadığından geçerli bağlam devam edemediği için, geçerli bağlamı engelleme veya durdurma yararlı olur. *Semafor* , geçerli yürütme bağlamının bir kaynağın kullanılabilir hale gelmesini beklemesi gereken bir durum örneğidir. Kritik bölüm nesnesi gibi bir semafor, bir bağlamdaki kodun bir kaynağa özel erişim sahibi olmasını sağlayan bir eşitleme nesnesidir. Ancak, kritik bölüm nesnesinden farklı olarak, bir semafor kaynağa aynı anda erişmek için birden fazla bağlam sağlar. En fazla bağlam sayısı bir semafor kilidi içeriyorsa, her ek bağlamın kilidi serbest bırakmaları için başka bir bağlam beklemesi gerekir.

### <a name="to-implement-the-semaphore-class"></a>Semafor sınıfını uygulamak için

1. Adlı bir sınıf bildirin `semaphore` . **`public`** **`private`** Bu sınıfa bölüm ekleyin.

[!code-cpp[concrt-cooperative-semaphore#1](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_1.cpp)]

1. **`private`** `semaphore` Sınıfının bölümünde, semafor sayısını tutan bir [std:: atomik](../../standard-library/atomic-structure.md) değişken ve semaforu elde etmek için beklemesi gereken bağlamların bulunduğu bir [concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) nesnesi bildirin.

[!code-cpp[concrt-cooperative-semaphore#2](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_2.cpp)]

1. **`public`** `semaphore` Sınıfının bölümünde, oluşturucuyu uygulayın. Oluşturucu, **`long long`** kilidi eşzamanlı olarak tutan en fazla bağlam sayısını belirten bir değer alır.

[!code-cpp[concrt-cooperative-semaphore#3](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_3.cpp)]

1. **`public`** `semaphore` Sınıfının bölümünde `acquire` yöntemini uygulayın. Bu yöntem, semafor sayısını atomik bir işlem olarak azaltır. Semafor sayısı negatif hale gelirse, geçerli bağlamı bekleme sırasının sonuna ekleyin ve geçerli bağlamı engellemek için [concurrency:: Context:: Block](reference/context-class.md#block) metodunu çağırın.

[!code-cpp[concrt-cooperative-semaphore#4](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_4.cpp)]

1. **`public`** `semaphore` Sınıfının bölümünde `release` yöntemini uygulayın. Bu yöntem, semafor sayısını atomik bir işlem olarak artırır. Semafor sayısı, artırma işleminden önce negatifse, kilidi bekleyen en az bir bağlam vardır. Bu durumda, bekleme sırasının önünde olan bağlamın engelini kaldırın.

[!code-cpp[concrt-cooperative-semaphore#5](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_5.cpp)]

## <a name="example"></a>Örnek

`semaphore` `Context::Block` Ve `Context::Yield` yöntemleri çalışma zamanının diğer görevleri gerçekleştirebilmesi için yürütme yaptığından, bu örnekteki sınıf birlikte çalışır.

`acquire`Yöntemi sayacı azaltır, ancak başka bir bağlam metodu çağırmadan önce bu bağlamı bekleme kuyruğuna eklemeyi bitiremeyebilir `release` . Bu şekilde, yöntemi için, yönteminin `release` bağlamı ekleme işleminin bitmesini beklemek için [eşzamanlılık:: Context:: yield](reference/context-class.md#yield) yöntemini çağıran bir döndürme döngüsü kullanır `acquire` .

Yöntemi metodu çağırmadan `release` önce yöntemi çağırabilir `Context::Unblock` `acquire` `Context::Block` . Çalışma zamanı bu yöntemlerin herhangi bir sırada çağrılmasına izin verdiğinden, bu yarış durumuna karşı korumanız gerekmez. Yöntemi, `release` `Context::Unblock` `acquire` metodu aynı bağlam için çağrı yapmadan önce çağırırsa `Context::Block` , bu bağlam engellenmeye devam eder. Çalışma zamanı yalnızca her `Context::Block` bir çağrısının öğesine karşılık gelen çağrısıyla eşleştirilmesini gerektirir `Context::Unblock` .

Aşağıdaki örnek, tüm sınıfı gösterir `semaphore` . `wmain`İşlevi bu sınıfın temel kullanımını gösterir. `wmain`İşlevi, semafora erişmesi gereken birkaç görev oluşturmak için [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını kullanır. Her seferinde üç iş parçacığı kilidi tutabildiğinden, bazı görevlerin başka bir görevin bitmesini beklemesi ve kilidi serbest bırakmaları gerekir.

[!code-cpp[concrt-cooperative-semaphore#6](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_6.cpp)]

Bu örnek, aşağıdaki örnek çıktıyı üretir.

```Output
In loop iteration 5...
In loop iteration 0...
In loop iteration 6...
In loop iteration 1...
In loop iteration 2...
In loop iteration 7...
In loop iteration 3...
In loop iteration 8...
In loop iteration 9...
In loop iteration 4...
```

Sınıfı hakkında daha fazla bilgi için `concurrent_queue` bkz. [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md). Algoritma hakkında daha fazla bilgi için `parallel_for` bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `cooperative-semaphore.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Cooperative-Semaphore. cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Bir nesneye erişimi verilen bir kapsama sınırlamak için *kaynak alımı başlatma* (rampa) modelini kullanabilirsiniz `semaphore` . OYıı deseninin altında, yığın üzerinde bir veri yapısı ayrılır. Bu veri yapısı oluşturulduğunda bir kaynağı başlatır veya alır ve veri yapısı yok edildiğinde bu kaynağı yok eder veya serbest bırakır. RAMPALAMA kapsamı, yok edicinin kapsayan kapsam gelmeden önce çağrıldığından emin olur. Bu nedenle, bir özel durum oluştuğunda veya bir işlev birden çok deyim içerdiğinde kaynak doğru bir şekilde yönetilir **`return`** .

Aşağıdaki örnek `scoped_lock` , sınıfının bölümünde tanımlanan adlı bir sınıfı tanımlar **`public`** `semaphore` . `scoped_lock`Sınıf [concurrency:: critical_section:: scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) ve [concurrency:: reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) sınıflarına benzer. Sınıfının Oluşturucusu, `semaphore::scoped_lock` verilen nesneye erişim sağlar `semaphore` ve yıkıcı bu nesneye erişimi yayınlar.

[!code-cpp[concrt-cooperative-semaphore#7](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_7.cpp)]
Aşağıdaki örnek, `parallel_for` algoritmanın işlevin dönüşünden önce serbest bırakılacağını sağlamak için, algoritmaya geçirilen çalışma işlevinin gövdesini değiştirir. Bu teknik, çalışma işlevinin özel durum açısından güvenli olmasını sağlar.

[!code-cpp[concrt-cooperative-semaphore#8](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_8.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Bağlamlar](../../parallel/concrt/contexts.md)<br/>
[Paralel Kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md)

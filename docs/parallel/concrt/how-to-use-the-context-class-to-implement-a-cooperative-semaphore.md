---
title: 'Nasıl yapılır: Bağlam Sınıfını İşbirlikçi Semafor Uygulamak için Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- cooperative semaphore implementing
- context class
ms.assetid: 22f4b9c0-ca22-4a68-90ba-39e99ea76696
ms.openlocfilehash: 5075052592993f413290242e70206b1e227064aa
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141899"
---
# <a name="how-to-use-the-context-class-to-implement-a-cooperative-semaphore"></a>Nasıl yapılır: Bağlam Sınıfını İşbirlikçi Semafor Uygulamak için Kullanma

Bu konu, ortak bir semafor sınıfı uygulamak için concurrency:: Context sınıfının nasıl kullanılacağını gösterir.

## <a name="remarks"></a>Açıklamalar

`Context` sınıfı, geçerli yürütme bağlamını engellemenize veya yapmanızı sağlar. Bir kaynak kullanılamadığından geçerli bağlam devam edemediği için, geçerli bağlamı engelleme veya durdurma yararlı olur. *Semafor* , geçerli yürütme bağlamının bir kaynağın kullanılabilir hale gelmesini beklemesi gereken bir durum örneğidir. Kritik bölüm nesnesi gibi bir semafor, bir bağlamdaki kodun bir kaynağa özel erişim sahibi olmasını sağlayan bir eşitleme nesnesidir. Ancak, kritik bölüm nesnesinden farklı olarak, bir semafor kaynağa aynı anda erişmek için birden fazla bağlam sağlar. En fazla bağlam sayısı bir semafor kilidi içeriyorsa, her ek bağlamın kilidi serbest bırakmaları için başka bir bağlam beklemesi gerekir.

### <a name="to-implement-the-semaphore-class"></a>Semafor sınıfını uygulamak için

1. `semaphore`adlı bir sınıf bildirin. Bu sınıfa `public` ve `private` bölümleri ekleyin.

[!code-cpp[concrt-cooperative-semaphore#1](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_1.cpp)]

1. `semaphore` sınıfının `private` bölümünde, semafor sayısını tutan bir [std:: atomik](../../standard-library/atomic-structure.md) değişken ve semaforu elde etmek için beklemesi gereken bağlamların bulunduğu bir [concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) nesnesi bildirin.

[!code-cpp[concrt-cooperative-semaphore#2](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_2.cpp)]

1. `semaphore` sınıfının `public` bölümünde oluşturucuyu uygulayın. Oluşturucu, kilidi eşzamanlı olarak tutan en fazla bağlam sayısını belirten bir `long long` değeri alır.

[!code-cpp[concrt-cooperative-semaphore#3](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_3.cpp)]

1. `semaphore` sınıfının `public` bölümünde `acquire` yöntemini uygulayın. Bu yöntem, semafor sayısını atomik bir işlem olarak azaltır. Semafor sayısı negatif hale gelirse, geçerli bağlamı bekleme sırasının sonuna ekleyin ve geçerli bağlamı engellemek için [concurrency:: Context:: Block](reference/context-class.md#block) metodunu çağırın.

[!code-cpp[concrt-cooperative-semaphore#4](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_4.cpp)]

1. `semaphore` sınıfının `public` bölümünde `release` yöntemini uygulayın. Bu yöntem, semafor sayısını atomik bir işlem olarak artırır. Semafor sayısı, artırma işleminden önce negatifse, kilidi bekleyen en az bir bağlam vardır. Bu durumda, bekleme sırasının önünde olan bağlamın engelini kaldırın.

[!code-cpp[concrt-cooperative-semaphore#5](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_5.cpp)]

## <a name="example"></a>Örnek

Bu örnekteki `semaphore` sınıfı, `Context::Block` ve `Context::Yield` yöntemleri çalışma zamanının diğer görevleri gerçekleştirebilmesi için yürütme işlemi yaptığından, birlikte çalışır.

`acquire` yöntemi sayacı azaltır, ancak başka bir bağlam `release` yöntemini çağırmadan önce bu bağlamı bekleme kuyruğuna eklemeyi bitiremeyebilir. Bu şekilde hesaba geçmek için `release` yöntemi, `acquire` yönteminin bağlamı ekleme işleminin bitmesini beklemek için [concurrency:: Context:: yield](reference/context-class.md#yield) metodunu çağıran bir döndürme döngüsü kullanır.

`release` yöntemi, `acquire` yöntemi `Context::Block` yöntemini çağırmadan önce `Context::Unblock` metodunu çağırabilir. Çalışma zamanı bu yöntemlerin herhangi bir sırada çağrılmasına izin verdiğinden, bu yarış durumuna karşı korumanız gerekmez. `release` yöntemi `acquire` Yöntem aynı bağlam için `Context::Block` çağırmadan önce `Context::Unblock` çağırırsa, bu bağlam engellenmeye devam eder. Çalışma zamanı yalnızca `Context::Block` yapılan her çağrının `Context::Unblock`karşılık gelen çağrısıyla eşleştirilmesini gerektirir.

Aşağıdaki örnek, tüm `semaphore` sınıfını gösterir. `wmain` işlevi bu sınıfın temel kullanımını gösterir. `wmain` işlevi, semafora erişmesi gereken birkaç görev oluşturmak için [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını kullanır. Her seferinde üç iş parçacığı kilidi tutabildiğinden, bazı görevlerin başka bir görevin bitmesini beklemesi ve kilidi serbest bırakmaları gerekir.

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

`concurrent_queue` sınıfı hakkında daha fazla bilgi için bkz. [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md). `parallel_for` algoritması hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `cooperative-semaphore.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc Cooperative-Semaphore. cpp**

## <a name="robust-programming"></a>Güçlü Programlama

`semaphore` nesnesine erişimi verilen bir kapsama sınırlamak için *kaynak alımı başlatma* (rampa) modelini kullanabilirsiniz. OYıı deseninin altında, yığın üzerinde bir veri yapısı ayrılır. Bu veri yapısı oluşturulduğunda bir kaynağı başlatır veya alır ve veri yapısı yok edildiğinde bu kaynağı yok eder veya serbest bırakır. RAMPALAMA kapsamı, yok edicinin kapsayan kapsam gelmeden önce çağrıldığından emin olur. Bu nedenle, bir özel durum oluştuğunda veya bir işlev birden çok `return` deyimi içerdiğinde kaynak doğru bir şekilde yönetilir.

Aşağıdaki örnek, `semaphore` sınıfının `public` bölümünde tanımlanan `scoped_lock`adlı bir sınıfı tanımlar. `scoped_lock` sınıfı [concurrency:: critical_section:: scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) ve [concurrency:: reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) sınıflarına benzer. `semaphore::scoped_lock` sınıfının Oluşturucusu verilen `semaphore` nesnesine erişim sağlar ve yıkıcı bu nesneye erişimi yayınlar.

[!code-cpp[concrt-cooperative-semaphore#7](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_7.cpp)]
Aşağıdaki örnek, işlevin dönüşünden önce semaforun serbest bırakılacağını sağlamak üzere `parallel_for` algoritmasına geçirilen çalışma işlevinin gövdesini değiştirir. Bu teknik, çalışma işlevinin özel durum açısından güvenli olmasını sağlar.

[!code-cpp[concrt-cooperative-semaphore#8](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_8.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Bağlamlar](../../parallel/concrt/contexts.md)<br/>
[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)

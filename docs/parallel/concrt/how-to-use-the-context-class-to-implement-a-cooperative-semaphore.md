---
title: 'Nasıl yapılır: bağlam sınıfını işbirlikçi semafor uygulamak için kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- cooperative semaphore implementing
- context class
ms.assetid: 22f4b9c0-ca22-4a68-90ba-39e99ea76696
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 384fe7674ff24af0250dede7cb4bafda0106bf46
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424787"
---
# <a name="how-to-use-the-context-class-to-implement-a-cooperative-semaphore"></a>Nasıl yapılır: Bağlam Sınıfını İşbirlikçi Semafor Uygulamak için Kullanma

Bu konuda, concurrency::Context sınıfını işbirlikçi semafor sınıfını uygulamak için kullanma gösterilmektedir.

`Context` Sınıfı, engelleme ya da geçerli yürütme bağlamı yield olanak tanır. Bir kaynak kullanılabilir olmadığından geçerli bağlam devam edemiyor engelleme ya da geçerli bağlam sonuçlanmıyor yararlı olur. A *semafor* burada geçerli yürütme bağlamı beklemesi gereken bir kaynak kullanılabilir hale gelmesi bir durum örneğidir. Semafor, bir kritik bölüm nesnesi gibi özel bir kaynağa erişimi için bir bağlam kodunda etkinleştiren bir eşitleme nesnesi olan. Ancak, kritik bölüm nesnesinin aksine, eşzamanlı olarak kaynağa erişmek birden fazla bağlam semafor sağlar. Semafor kilit bağlamları en fazla sayısını tutar, her ek bağlam Kilidi açmak başka bir bağlam için beklemeniz gerekir.

### <a name="to-implement-the-semaphore-class"></a>Semafor sınıfını uygulamak için

1. Adlı bir sınıf bildirme `semaphore`. Ekleme `public` ve `private` Bu sınıf için bölümler.

[!code-cpp[concrt-cooperative-semaphore#1](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_1.cpp)]

1. İçinde `private` bölümünü `semaphore` sınıfı, bildirmek bir [std::atomic](../../standard-library/atomic-structure.md) semafor tutar değişkeni ve [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) bağlamları tutan nesne Semafor almak için beklemeniz gerekir.

[!code-cpp[concrt-cooperative-semaphore#2](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_2.cpp)]

1. İçinde `public` bölümünü `semaphore` sınıfı, yapıcısını uygular. Oluşturucuya alan bir `long long` eşzamanlı olarak kilidi tutan bağlamları üst sınırını belirten bir değer.

[!code-cpp[concrt-cooperative-semaphore#3](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_3.cpp)]

1. İçinde `public` bölümünü `semaphore` sınıfı, uygulama `acquire` yöntemi. Bu yöntem azaltır Semafor atomik işlem sayılır. Semafor sayısı negatif olduğunda geçerli bağlam çağrısı ve bekleme kuyruğu sonuna ekleyin. [concurrency::Context::Block](reference/context-class.md#block) geçerli bağlam engellemek için yöntemi.

[!code-cpp[concrt-cooperative-semaphore#4](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_4.cpp)]

1. İçinde `public` bölümünü `semaphore` sınıfı, uygulama `release` yöntemi. Bu yöntem, bir atomik işlem olarak semafor sayısını artırır. Önce Artım işlemi semafor sayı negatifse, kilit için bekleyen en az bir bağlam yoktur. Bu durumda, bekleme kuyruğun önündeki bağlam engeli kaldırın.

[!code-cpp[concrt-cooperative-semaphore#5](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_5.cpp)]

## <a name="example"></a>Örnek

`semaphore` Sınıfı bu örnekte davranışını işbirliği içerisinde devamlılığı çünkü `Context::Block` ve `Context::Yield` yöntemleri yürütme çalışma zamanı diğer görevleri gerçekleştirebilmeleri için yield.

`acquire` Sayacı, ancak değil son bağlamı başka bir bağlam çağrıları bekleme kuyrukta ekleme yöntemi azaltır `release` yöntemi. Bunun için hesap için `release` yöntemi çağıran bir döndürme döngüsü kullanır [concurrency::Context::Yield](reference/context-class.md#yield) beklemek yöntemi `acquire` bağlam ekleme işlemini sonlandırmak için yöntemi.

`release` Yöntemi çağırabilir `Context::Unblock` yöntemi önce `acquire` yöntem çağrılarını `Context::Block` yöntemi. Bu yöntemlerin herhangi bir sırada çağrılacak çalışma zamanı izin verdiğinden bu yarış karşı korumak sahip değilsiniz. Varsa `release` yöntem çağrılarını `Context::Unblock` önce `acquire` yöntem çağrılarını `Context::Block` aynı içerik için bu bağlamı engeli kalır. Çalışma zamanı, yalnızca her için çağırmanızı gerektirir `Context::Block` karşılık gelen bir çağrı ile eşleşen `Context::Unblock`.

Aşağıdaki örnek, tam gösterir `semaphore` sınıfı. `wmain` İşlevi bu sınıfın temel kullanımını gösterir. `wmain` İşlevini kullanan [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını semafor erişim gerektiren bazı görevler oluşturun. Üç iş parçacığı herhangi bir zamanda kilit içerebileceği için bazı görevler için başka bir görevi bitirmek ve kilidi beklemeniz gerekir.

[!code-cpp[concrt-cooperative-semaphore#6](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_6.cpp)]

Bu örnek, aşağıdaki örnek çıktısı üretir.

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

Hakkında daha fazla bilgi için `concurrent_queue` sınıfı [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md). Hakkında daha fazla bilgi için `parallel_for` algoritmasını bkz [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `cooperative-semaphore.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc Guyana semaphore.cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Kullanabileceğiniz *olduğu kaynak alımı başlatma* (RAII) deseni erişimi sınırlamak için bir `semaphore` nesne belirli bir kapsama. RAII deseni altında bir veri yapısı yığında ayrılır. Bu veri yapısını başlatır veya bir kaynak oluşturulur ve yok eder veya veri yapısı kaldırıldığında bu kaynağı yayınlar zaman alır. RAII deseni kapsayan kapsam çıkar önce yok Edicisi çağrılır garanti eder. Bu nedenle, kaynağın doğru bir özel durum oluştuğunda ya da birden çok işlev içerdiğinde, yönetilen `return` deyimleri.

Aşağıdaki örnekte adlı bir sınıf tanımlar `scoped_lock`, tanımlanan `public` bölümünü `semaphore` sınıfı. `scoped_lock` Sınıfına benzer [concurrency::critical_section::scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) ve [concurrency::reader_writer_lock::scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) sınıfları. Oluşturucusuna `semaphore::scoped_lock` sınıfı edinme erişim verilen `semaphore` nesne ve yok edici bu nesneye erişimi serbest bırakır.

[!code-cpp[concrt-cooperative-semaphore#7](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_7.cpp)]
Aşağıdaki örnek, geçirilen iş işlev gövdesini değiştirir `parallel_for` BT'nin RAII semafor işlevi döndürmeden önce yayımlanan emin olmak için kullanır. böylece algoritması. Bu teknik, iş işlev özel durum açısından güvenli olmasını sağlar.

[!code-cpp[concrt-cooperative-semaphore#8](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_8.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlamlar](../../parallel/concrt/contexts.md)<br/>
[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)


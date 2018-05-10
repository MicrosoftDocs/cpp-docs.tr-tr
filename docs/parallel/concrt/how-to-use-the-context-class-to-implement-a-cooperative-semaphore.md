---
title: 'Nasıl yapılır: bağlam sınıfını işbirlikçi semafor uygulamak için kullanın | Microsoft Docs'
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
ms.openlocfilehash: 481c5f092becee7f455294437bdc695a6e1e4057
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-the-context-class-to-implement-a-cooperative-semaphore"></a>Nasıl yapılır: Bağlam Sınıfını İşbirlikçi Semafor Uygulamak için Kullanma
Bu konu concurrency::Context sınıfını işbirlikçi semafor sınıfı uygulamak için nasıl kullanılacağını gösterir.  
  
 `Context` Sınıfı engellemek ya da geçerli yürütme bağlamı verim olanak sağlar. Bir kaynak kullanılabilir olmadığından geçerli bağlamı devam edemiyor engelleme ya da geçerli bağlamı oluşturan yararlıdır. A *semafor* burada geçerli yürütme bağlamı beklemesi gereken bir kaynak kullanılabilir hale gelmesi bir durum örneğidir. Bir kritik bölüm nesne gibi bir semafor özel bir kaynağa erişim sağlamak için bir bağlam kodda sağlayan bir eşitleme nesnesidir. Ancak, bir kritik bölüm nesnesi semafor kaynağa eşzamanlı olarak erişmek birden fazla bağlam sağlar. Bağlamları üst sınırını semafor kilit barındırıyorsa, her ek bağlam kilidi serbest bırakmak başka bir bağlam için beklemeniz gerekir.  
  
### <a name="to-implement-the-semaphore-class"></a>Semafor sınıfını uygulamak için  
  
1.  Adlı bir sınıf bildirme `semaphore`. Ekleme `public` ve `private` bu sınıfa bölümler.  
  
 [!code-cpp[concrt-cooperative-semaphore#1](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_1.cpp)]  
  
2.  İçinde `private` bölümünü `semaphore` sınıfı, bildirme bir [std::atomic](../../standard-library/atomic-structure.md) semafor sayısı tutan değişken ve [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) bağlamları tutan nesnesi Semafor edinmeye beklemeniz gerekir.  
  
 [!code-cpp[concrt-cooperative-semaphore#2](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_2.cpp)]  
  
3.  İçinde `public` bölümünü `semaphore` sınıfı, Oluşturucusu uygulayın. Oluşturucuya alan bir `long long` kilidi eşzamanlı olarak tutabilir bağlamları en fazla sayısını belirten değer.  
  
 [!code-cpp[concrt-cooperative-semaphore#3](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_3.cpp)]  

4.  İçinde `public` bölümünü `semaphore` sınıfı, uygulama `acquire` yöntemi. Bu yöntem azaltır Semafor atomik bir işlem olarak sayılır. Semafor sayısı negatif olursa, geçerli bağlam çağrısı ve bekleme sıra sonuna ekleyin [concurrency::Context::Block](reference/context-class.md#block) geçerli bağlamı engellemek için yöntem.  
  
 [!code-cpp[concrt-cooperative-semaphore#4](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_4.cpp)]  
  
5.  İçinde `public` bölümünü `semaphore` sınıfı, uygulama `release` yöntemi. Bu yöntem, atomik bir işlem olarak semafor sayısını artırır. Semafor sayısı önce artırma işlemi negatifse kilidi beklerken en az bir bağlam yoktur. Bu durumda, bekleme sırasının öne olan bağlamına engellemesini.  
  
 [!code-cpp[concrt-cooperative-semaphore#5](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_5.cpp)]  
  
## <a name="example"></a>Örnek  
 `semaphore` Sınıfı bu örnekte davranır işlevinizde çünkü `Context::Block` ve `Context::Yield` yöntemleri verim yürütme böylece çalışma zamanı başka görevler gerçekleştirebilirsiniz.  
  
 `acquire` Sayacı, ancak değil son önce başka bir bağlam çağrıları bekleme kuyruğuna bağlam ekleme yöntemi azaltır `release` yöntemi. Bunun için hesap için `release` yöntemini çağıran bir döndürme döngü kullanır [concurrency::Context::Yield](reference/context-class.md#yield) için beklenecek yöntemi `acquire` bağlam ekleme işlemini sonlandırmak için yöntem.  
  
 `release` Yöntemi çağırabilirsiniz `Context::Unblock` yönteminden önce `acquire` yöntem çağrılarını `Context::Block` yöntemi. Çalışma zamanı bu yöntemlerin herhangi bir sırada çağrılacak sağladığından Bu yarış durumu karşı korumak yok. Varsa `release` yöntem çağrılarını `Context::Unblock` önce `acquire` yöntem çağrılarını `Context::Block` aynı içerik için bu bağlam engeli kalır. Çalışma zamanı yalnızca her için çağrı gerektirir `Context::Block` karşılık gelen çağrısıyla eşleşen `Context::Unblock`.  
  
 Aşağıdaki örnek eksiksiz gösterir `semaphore` sınıfı. `wmain` İşlevi bu sınıfın temel kullanım gösterir. `wmain` İşlev kullandığı [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) semafor erişim gerektiren çeşitli görevleri oluşturmak üzere algoritması. Üç iş parçacığı herhangi bir zamanda kilidi tutmak için bazı görevler ve kilidi serbest başka bir görev için beklemeniz gerekir.  
  
 [!code-cpp[concrt-cooperative-semaphore#6](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_6.cpp)]  
  
 Bu örnekte aşağıdaki örnek çıkışı üretir.  
  
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
  
 Hakkında daha fazla bilgi için `concurrent_queue` sınıfı için bkz: [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md). Hakkında daha fazla bilgi için `parallel_for` algoritması bkz [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `cooperative-semaphore.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc işbirlikçi-semaphore.cpp**  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Kullanabilirsiniz *kaynak edinme olan başlatma* (RAII) deseni erişimi sınırlamak için bir `semaphore` belirli bir kapsam nesnesi. RAII deseni altında bir veri yapısı yığında ayrılmış. Bu veri yapısını başlatır veya bir kaynak oluşturulur ve bozar veya veri yapısı kaldırıldığı zaman, kaynak serbest zaman alır. RAII deseni çevreleyen kapsamdaki çıkar önce yıkıcı adlandırılır güvence altına alır. Bu nedenle, kaynak doğru bir özel durum oluştuğunda veya birden çok işlev içerdiğinde, yönetilen `return` deyimleri.  
  
 Aşağıdaki örnek adlı bir sınıf tanımlar `scoped_lock`, içinde tanımlanan `public` bölümünü `semaphore` sınıfı. `scoped_lock` Sınıfı benzer [concurrency::critical_section::scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) ve [concurrency::reader_writer_lock::scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) sınıfları. Oluşturucusunun `semaphore::scoped_lock` sınıfı edinir erişim verilen `semaphore` nesne ve yıkıcısı bu nesneye erişimi serbest bırakır.  
  
 [!code-cpp[concrt-cooperative-semaphore#7](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_7.cpp)]    
 Aşağıdaki örnek geçirilir iş işlevinin gövdesini değiştirir `parallel_for` işlevi döndürmeden önce semafor yayımlanır emin olmak için onun RAII kullanan algoritması. Bu teknik iş işlev özel durum güvenli olmasını sağlar.  
  
 [!code-cpp[concrt-cooperative-semaphore#8](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_8.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlamları](../../parallel/concrt/contexts.md)   
 [Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)


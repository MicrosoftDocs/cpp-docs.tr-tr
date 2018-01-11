---
title: "İzlenecek yol: Vadeli işlemleri uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- implementing futures [Concurrency Runtime]
- futures, implementing [Concurrency Runtime]
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 119969860f031acbc2f1764a34a456d2e8a16437
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-implementing-futures"></a>İzlenecek yol: Vadeli İşlemleri Uygulama
Bu konu, uygulamanızı vadeli uygulamak gösterilmiştir. Konusunda daha fazla yapan varolan işlevsellikte eşzamanlılık çalışma zamanı bir şey halinde birleştirmek gösterilmiştir.  
  
> [!IMPORTANT]
>  Bu konu, tanıtım amacıyla vadeli kavramı gösterilmektedir. Kullanmanızı öneririz [std::future](../../standard-library/future-class.md) veya [concurrency::task](../../parallel/concrt/reference/task-class.md) gerektiren zaman zaman uyumsuz bir görevi daha sonra kullanmak için bir değer hesaplar.  
  
 A *görev* ek, daha ayrıntılı hesaplamalar ayrılmış bir hesaplama değil. A *gelecekteki* daha sonra kullanmak için bir değer hesaplar zaman uyumsuz bir görevdir.  
  
 Vadeli uygulamak için bu konuda tanımlar `async_future` sınıfı. `async_future` Sınıfı, bu bileşenlerin eşzamanlılık çalışma zamanı kullanır: [concurrency::task_group](reference/task-group-class.md) sınıfı ve [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) sınıfı. `async_future` Sınıfını kullanan `task_group` zaman uyumsuz olarak bir değeri hesaplamak için sınıf ve `single_assignment` hesaplamanın sonucu depolamak için sınıf. Oluşturucusunun `async_future` sınıfı sonuç hesaplar bir iş işlevi alır ve `get` yöntemi sonucu alır.  
  
### <a name="to-implement-the-asyncfuture-class"></a>Async_future sınıfı uygulamak için  
  
1.  Adlı bir şablon sınıfı bildirme `async_future` elde edilen hesaplama türüne parametreli. Ekleme `public` ve `private` bu sınıfa bölümler.  
  
 [!code-cpp[concrt-futures#2](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_1.cpp)]  
  
2.  İçinde `private` bölümünü `async_future` sınıfı, bildirme bir `task_group` ve `single_assignment` veri üyesi.  
  
 [!code-cpp[concrt-futures#3](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_2.cpp)]  
  

3.  İçinde `public` bölümünü `async_future` sınıfı, Oluşturucusu uygulayın. Oluşturucu sonuç hesaplar iş işlevi parametreli bir şablondur. İş işlevinde Oluşturucusu zaman uyumsuz olarak yürütür `task_group` veri üyesi ve kullandığı [concurrency::send](reference/concurrency-namespace-functions.md#send) sonucu yazmak için işlevini `single_assignment` veri üyesi.  
  
 [!code-cpp[concrt-futures#4](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_3.cpp)]  
  
4.  İçinde `public` bölümünü `async_future` sınıfı, yıkıcı uygulayın. Yok Edicisi görevin tamamlanmasını bekler.  
  
 [!code-cpp[concrt-futures#5](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_4.cpp)]  
  

5.  İçinde `public` bölümünü `async_future` sınıfı, uygulama `get` yöntemi. Bu yöntem [concurrency::receive](reference/concurrency-namespace-functions.md#receive) iş işlevin sonucu almak için işlevi.  

  
 [!code-cpp[concrt-futures#6](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_5.cpp)]  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek eksiksiz gösterir `async_future` sınıfı ve kullanım örneği. `wmain` İşlev oluşturur bir std::[vektör](../../standard-library/vector-class.md) 10.000 rastgele tamsayı değerleri içeren nesne. Daha sonra kullanır `async_future` bulunan en küçük ve en büyük değerleri bulmaya nesneleri `vector` nesnesi.  
  
### <a name="code"></a>Kod  
 [!code-cpp[concrt-futures#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_6.cpp)]  
  
### <a name="comments"></a>Açıklamalar  
 Bu örnek şu çıkışı üretir:  
  
```Output  
smallest: 0  
largest:  9999  
average:  4981  
```  
  
 Örnek kullanır `async_future::get` hesaplama sonuçlarını alma yöntemi. `async_future::get` Yöntemi hesaplama Hesaplama etkin durumdaysa tamamlanmasını bekler.  
  
## <a name="robust-programming"></a>Güçlü Programlama  


 Genişletmek için `async_future` iş işlevi tarafından oluşturulan özel durumları işleme, değiştirmek için sınıf `async_future::get` çağrılacak yöntem [concurrency::task_group::wait](reference/task-group-class.md#wait) yöntemi. `task_group::wait` Yöntemi iş işlevi tarafından oluşturulan özel durumları oluşturur.  


  
 Aşağıdaki örnek, değiştirilmiş sürümünü gösterir `async_future` sınıfı. `wmain` İşlev kullanan bir `try` - `catch` sonucunu yazdırmak için blok `async_future` nesne veya iş işlevi tarafından oluşturulan özel durum değeri yazdırmak için.  
  
 [!code-cpp[concrt-futures-with-eh#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_7.cpp)]  
  
 Bu örnek şu çıkışı üretir:  
  
```Output  
caught exception: error  
```  
  
 Eşzamanlılık Çalışma zamanı özel durum işleme modeli hakkında daha fazla bilgi için bkz: [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `futures.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc futures.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma zamanı izlenecek yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [task_group sınıfı](reference/task-group-class.md)   
 [single_assignment Sınıfı](../../parallel/concrt/reference/single-assignment-class.md)

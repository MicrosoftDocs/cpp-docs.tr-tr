---
title: "Eşitleme veri yapıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: synchronization data structures
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1dd1c47cad01e0324f8027593eb4933f70cd6191
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="synchronization-data-structures"></a>Eşitleme Veri Yapıları
Eşzamanlılık Çalışma zamanı birden çok iş parçacığı tarafından paylaşılan verilere erişim eşitlemenize olanak birkaç veri yapılarını sağlar. Bu veri yapıları seyrek değiştirmek veri paylaşılan olduğunda yararlıdır. Eşitleme nesnesi, örneğin, önemli bir bölümü, paylaşılan kaynağı kullanılabilir hale gelene kadar beklenecek başka bir iş parçacığı neden olur. Bu nedenle, sık kullanılan veri erişimi eşitlemek için böyle bir nesnenin kullanırsanız, uygulamanızda ölçeklenebilirlik kaybedebilir. [Paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) sağlar [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) çeşitli iş parçacıkları ve eşitleme gerek kalmadan görevler arasında kaynak paylaşımı sağlayan sınıf. Hakkında daha fazla bilgi için `combinable` sınıfı için bkz: [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).  
  
##  <a name="top"></a>Bölümler  
 Bu konuda aşağıdaki zaman uyumsuz ileti bloğu türleri ayrıntılı açıklanmıştır:  
  
-   [critical_section](#critical_section)  
  
-   [reader_writer_lock](#reader_writer_lock)  
  
-   [scoped_lock ve scoped_lock_read](#scoped_lock)  
  
-   [event](#event)  
  
##  <a name="critical_section"></a>critical_section  
 [Concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) sınıfı, bunları preempting yerine diğer görevlere verir işbirlikçi karşılıklı dışlama nesneyi temsil eder. Kritik bölümler, birden çok iş parçacığı özel okuma ve yazma erişimi Paylaşılan verilere gerektiğinde faydalıdır.  

 `critical_section` Yeniden girme olmayan bir sınıftır. [Concurrency::critical_section::lock](reference/critical-section-class.md#lock) yöntemi türünde bir özel durum atar [concurrency::improper_lock](../../parallel/concrt/reference/improper-lock-class.md) kilidi zaten sahip iş parçacığı tarafından çağrıldıklarında.  


  
### <a name="methods-and-features"></a>Yöntemleri ve özellikleri  
 Aşağıdaki tabloda tarafından tanımlanan önemli yöntemleri gösterir `critical_section` sınıfı.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[lock](reference/critical-section-class.md#lock)|Kritik bölüm edinir. Kilit alır kadar çağıran bağlamını engeller.|  
|[try_lock](reference/critical-section-class.md#try_lock)|Kritik bölüm almaya çalışır, ancak değil engeller.|  
|[kilidini aç](reference/critical-section-class.md#unlock)|Kritik bölüm serbest bırakır.|  
  
 [[Üst](#top)]  
  
##  <a name="reader_writer_lock"></a>reader_writer_lock  
 [Concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) sınıfı, iş parçacığı okuma/yazma işlemleri Paylaşılan verilere sağlar. Birden çok iş parçacığı bir paylaşılan kaynağa eşzamanlı okuma erişimi gerektiren ama bu paylaşılan kaynağa nadiren yazma Okuyucu/Yazıcı kilitleri kullanın. Bu sınıf, herhangi bir zamanda bir nesneye yalnızca bir iş parçacığı yazma erişim sağlar.  
  
 `reader_writer_lock` Sınıfı gerçekleştirebilir daha iyi `critical_section` çünkü sınıf bir `critical_section` nesne eşzamanlı okuma erişimi engelleyen bir paylaşılan kaynağa özel erişim edinir.  
  
 Gibi `critical_section` sınıfı, `reader_writer_lock` sınıfı, bunları preempting yerine diğer görevlere verir işbirlikçi karşılıklı dışlama nesneyi temsil eder.  
  
 Paylaşılan kaynağa yazmalısınız bir iş parçacığı bir Okuyucu/Yazıcı kilit alır, yazıcı kilidi serbest kadar kaynak da erişmesi gereken başka bir iş parçacığı engellenir. `reader_writer_lock` Sınıf örneği, bir *yazma tercih* bekleme okuyucular engelini kaldırır önce bekleme yazıcılarının engelini kaldırır kilit kilidinin.  
  
 Gibi `critical_section` sınıfı, `reader_writer_lock` yeniden girme olmayan bir sınıftır. [Concurrency::reader_writer_lock::lock](reference/reader-writer-lock-class.md#lock) ve [concurrency::reader_writer_lock::lock_read](reference/reader-writer-lock-class.md#lock_read) yöntemleri throw türünde bir özel durum `improper_lock` zaten sahip olan bir iş parçacığı tarafından çağrıldıklarında Kilit.  


  
> [!NOTE]
>  Çünkü `reader_writer_lock` sınıfı yeniden girme olmayan, salt okunur kilit Okuyucu/Yazıcı kilit yükseltme veya bir salt okunur kilidi Okuyucu/Yazıcı kilit düşürmek. Bu işlemlerin gerçekleştirme belirtilmeyen davranışı üretir.  
  
### <a name="methods-and-features"></a>Yöntemleri ve özellikleri  
 Aşağıdaki tabloda tarafından tanımlanan önemli yöntemleri gösterir `reader_writer_lock` sınıfı.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[lock](reference/reader-writer-lock-class.md#lock)|Okuma/yazma erişimi kilidi edinir.|  
|[try_lock](reference/reader-writer-lock-class.md#try_lock)|Okuma/yazma erişimi kilidi almaya çalışır, ancak değil engeller.|  
|[lock_read](reference/reader-writer-lock-class.md#lock_read)|Salt okunur erişim kilidi edinir.|  
|[try_lock_read](reference/reader-writer-lock-class.md#try_lock_read)|Kilit salt okunur erişim kazanmak çalışır, ancak değil engeller.|  
|[kilidini aç](reference/reader-writer-lock-class.md#unlock)|Kilidi serbest bırakır.|  
  
 [[Üst](#top)]  
  
##  <a name="scoped_lock"></a>scoped_lock ve scoped_lock_read  
 `critical_section` Ve `reader_writer_lock` sınıfları karşılıklı dışlama nesneleriyle çalışma biçimini basitleştirmek iç içe geçmiş yardımcı sınıfları sağlar. Bu yardımcı sınıfları olarak da bilinir *kilitleri kapsamlı*.  
  
 `critical_section` Sınıfı içeren [concurrency::critical_section::scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) sınıfı. Sağlanan erişim Oluşturucusu edinir `critical_section` nesne; söz konusu nesne yıkıcı sürümleri erişimi. `reader_writer_lock` Sınıfı içeren [concurrency::reader_writer_lock::scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) benzer sınıfı `critical_section::scoped_lock`, sağlanan yazma erişimini yönetir ancak bu `reader_writer_lock` nesnesi. `reader_writer_lock` Sınıfı ayrıca içerir [concurrency::reader_writer_lock::scoped_lock_read](reference/reader-writer-lock-class.md#scoped_lock_read_class) sınıfı. Bu sınıf sağlanan okuma erişimi yöneten `reader_writer_lock` nesnesi.  

  
 Kapsamlı kilitleri sağlayan birkaç avantaj ile çalışırken `critical_section` ve `reader_writer_lock` el ile nesneleri. Genellikle, kapsamlı bir kilit yığında ayırın. Bunu bozulduğunda kapsamlı bir kilidi karşılıklı dışlama nesneye erişimi otomatik olarak açar; Bu nedenle, el ile temel alınan nesnenin kilidini açma değil. Birden çok işlevi içeriyor gerektiğinde bu faydalıdır `return` deyimleri. Kapsamlı kilitleri de uyumlu özel kod yazmanıza yardımcı olabilir. Zaman bir `throw` deyimi neden bırakma için yığın, tüm etkin kapsamlı LOCK yok Edicisi adı verilir ve bu nedenle karşılıklı dışlama nesne her zaman doğru serbest.  
  
> [!NOTE]
>  Kullandığınızda `critical_section::scoped_lock`, `reader_writer_lock::scoped_lock`, ve `reader_writer_lock::scoped_lock_read` sınıfları değil el ile serbest karşılıklı dışlama nesnesini erişimi. Bu, çalışma zamanı'ı geçersiz bir durumda koyabilirsiniz.  
  
##  <a name="event"></a>Olay  
 [Concurrency::event](../../parallel/concrt/reference/event-class.md) sınıfı durumu sinyal ya da işareti olmayan bir eşitleme nesnesi temsil eder. Paylaşılan verilere erişimi korumanın amacı olan, kritik bölümler gibi eşitleme nesneleri aksine akışını olayları eşitleyin.  
  
 `event` Sınıfı, başka bir görev için iş bir görev tamamlandığında yararlıdır. Örneğin, bir görev, verileri bir ağ bağlantısı veya bir dosyadan okuma izni olduğunu başka bir görev sinyal.  
  
### <a name="methods-and-features"></a>Yöntemleri ve özellikleri  
 Aşağıdaki tabloda birkaç tarafından tanımlanan önemli yöntemleri gösterilmektedir `event` sınıfı.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[bekleme](reference/event-class.md#wait)|Olay işaret hale bekler.|  
|[set](reference/event-class.md#set)|Olay iş durumuna ayarlar.|  
|[Sıfırla](reference/event-class.md#reset)|Olay işaret olmayan durumuna ayarlar.|  
|[wait_for_multiple](reference/event-class.md#wait_for_multiple)|Birden çok olay işaret hale bekler.|  

  
### <a name="example"></a>Örnek  
 Nasıl kullanılacağını gösteren bir örnek için `event` sınıfı için bkz: [eşitleme veri yapılarını Windows API karşılaştırma](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).  
  
 [[Üst](#top)]  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Eşitleme Veri Yapılarını Windows API ile Karşılaştırma](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)  
 Eşitleme veri yapılarını Windows API tarafından sağlanan davranışını karşılaştırır.  
  
 [Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)  
 Paralel Programlama basitleştiren ve ilgili konulara bağlantılar içerir eşzamanlılık çalışma, açıklar.


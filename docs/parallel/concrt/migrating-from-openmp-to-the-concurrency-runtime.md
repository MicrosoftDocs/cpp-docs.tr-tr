---
title: "OpenMP öğesinden eşzamanlılık çalışma zamanına geçiş | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Concurrency Runtime, migrating from OpenMP
- OpenMP, migrating to the Concurrency Runtime
ms.assetid: 9bab7bb1-e45d-44b2-8509-3b226be2c93b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 65359e76e036a0d8d33de2de9f6c96c6425d2152
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="migrating-from-openmp-to-the-concurrency-runtime"></a>OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş
Eşzamanlılık Çalışma zamanı çeşitli programlama modeli sağlar. Bu modeller çakışıyor olabilir veya diğer kitaplıkları modellerinin tamamlar. Bu belgeler bölümü karşılaştırma [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp) eşzamanlılık çalışma zamanı ve Eşzamanlılık Çalışma zamanı kullanmak için mevcut OpenMP kod geçirme hakkında örnekler sağlar.  
  
 OpenMP programlama modeli açık bir standart tarafından tanımlanır ve Fortran ve C/C++ programlama dilleri için iyi tanımlanmış bağlamalar belirtildi. OpenMP sürümleri 2.0 ve Visual C++ derleyicisi tarafından desteklenir, 2.5 yinelemeli paralel algoritmalar için uymaktadır; diğer bir deyişle, bunlar paralel yineleme bir veri dizisi üzerinde gerçekleştirin. OpenMP 3.0 yinelemeli görevlerinin yanı sıra yinelemeli olmayan görevlerini destekler.  
  
 Paralellik derecesini önceden belirlenir ve sistemin kullanılabilir kaynakları eşleştiğinde OpenMP en etkili yoldur. OpenMP yüksek performanslı bilgi işlem, özellikle iyi bir eşleşme çok büyük hesaplama sorunları bir bilgisayarda işlem kaynakları arasında dağıtıldığı modelidir. Bu senaryoda, donanım ortamı genellikle sabittir ve geliştirici algoritma çalıştırıldığında tüm bilgi işlem kaynaklarına özel erişim sağlamak makul biçimde bekleyebilirsiniz.  
  
 Ancak, daha az kısıtlanmış bilgi işlem ortamlarını OpenMP için iyi bir eşleşme olmayabilir. Örneğin, özyinelemeli sorunları (örneğin, quicksort algoritması veya veri ağacının arama) OpenMP 2.0 ve 2.5 kullanarak uygulama daha zordur. Eşzamanlılık Çalışma zamanı sağlayarak OpenMP yeteneklerini tamamlar [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) ve [paralel Desen kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL). Zaman uyumsuz aracılar kitaplığı parçalı görev paralelliği destekler; PPL'de daha fazla hassas Paralel Görevler destekler. Eşzamanlılık Çalışma zamanı uygulamanızı mantığa göre odaklanabilmeniz paralel işlemleri gerçekleştirmek için gerekli altyapıyı sağlar. Eşzamanlılık Çalışma zamanı programlama modelleri çeşitli sağladığından, ancak kendi ek yükü zamanlama diğer eşzamanlılık kitaplıkları OpenMP gibi daha büyük olabilir. Bu nedenle, eşzamanlılık çalışma zamanı kullanmak için mevcut OpenMP kodunuzu dönüştürürken performans artımlı olarak sınamanızı öneririz.  
  
## <a name="when-to-migrate-from-openmp-to-the-concurrency-runtime"></a>OpenMP öğesinden eşzamanlılık çalışma zamanına geçiş zamanı  
 Eşzamanlılık Çalışma zamanı aşağıdaki durumlarda kullanmak için mevcut OpenMP kod geçirmek için yararlı olabilir.  
  
|Durumları|Eşzamanlılık Çalışma zamanı avantajları|  
|-----------|-------------------------------------------|  
|Genişletilebilir bir eş zamanlı programlama altyapısı gerektirir.|Eşzamanlılık Çalışma zamanı yer alan özelliklerin çoğunu genişletilebilir. Ayrıca, yeni bir tane oluşturmak için var olan özellikleri birleştirebilirsiniz. OpenMP derleyici yönergeleri kullandığından, kolayca genişletilemez.|  
|Uygulamanızı işbirlikçi Engellemesi yararlı.|Bir görev henüz kullanılabilir olmayan bir kaynak gerektirdiğinden engellediğinde, kaynak için ilk görev beklediği sırada eşzamanlılık çalışma zamanı diğer görevleri gerçekleştirebilirsiniz.|  
|Uygulamanız, dinamik yük dengeleme yararlı.|Eşzamanlılık Çalışma zamanı iş yüklerini değiştirme gibi bilgi işlem kaynakları, ayırma ayarlayan bir zamanlama algoritması kullanır. Paralel bir bölgeye bilgi işlem kaynakları Zamanlayıcısı ayırdığında OpenMP, bu kaynak ayırma hesaplama düzeltilmiştir.|  
|Özel durum işleme desteği gerektirir.|PPL'de hem içinde hem de bir paralel bölge veya döngü dışında özel durumlarını yakalama olanak sağlar. OpenMP, döngü ve paralel bölge içinde özel durum işlemesi gerekir.|  
|İptal mekanizması gerektirir.|PPL'de tek tek görevler ve paralel iş ağaçları iptal etmek uygulamaları etkinleştirir. OpenMP kendi iptal mekanizması uygulamak için uygulama gerektirir.|  
|Başladığı farklı bir bağlamda tamamlamak için paralel kod gerektirir.|Eşzamanlılık Çalışma zamanı, bir görev bir bağlamında başlatın ve sonra bekleyin veya başka bir bağlamda görev iptal olanak tanır. OpenMP, tüm paralel iş başladığı bağlamda bitmesi gerekir.|  
|Gelişmiş hata ayıklama desteği gerektirir.|Visual Studio sağlar **Paralel Yığınlar** ve **Paralel Görevler** windows böylece birden çok iş parçacıklı uygulamalar daha kolay ayıklayabilirsiniz.<br /><br /> Eşzamanlılık Çalışma zamanı için destek hata ayıklama hakkında daha fazla bilgi için bkz: [görevleri penceresini kullanma](/visualstudio/debugger/using-the-tasks-window), [Paralel Yığınlar penceresini kullanarak](/visualstudio/debugger/using-the-parallel-stacks-window), ve [izlenecek yol: paralel hata ayıklama Uygulama](/visualstudio/debugger/walkthrough-debugging-a-parallel-application).|  
  
## <a name="when-not-to-migrate-from-openmp-to-the-concurrency-runtime"></a>OpenMP öğesinden eşzamanlılık çalışma zamanına geçirmek istemiyorsanız ne zaman  
 Eşzamanlılık Çalışma zamanı kullanmak için mevcut OpenMP kod geçirmek uygun olmayabilir aşağıdaki durumlarda açıklanmaktadır.  
  
|Durumları|Açıklama|  
|-----------|-----------------|  
|Uygulama zaten gereksinimlerinize uygun.|Uygulama performansı ve geçerli hata ayıklama desteği memnun kaldığınızda, geçiş uygun olmayabilir.|  
|Paralel döngü gövdelerini az şey gerçekleştirin.|Eşzamanlılık Çalışma zamanı Görev Zamanlayıcısı'nı yükü özellikle döngü gövdesine nispeten küçük olduğunda döngü gövdesine paralel olarak yürütülen avantajlarını üstesinden değil.|  
|Uygulamanız, c dilinde yazılır|Eşzamanlılık Çalışma zamanı C++ özelliklerinin kullandığından, tam olarak kullanmak için C uygulamayı sağlayan kodu yazılamıyor olduğunda, uygun olmayabilir.|  
  
## <a name="related-topics"></a>İlgili Konular  
 [Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak üzere Döngü için bir OpenMP paralelini Dönüştürme](../../parallel/concrt/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime.md)  

 OpenMP kullanan temel bir döngü verilen [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) ve [için](../../parallel/openmp/reference/for-openmp.md) yönergeleri, eşzamanlılık çalışma zamanı kullanmak üzere dönüştürülmesi gösterilmektedir [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritma.  

  
 [Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için İptali Kullanan bir OpenMP Döngüsünü Dönüştürme](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)  
 Bir OpenMP verilen [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[için](../../parallel/openmp/reference/for-openmp.md) çalıştırmak için tüm yinelemeleri gerektirmez döngü eşzamanlılık çalışma zamanı iptal mekanizması kullanacak şekilde dönüştürmek nasıl gösterir.  
  
 [Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için Özel Durum İşleme Kullanan bir OpenMP Döngüsünü Dönüştürme](../../parallel/concrt/convert-an-openmp-loop-that uses-exception-handling.md)  
 Bir OpenMP verilen [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[için](../../parallel/openmp/reference/for-openmp.md) özel durum işleme gerçekleştirir döngü eşzamanlılık çalışma zamanı özel durum mekanizması işleme kullanacak şekilde dönüştürmek nasıl gösterir.  
  
 [Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için Azaltma Değişkeni Kullanan bir OpenMP Döngüsünü Dönüştürme](../../parallel/concrt/convert-an-openmp-loop-that-uses-a-reduction-variable.md)  
 Bir OpenMP verilen [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[için](../../parallel/openmp/reference/for-openmp.md) kullanan döngüsünü [azaltma](../../parallel/openmp/reference/reduction.md) yan tümcesi, eşzamanlılık çalışma zamanı kullanmak için dönüştürmenin nasıl yapılacağı gösterilmektedir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma zamanı](../../parallel/concrt/concurrency-runtime.md)   
 [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp)   
 [Paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)


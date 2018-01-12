---
title: "Eşzamanlılık Çalışma zamanı diğer eşzamanlılık modelleriyle karşılaştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Concurrency Runtime, compared to other models
ms.assetid: d8b9a1f4-f15f-43c3-a5b4-c0991edf9c86
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e20523eb8a2c78cfa72b6c3084e9ca9f620a916c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comparing-the-concurrency-runtime-to-other-concurrency-models"></a>Eşzamanlılık Çalışma Zamanını Diğer Eşzamanlılık Modelleriyle Karşılaştırma
Bu belge özellikleri ve Eşzamanlılık Çalışma zamanı ve diğer teknolojiler programlama modelleri arasındaki farklar açıklanmaktadır. Eşzamanlılık Çalışma zamanı yararları diğer programlama modelleri yararları nasıl karşılaştırmak anlayarak, uygulamalarınızın gereksinimlerini en iyi karşılayan teknolojisi seçebilirsiniz.  
  
 Windows iş parçacığı havuzu veya OpenMP, gibi başka bir programlama modeli şu anda kullanıyorsanız, burada, eşzamanlılık çalışma zamanına geçiş uygun olabilir durumlar vardır. Örneğin, konu [OpenMP öğesinden eşzamanlılık çalışma zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md) ne zaman bu OpenMP öğesinden eşzamanlılık çalışma zamanına geçiş uygun olabilir açıklar. Ancak, uygulama performansı ve geçerli hata ayıklama desteği memnun kaldığınızda, geçiş gerekli değildir.  
  
 Başka bir eşzamanlılık modelini kullanan mevcut uygulamanızda tamamlamak için eşzamanlılık çalışma zamanı verimliliği avantajları ve özelliklerini kullanabilirsiniz. Eşzamanlılık Çalışma zamanı, birden çok görev zamanlayıcılar aynı bilgi işlem kaynakları için rekabet ettiği Yük Dengeleme garanti edemez. Ancak, iş yüklerini çakışmaması olduğunda bu etkiyi en az olur.  
  
##  <a name="top"></a>Bölümler  
  
-   [İşbirlikçi planlama için PreEmptive tarafından planlama karşılaştırma](#models)  
  
-   [Eşzamanlılık Çalışma zamanı Windows API karşılaştırma](#winapi)  
  
-   [Eşzamanlılık çalışma zamanına OpenMP karşılaştırma](#openmp)  
  
##  <a name="models"></a>İşbirlikçi planlama için PreEmptive tarafından planlama karşılaştırma  
 PreEmptive tarafından modeli ve modelleri zamanlama işbirlikçi bilgi işlem kaynakları paylaşmak birden çok görev etkinleştirmek için iki ortak işlemciler veya donanım iş parçacıkları yöntemleridir.  
  
### <a name="preemptive-and-cooperative-scheduling"></a>PreEmptive tarafından ve işbirlikçi zamanlama  
 *PreEmptive tarafından zamanlama* belirli bir süre için bir bilgisayar kaynağına her görev özel erişim verir ve başka bir görev geçer hepsini ve öncelik tabanlı bir mekanizma. PreEmptive tarafından zamanlama çoklu işletim sistemlerinde Windows gibi ortak*. İşbirlikçi zamanlama* görevi tamamlanana kadar veya görev kendi kaynağa erişim izni verir kadar bir bilgisayar kaynağına her görev özel erişim sağlayan bir mekanizmadır. Eşzamanlılık Çalışma zamanı, kaynakları işleme en fazla kullanım elde etmek için işletim sistemi PreEmptive tarafından Zamanlayıcı ile birlikte işbirlikçi zamanlama kullanır.  
  
### <a name="differences-between-preemptive-and-cooperative-schedulers"></a>PreEmptive tarafından ve işbirlikçi zamanlayıcılar arasındaki farklar  
 Her iş parçacığı ilerleme yapar emin olmak için kaynak bilgisayar için birden çok iş parçacığı eşit erişmesini sağlamak PreEmptive tarafından zamanlayıcılar arama. Çok sayıda bilgi işlem kaynaklarına sahip bilgisayarlarda, Orta erişim sağlayarak daha az sorunlu olur; Ancak, kaynakların verimli kullanımı sağlayarak daha sorunlu olur.  
  
 PreEmptive tarafından çekirdek modu Zamanlayıcı planlama kararları almak için işletim sisteminde yararlanmayı uygulama kodu gerektirir. Buna karşılık, bir kullanıcı modu işbirlikçi Zamanlayıcı kendi planlama kararları almak uygulama kodu sağlar. İşbirlikçi zamanlama uygulama tarafından yapılması birçok zamanlama kararlarını sağladığından, çok çekirdek modu eşitlemede ilişkili ek yükünü azaltır. Zamanlamak için diğer iş olduğunda işbirlikçi Zamanlayıcı genellikle işletim sistemi çekirdeğe zamanlama kararlarını erteler. İşbirlikçi Zamanlayıcı işletim sistemi zamanlayıcı çekirdeğe iletilen engelleyici bir işlem yoktur ancak işlemi kullanıcı modu Zamanlayıcı iletilen değil de erteler.  
  
### <a name="cooperative-scheduling-and-efficiency"></a>İşbirlikçi zamanlama ve verimliliği  
 PreEmptive tarafından bir zamanlayıcı için aynı öncelik düzeyine sahip tüm iş eşittir. PreEmptive tarafından Zamanlayıcı iş parçacığı içinde oluşturuldukları sırada genellikle zamanlar. Ayrıca, bir PreEmptive tarafından Zamanlayıcı iş parçacığı önceliği temelinde hepsini şekilde, bir zaman dilimi her iş parçacığı sağlar. Bu mekanizma (her iş parçacığı ilerleme yapmaz) eşitliği sağlasa da, bazı verimliliği maliyetlerine gelir. Örneğin, birçok hesaplama yoğunluklu algoritması eşitliği gerektirmez. Bunun yerine, ilgili görevleri az genel zamanında son önemlidir. İşbirlikçi zamanlama daha verimli bir şekilde çalışması zamanlamak bir uygulama sağlar. Örneğin, birçok iş parçacığı sayısı olan bir uygulama göz önünde bulundurun. Aynı anda çalışmasına kaynakları paylaşmaz iş parçacıklarını zamanlama eşitleme yükünü azaltmak ve böylelikle verimliliği artırabilirsiniz. Böylece her ardışık düzen aşaması girişi zaten bellek önbelleğine yüklendiğinden görevleri zamanlamak için başka bir işlem hatları görevlerin (burada her görev öncekinin Çıkışta davranır) çalıştırmak için aynı işlemci etkilidir.  
  
### <a name="using-preemptive-and-cooperative-scheduling-together"></a>PreEmptive tarafından ve işbirlikçi birlikte zamanlama kullanma  
 İşbirlikçi zamanlama, tüm zamanlama sorunları çözmez. Örneğin, diğer görevlere oldukça verim olmayan görevler tüm kullanılabilir bilgi işlem kaynaklarını tüketebilir ve diğer görevleri ilerleme yapmasını önlemek. Eşzamanlılık Çalışma zamanı verimliliği avantajlarını işbirlikçi zamanlama PreEmptive tarafından zamanlama eşitliği garanti tamamlamak üzere kullanır. Varsayılan olarak, bilgi işlem kaynaklarına arasında iş verimli bir şekilde dağıtmak için bir iş çalarak algoritmasını kullanan işbirlikçi Zamanlayıcısı'nı eşzamanlılık çalışma zamanı sağlar. Ancak, eşzamanlılık çalışma zamanı Zamanlayıcı'yı da oldukça kaynakları uygulamalar arasında dağıtmak için işletim sisteminin PreEmptive tarafından Zamanlayıcı kullanır. İş parçacığı üzerinde ayrıntılı denetim üretmek için uygulamalarınızda özel zamanlayıcılar ve Zamanlayıcı ilkeleri de oluşturabilirsiniz.  
  
 [[Üst](#top)]  
  
##  <a name="winapi"></a>Eşzamanlılık Çalışma zamanı Windows API karşılaştırma  
 Genellikle Windows API adlandırılır (ve önceden Win32 biliniyordu), Microsoft Windows uygulama programlama arabirimi, uygulamalarınızda eşzamanlılık sağlayan bir programlama modelidir. Eşzamanlılık Çalışma zamanı temel işletim sistemi bulunmayan ek programlama modelleri sağlamak için Windows API inşa edilmiştir.  
  
 Eşzamanlılık Çalışma Zamanı paralel iş gerçekleştirmek için Windows API iş parçacığı modeli oluşturur. Ayrıca Windows API bellek yönetimi ve iş parçacığı yerel depolama mekanizmaları kullanır. Windows 7 ve Windows Server 2008 R2 üzerinde kullanıcı zamanlanabilir iş parçacıkları ve 64'ten fazla donanım iş parçacığı olan bilgisayarlar için Windows API desteği kullanır. Eşzamanlılık Çalışma zamanı Windows API modelini işbirlikçi Görev Zamanlayıcısı ve bir iş çalarak algoritması bilgi işlem kaynaklarının kullanımını en üst düzeye çıkarmak için sağlayarak ve birden çok eşzamanlı Zamanlayıcı örnekleri sağlayarak genişletir.  
   
### <a name="programming-languages"></a>Programlama dilleri  
 Windows API C programlama dili programlama modeli kullanıma sunmak için kullanır. Eşzamanlılık Çalışma zamanı C++ dilinde yeni özelliklerinden yararlanır bir C++ programlama arabirimi sağlar. Örneğin, lambda işlevleri paralel iş işlevleri tanımlamak için kısa, tür kullanımı uyumlu bir mekanizma sağlar. Eşzamanlılık Çalışma zamanı kullanan yeni C++ özellikleri hakkında daha fazla bilgi için bkz: [genel bakış](../../parallel/concrt/asynchronous-message-blocks.md).  
  
### <a name="threads-and-thread-pools"></a>İş parçacıkları ve iş parçacığı havuzları  
 İş parçacığı Windows API içinde merkezi eşzamanlılık mekanizmadır. Tipik olarak kullandığınız [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) işlevi iş parçacığı oluşturabilir. İş parçacığı oluşturma ve kullanma görece kolay olsa da, işletim sistemi önemli miktarda süre ve bunları yönetmek için diğer kaynakları ayırır. Her iş parçacığı aynı öncelik düzeyindeki başka bir iş parçacığı olarak aynı yürütme süresi almak için garanti rağmen Ayrıca, ilişkili ek yükü yeterli büyüklükte görevler oluşturma gerektirir. Küçük veya daha ayrıntılı görevler için eşzamanlılık ile ilişkili ek yükü paralel olarak çalışan görevlerin yararı daha ağır basar.  
  
 İş parçacığı havuzu iş parçacığı Yönetim maliyetini azaltmak için bir yoludur. Özel iş parçacığı havuzları ve her ikisi de verimli bir şekilde paralel olarak çalıştırmak küçük iş öğeleri etkinleştirmek Windows API'si tarafından sağlanan iş parçacığı havuzu uygulama. Windows iş parçacığı havuzu iş öğeleri ilk çıkar (FIFO) sıradaki tutar. Her iş öğesi havuza eklenen sırayla başlatılır.  
  
 Eşzamanlılık Çalışma zamanı mekanizması zamanlama FIFO genişletmek için bir iş çalarak algoritması uygular. Algoritma henüz başlatılmamış görevleri iş öğeleri dışında çalışan iş parçacıklarını taşır. İş çalarak algoritması iş yükleri dengeleyebilirsiniz rağmen aynı zamanda edilmemesi için iş öğeleri neden olabilir. Bu sipariş işlem zaman gönderildiği olandan farklı bir sırada başlatmak bir iş öğesi neden olabilir. Bu özyinelemeli algoritmalarıyla yararlıdır daha iyi olduğu fırsat veri daha yeni görevler eskiler arasında arasında paylaşılır. İlk çalıştırmak için yeni öğeleri alınıyor, daha az İsabetsiz Önbellek okuma sayısı ve büyük olasılıkla daha az sayfa hataları anlamına gelir.  
  
 İşletim sistemi açısından bakıldığında, iş çalarak haksız. Bir uygulama bir algoritma ya da paralel olarak çalıştırmak için görev uygular, ancak, alt görevler arasında eşitliği her zaman bir önemi yoktur. Ne önemli nasıl hızlı bir şekilde genel görev tamamlandığında olur. Diğer algoritmalar için FIFO uygun zamanlama stratejidir.  
  
### <a name="behavior-on-various-operating-systems"></a>Çeşitli işletim sistemleri davranış  
 Windows Vista'da yığın performansı geliştirildi dışında Windows XP ve Windows Vista, eşzamanlılık çalışma zamanı kullanan uygulamalar benzer şekilde davranır.  
  
 Windows 7 ve Windows Server 2008 R2 işletim sistemi daha fazla eşzamanlılık ve ölçeklenebilirlik destekler. Örneğin, bu işletim sistemlerinin 64 taneden fazla donanım iş parçacığı olan bilgisayarları destekler. Windows API kullanan mevcut bir uygulamayı, bu yeni özelliklerden yararlanmak için değiştirilmesi gerekir. Ancak, eşzamanlılık çalışma zamanı otomatik olarak kullanan bir uygulamanın bu özellikler kullanır ve değişiklik gerektirmez.  
  
 [Base.user mode_scheduling](http://msdn.microsoft.com/library/windows/desktop/dd627187)  
  
 [[Üst](#top)]  
  
##  <a name="openmp"></a>Eşzamanlılık çalışma zamanına OpenMP karşılaştırma  
 Eşzamanlılık Çalışma zamanı çeşitli programlama modeli sağlar. Bu modeller çakışıyor olabilir veya diğer kitaplıkları modellerinin tamamlar. Bu bölümde eşzamanlılık çalışma zamanına karşılaştırır [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp).  
  
 OpenMP programlama modeli açık bir standart tarafından tanımlanır ve Fortran ve C/C++ programlama dilleri için iyi tanımlanmış bağlamalar belirtildi. OpenMP sürümleri 2.0 ve 2.5 yinelemeli paralel algoritmalar için uymaktadır; diğer bir deyişle, bunlar paralel yineleme bir veri dizisi üzerinde gerçekleştirin. Paralellik derecesini önceden belirlenir ve sistemin kullanılabilir kaynakları eşleştiğinde OpenMP en etkili yoldur. OpenMP yüksek performanslı bilgi işlem, özellikle iyi bir eşleşme çok büyük hesaplama sorunları tek bir bilgisayarın işlem kaynakları arasında dağıtıldığı modelidir. Bu senaryoda, donanım ortamı bilinen ve geliştirici algoritma yürütüldüğünde, bilgi işlem kaynakları için özel erişim sağlamak makul biçimde bekleyebilirsiniz.  
  
 Ancak, diğer, daha az kısıtlanmış bilgi işlem ortamlarını OpenMP için iyi bir eşleşme olmayabilir. Örneğin, özyinelemeli sorunları (örneğin, quicksort algoritması veya veri ağacının arama) OpenMP kullanarak uygulama daha zordur. Eşzamanlılık Çalışma zamanı sağlayarak OpenMP yeteneklerini tamamlar [paralel Desen kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL) ve [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md). OpenMP, kullanılabilir kaynakları uyum ve iş yüklerini değiştirme gibi paralellik derecesini ayarlar dinamik bir zamanlayıcı eşzamanlılık çalışma zamanı sağlar.  
  
 Eşzamanlılık Çalışma zamanı yer alan özelliklerin çoğunu genişletilebilir. Ayrıca, yeni bir tane oluşturmak için var olan özellikleri birleştirebilirsiniz. OpenMP derleyici yönergeleri kullandığından, kolayca genişletilemez.  
  
 Eşzamanlılık Çalışma zamanı karşılaştırır OpenMP ve Eşzamanlılık Çalışma zamanı kullanmak için mevcut OpenMP kod geçirme hakkında daha fazla bilgi için bkz: [OpenMP öğesinden eşzamanlılık çalışma zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md).  
  
 [[Üst](#top)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma zamanı](../../parallel/concrt/concurrency-runtime.md)     
 [Genel bakış](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [Zaman uyumsuz aracılar kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)   
 [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp)

---
title: "Zamana bağlı kodu geliştirme ipuçları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- _lsearch function
- qsort function
- background tasks
- standard sort routines
- clock cycle losses
- code, time-critical
- memory [C++], monitoring usage
- execution, speed improvements
- local heap performance
- optimization [C++], time-critical code
- performance [C++], time-critical code
- threading [C++], performance
- cache [C++], hits and misses
- linear search performance
- page faults
- best practices, time-critical code
- searching [C++], improving performance
- sorting data, improving performance
- threading [C++], best practices
- threading [C++], background tasks
- lists, sorting
- bsearch function
- MFC [C++], performance
- sort routines
- programs [C++], performance
- _lfind function
- heap allocation, time-critical code performance
ms.assetid: 3e95a8cc-6239-48d1-9d6d-feb701eccb54
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5efcf042932163f1e932a55622f7dddd167b8961
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="tips-for-improving-time-critical-code"></a>Zamana Bağlı Kodu Geliştirme İpuçları
Hızlı kod yazma uygulamanız ve sistemi ile nasıl etkileşim kurduğu tüm yönlerini anlaşılması gerekir. Bu konu, kodunuzu zaman açısından kritik bölümlerini başarılı şekilde gerçekleştirdiğinizden emin olun yardımcı olmak için daha belirgin kodlama teknikleri, bazı önerileri sunar.  
  
 Özetlemek gerekirse, zamana bağlı kodu geliştirme gerektiren:  
  
-   Bilmeniz programınızın hangi kısımlarının hızlı olması gerekir.  
  
-   Kodunuzu hızına ve boyutu bilirsiniz.  
  
-   Yeni özellikler maliyetini bilirsiniz.  
  
-   İşi gerçekleştirmek için gereken en düşük iş bilirsiniz.  
  
 Kodunuzu performansına bilgi toplamak için Performans İzleyicisi'ni (perfmon.exe) kullanabilirsiniz.  
  
## <a name="sections-in-this-article"></a>Bu makaledeki bölümler  
  
-   [İsabetsiz önbellek okuma sayısı ve sayfa hataları](#_core_cache_hits_and_page_faults)  
  
-   [Sıralama ve arama](#_core_sorting_and_searching)  
  
-   [MFC ve sınıf kitaplıkları](#_core_mfc_and_class_libraries)  
  
-   [Paylaşılan kitaplıklar](#vcovrsharedlibraries)  
  
-   [Yığınları](#_core_heaps)  
  
-   [İş parçacıkları](#_core_threads)  
  
-   [Küçük çalışma kümesi](#_core_small_working_set)  
  
##  <a name="_core_cache_hits_and_page_faults"></a>İsabetsiz önbellek okuma sayısı ve sayfa hataları  
 Her iki iç ve dış önbellekteki, önbellek isabet eksik yanı sıra sayfa hataları (program yönergeleri ve veriler için ikincil depolama gitme) bir program performansını yavaşlatabilir.  
  
 CPU önbelleği isabet programınızı 10-20 döngüleri saat maliyeti olabilir. Dış önbellek isabet 20-40 saat döngüleri maliyeti olabilir. Bir sayfa hatası (500 milyon yönergeleri/saniye işleyen bir işlemci ve süredir sayfa hatası 2 milisaniyelik varsayılarak) bir milyon saat döngüleri maliyeti olabilir. Bu nedenle en iyisi kaçırılan Önbelleği İsabetli Okuma ve sayfa hatalarının sayısını azaltır kod yazmaya program yürütme olur.  
  
 Daha fazla sayfa hataları alın veya önbellek gerekli daha sık kaçırılması yavaş programlarının bir nedenidir. Bu durumu önlemek için veri yapıları ilgili şeyler birlikte tutmak anlamına gelir başvuru iyi yere göre ile kullanmak önemlidir. Bazen mükemmel görünen bir veri yapısı başvuru zayıf yere göre nedeniyle horrible olmadığı ortaya çıkmıştır ve bazen ters geçerlidir. Aşağıda, iki örnek verilmiştir:  
  
-   Öğenin veya sona listesini çapraz geçiş aradığınızda, her atlanan bağlantısı yolunu önbellek kaçırılması veya bir sayfa hatasına neden dinamik olarak ayrılan bağlı listeler program performansı düşürebilir. Basit diziler üzerinde temel bir listesi uygulaması, gerçekte daha iyi önbelleğe alma nedeniyle çok daha hızlı olabilir ve daha az hataları bile sayfa — dizi daha zor büyümeye olacak bulgusunun izin vererek, hala daha hızlı olabilir.  
  
-   Karma tabloları dinamik olarak bağlı listeler ayrılan kullanmak performansı düşürebilir. Uzantıya göre dinamik olarak ayrılan bağlı listeler içeriklerini depolamak için kullanmak karma tabloları gerçekleştirebileceğiniz önemli ölçüde daha zayıf. Aslında, son analiz, bir dizi Basit doğrusal arama gerçekte (koşullara bağlı olarak) daha hızlı olabilir. Dizi tabanlı karma tabloları (sözde "kapalı karma") uygulamasıdır üstün performans sık olan çoğunlukla-göz ardı edilir.  
  
##  <a name="_core_sorting_and_searching"></a>Sıralama ve arama  
 Sıralama için birçok genel işlemler karşılaştırıldığında kendiliğinden zaman alıcıdır. Gereksiz yavaşlama önlemek için en iyi yolu, kritik zamanlarda sıralama kaçınmaktır. İçin mümkün olabilir:  
  
-   Sıralama Performans kritik olmayan bir saate kadar erteleyin.  
  
-   Verileri bir önceki, performans kritik olmayan zamanda sıralayın.  
  
-   Yalnızca gerçekten gerek duyduğu veri parçası sıralama sıralama.  
  
 Bazı durumlarda, sıralanmış listesinde oluşturabilirsiniz. Sıralanmış olarak veri eklemek gerekiyorsa, İsabetsiz Önbellek okuma sayısı ve sayfa hataları yol başvuru, zayıf yerleşim yeri ile daha karmaşık bir veri yapısı gerektirebileceği için dikkatli olmak. Her durumda çalışan bir yaklaşım vardır. Çeşitli yaklaşımlar deneyin ve farkları ölçebilirsiniz.  
  
 Sıralama için genel bazı ipuçları şunlardır:  
  
-   Stok sıralama hatalar en aza indirmek için kullanın.  
  
-   Önceden sıralama karmaşıklığını azaltmak için yapabileceğiniz herhangi bir iş faydalı olur. Bir kerelik geçişi verilerinizi üzerinden karşılaştırmaları basitleştirir ve sıralama (n günlük n) O O(n) için azaltır, neredeyse kesinlikle şimdi gelecektir.  
  
-   Sıralama algoritması ve çalıştırmak için beklediğiniz veri başvuru yerleşim düşünün.  
  
 Sıralama için aramalar için daha az alternatifleri vardır. Arama zaman açısından kritik bir ikili arama veya karma tablo arama neredeyse her zaman en iyi ise, ancak sıralama ile gibi yerleşim yeri göz önünde bulundurmanız gerekir. Küçük bir dizi doğrusal arama İsabetsiz Önbellek veya ikili arama sayfa hataları neden olan çok sayıda işaretçileri ile bir veri yapısı üzerinden daha hızlı olabilir.  
  
##  <a name="_core_mfc_and_class_libraries"></a>MFC ve sınıf kitaplıkları  
 Microsoft Foundation sınıfları (MFC) kod yazma büyük ölçüde basitleştirebilir. Zaman açısından kritik kod yazarken sınıfların bazıları devralınmış yükünü haberdar olmanız gerekir. Performans gereksinimlerinizi karşılıyorsa görmek için zaman açısından kritik kod kullanan MFC kodu inceleyin. Aşağıdaki listede, MFC sınıfları ve işlevleri bilincinde olmanız gereken tanımlanmaktadır:  
  
-   `CString`MFC için bellek tahsis etmek için C çalışma zamanı kitaplığı çağıran bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) dinamik olarak. Genel olarak bakıldığında, `CString` herhangi dinamik olarak ayrılan bir dize olarak etkilidir. Dizesiyle dinamik olarak ayrılan gibi dinamik ayırma ve yayın yüke sahiptir. Genellikle, bir basit `char` dizi yığında aynı amaca hizmet eder ve daha hızlıdır. Kullanmayan bir `CString` bir sabit dize depolamak için. Bunun yerine `const char *` kullanın. Gerçekleştirdiğiniz ile herhangi bir işlem bir `CString` nesnesi bazı ek sahiptir. Çalışma zamanı kitaplığını kullanarak [dize işlevleri](../../c-runtime-library/string-manipulation-crt.md) daha hızlı olabilir.  
  
-   `CArray`A [CArray](../../mfc/reference/carray-class.md) normal bir dizi değil, ancak programınızı, gerekmeyebilir esneklik sağlar. Dizi için belirli sınırları biliyorsanız, bunun yerine genel sabit bir dizi kullanabilirsiniz. Kullanırsanız `CArray`, kullanın `CArray::SetSize` boyutuna kurmak ve olarak büyüdüğü bir yeniden ayırma gerekli olduğunda öğe sayısını belirtin. Aksi takdirde, öğe eklemek, dizi sık bırakılan ve kopyalanır, verimsiz ve bellek parçalara neden olabilir. Ayrıca dikkat edin, bir diziye bir öğe eklemek isterseniz `CArray` sonraki öğeleri bellekte taşır ve dizi büyümeye gerekebilir. Bu eylemler İsabetsiz Önbellek okuma sayısı ve sayfa hataları neden olabilir. MFC kullanan kodu bakarsanız, daha belirgin bir şey performansını artırmak için senaryonuz için yazabilirsiniz görebilirsiniz. Bu yana `CArray` bir şablon, örneğin, sağladığınız `CArray` özelleştirmeleri belirli türleri için.  
  
-   `CList`[CList](../../mfc/reference/clist-class.md) karakteriyle bağlantılı bir liste öğesi ekleme head hızlı olmasını olduğu sonu ve bilinen bir konuma (`POSITION`) listesinde. Bir öğe değeri veya dizin tarafından arayan bir sıralı arama, ancak olabilen listesi uzunsa, yavaş gerektirir. Kodunuzu karakteriyle bağlantılı listesini gerektirmiyorsa kullanarak alan isteyebilirsiniz `CList`. Tek bağlı bir liste kullanarak tüm işlemleri için ek bir işaretçi yanı sıra bu işaretçinin bellek güncelleştirme yükünü kaydeder. Ek bellek harika değildir, ancak başka bir fırsat İsabetsiz Önbellek okuma sayısı veya sayfa hataları için değil.  
  
-   `IsKindOf`Bu işlev, birçok çağrıları üretir ve çok sayıda farklı veri alanlarını başvuru hatalı yere göre önde gelen bellekte erişebilirsiniz. Hata ayıklama derlemede (örneğin bir ASSERT çağrısı) için kullanışlıdır ancak bir yayın derleme kullanmaktan kaçınmak deneyin.  
  
-   `PreTranslateMessage`Kullanım `PreTranslateMessage` windows belirli ağacının farklı klavye Hızlandırıcıları gerektiğinde veya içinde ileti Pompalama ileti işleme eklemeniz gerekir. `PreTranslateMessage`MFC gönderme iletileri değiştirir. Geçersiz kılarsanız `PreTranslateMessage`, bu nedenle yalnızca düzeyinde gerekli. Örneğin, geçersiz kılmak gerekli değildir `CMainFrame::PreTranslateMessage` yalnızca belirli bir görünüm alt öğelerine giden iletiler yer ilgileniyorsanız. Geçersiz kılma `PreTranslateMessage` görünüm için bunun yerine sınıfı.  
  
     Normal gönderme yolunu kullanarak aşmak değil `PreTranslateMessage` herhangi penceresine gönderilen tüm iletiler işlemek için. Kullanım [pencere yordamları](../../mfc/registering-window-classes.md) ve MFC ileti eşlemeleri bu amaç için.  
  
-   `OnIdle`Boşta olaylar gerçekleşebilir bazen değil beklediğiniz gibi arasında `WM_KEYDOWN` ve `WM_KEYUP` olaylar. Zamanlayıcılar kodunuzu tetiklemek için daha etkili bir yolu olabilir. Zorlama `OnIdle` art arda false iletileri oluşturma ya da her zaman döndürerek çağrılacak `TRUE` geçersiz kılma gelen `OnIdle`, hangi hiçbir zaman izin uyku moduna, iş parçacığı. Yeniden süreölçer veya ayrı bir iş parçacığı daha uygun olabilir.  
  
##  <a name="vcovrsharedlibraries"></a>Paylaşılan kitaplıklar  
 Kodu yeniden kullanma tercih edilir. Başka birinin kod kullanacaksanız, tam olarak performans sizin için önemli olduğu durumlarda yaptığı bildiğinizden emin olmalısınız. Bunu anlamanın en iyi yolu kaynak kod atlama veya PView veya Performans İzleyicisi gibi araçlarla ölçme ' dir.  
  
##  <a name="_core_heaps"></a>Yığınları  
 Birden çok yığınlara tedbirli ile kullanın. İle oluşturulan ek yığın `HeapCreate` ve `HeapAlloc` yönetmek ve ilgili ayırmaları birtakım dispose izin verir. Çok fazla bellek yürütme yok. Birden çok yığınlara kullanıyorsanız, özel başlangıçta kararlıdır bellek miktarını dikkat edin.  
  
 Birden çok yığınlara yerine kodunuzu ve varsayılan öbek arasında arabirim için yardımcı işlevleri kullanabilirsiniz. Yardımcı işlevleri, uygulamanızın performansını artırabilir özel ayırma stratejileri kolaylaştırır. Örneğin, sık küçük ayırmaları gerçekleştirirseniz, bu ayırmalardan varsayılan öbek bir parçası için yerelleştirme isteyebilirsiniz. Büyük bir bellek bloğu ayrılamadı ve o bloğundan suballocate için yardımcı işlevini kullanın. Bunu yaparsanız dışında varsayılan öbek ayırma gelen olduğundan, kullanılmayan belleği ile ek yığınlara yoktur.  
  
 Bazı durumlarda, ancak varsayılan öbek kullanarak başvuru yere göre azaltabilir. Yığın yığın nesneleri taşıma etkilerini ölçmek için işlem Görüntüleyici, Spy ++ veya Performans İzleyicisi'ni kullanın.  
  
 Öbek üzerinde her ayırma için hesap adına, yığın ölçün. C çalışma zamanı kullanmak [hata ayıklama yığını yordamları](/visualstudio/debugger/crt-debug-heap-details) denetim noktasına ve, yığın dökümü. Microsoft Excel gibi bir elektronik tablo programına çıkış okuyun ve sonuçları görüntülemek için pivot tablolarını kullanın. Toplam sayısı, boyutu ve ayırmalarının dağıtım unutmayın. Bu çalışma kümesi boyutu ile karşılaştırın. Ayrıca ilgili ölçekli nesnelerin Kümelemesi adresindeki arayın.  
  
 Performans sayaçları, bellek kullanımını izlemek için de kullanabilirsiniz.  
  
##  <a name="_core_threads"></a>İş parçacıkları  
 Arka plan görevleri için olayların etkili boşta işleme iş parçacıkları kullanmaktan daha hızlı olabilir. Tek iş parçacıklı bir programda referansın yere göre anlamak daha kolay olur.  
  
 İyi altın kural yalnızca üzerinde engelleyen bir işletim sistemi bildirim arka plan çalışması kök dizininde ise bir iş parçacığı kullanmaktır. Bir olay ana iş parçacığını engellemek için pratik olduğu için iş parçacığı böyle bir durumda en iyi çözümdür.  
  
 İş parçacığı iletişim sorunları da sunar. Bir liste iletilerinin veya ayırma ve paylaşılan bellek kullanarak, iş parçacıkları arasında iletişimi bağlantı yönetmeniz gerekir. İletişimi bağlantı genellikle yönetme yarış durumları engellemek için ve sorunları kilitlenme eşitleme gerektirir. Bu karmaşıklık kolayca hataları ve performans sorunlarını kapatabilirsiniz.  
  
 Daha fazla bilgi için bkz: [boşta döngü işleme](../../mfc/idle-loop-processing.md) ve [çoklu iş parçacığı kullanımı](../../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
##  <a name="_core_small_working_set"></a>Küçük çalışma kümesi  
 Daha küçük çalışma kümeleri başvuru daha iyi yere göre daha az sayfa hataları ve daha fazla önbellek isabet anlamına gelir. İşlemin çalışma kümesi başvuru yere göre ölçmek üzere işletim sistemini doğrudan sağlayan en yakın ölçümüdür.  
  
-   Çalışma kümesi, üst ve alt sınırları ayarlamak için kullanın [SetProcessWorkingSetSize](http://msdn.microsoft.com/library/windows/desktop/ms683226.aspx).  
  
-   Çalışma kümesi, üst ve alt sınırları almak için [GetProcessWorkingSetSize](http://msdn.microsoft.com/library/windows/desktop/ms686234.aspx).  
  
-   Çalışma kümesi boyutu görüntülemek için Spy ++ kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kodunuzu iyileştirme](../../build/reference/optimizing-your-code.md)
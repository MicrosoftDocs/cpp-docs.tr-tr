---
title: Zamana Bağlı Kodu Geliştirme İpuçları
ms.date: 11/04/2016
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
ms.openlocfilehash: 97a9a54be1b322edfe8cfeca84e03f9a6766b8fe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62314721"
---
# <a name="tips-for-improving-time-critical-code"></a>Zamana Bağlı Kodu Geliştirme İpuçları

Hızlı kod yazma, uygulamanızı ve sistemi ile nasıl etkileşim kurduğu tüm yönlerini anlaşılması gerekir. Bu konuda, zaman açısından kritik kod bölümlerini tatmin edici bir şekilde gerçekleştirdiğinizden emin olun yardımcı olmak için daha belirgin kodlama tekniklerini bazılarının önerileri sunar.

Özetlemek gerekirse, zamana bağlı kodu geliştirme gerektiren:

- Programınızın hangi parçalarının hızlı olmak zorunda bildirin.

- Boyutu ve kodunuzu hızını bildirin.

- Yeni özellikler maliyetini bildirin.

- İşi tamamlamak için gereken en düşük iş bildirin.

Kodunuzun performansını bilgi toplamak için Performans İzleyicisi'ni (perfmon.exe) kullanabilirsiniz.

## <a name="sections-in-this-article"></a>Bu makaledeki bölümler

- [İsabetsiz önbellek okuma sayısı ve sayfa hataları](#_core_cache_hits_and_page_faults)

- [Sıralama ve arama](#_core_sorting_and_searching)

- [MFC ve sınıf kitaplıkları](#_core_mfc_and_class_libraries)

- [Paylaşılan kitaplıklar](#vcovrsharedlibraries)

- [Yığınlar](#_core_heaps)

- [İş Parçacıkları](#_core_threads)

- [Küçük çalışma kümesi](#_core_small_working_set)

##  <a name="_core_cache_hits_and_page_faults"></a> İsabetsiz önbellek okuma sayısı ve sayfa hataları

Her iki iç ve dış önbellekte, önbellek isabet eksik yanı sıra sayfa hataları (program yönergeleri ve veriler için ikincil depolama gidip) bir programın performansını yavaşlatabilir.

CPU önbellek isabet programınızı 10-20 saat döngüleri maliyeti olabilir. Dış önbellek isabet 20-40 saat döngüsü maliyeti olabilir. Sayfa hatası (yönergeleri saniyede 500 milyon işleyen bir işlemci ve süredir sayfa hatası 2 milisaniye varsayılarak) bir milyon saat döngüsü maliyeti olabilir. Bu nedenle, program yürütmenin kaçırılan Önbelleği İsabetli Okuma ve sayfa hatalarının sayısını azaltacak kod yazmak için en iyi ilgiden gereklidir.

Daha fazla sayfa hataları alın veya önbellek gerekli çok sık kaçırmayın yavaş programları için bir nedenidir. Bunu önlemek için veri yapıları ile ilgili öğeleri bir arada tutmak anlamına gelir, başvuru iyi konumu kullanmak önemlidir. Başvurunun düşük konumu nedeniyle horrible olmasını bazen harika görünen veri yapısı ettik ve bazen bu durumun tersi de geçerlidir. İki örnek aşağıda verilmiştir:

- Bir öğenin veya sonuna bir liste geçiş arama yaptığınızda Atlanan her bağlantı önbellek kaçırmayın veya sayfa hatasına neden olduğundan dinamik olarak ayrılan bağlantılı liste program performansı azaltabilir. Basit dizileri temel alınarak bir listesi uygulaması gerçekten daha iyi önbelleğe alma nedeniyle çok daha hızlı olabilir ve daha az bile hataları sayfasında — dizi büyümesine zor olabilecek bulgusunun izin vererek, yine de daha hızlı olabilir.

- Karma tabloları bağlantılı liste dinamik olarak ayrılan kullanmak performansı düşürebilir. Uzantıya göre dinamik olarak ayrılan bağlantılı liste içeriklerini depolamak için kullandığınız karma tabloları gerçekleştirebileceğiniz önemli ölçüde daha kötü oluyor. Aslında, son analiz, basit bir doğrusal arama bir dizi aracılığıyla gerçekten (koşullara bağlı olarak) daha hızlı olabilir. Genellikle atlamış üstün performans sık olan bir uygulama olan dizi tabanlı karma tabloları (sözde "kapalı karma").

##  <a name="_core_sorting_and_searching"></a> Sıralama ve arama

Sıralama için birçok tipik işlem kıyasla kendiliğinden zaman alıcıdır. Gereksiz yavaşlama önlemek için en iyi yolu, kritik zamanlarda sıralama kaçınmaktır. Şunları olabilir:

- Performans kritik olmayan bir zamana kadar sıralama erteleyin.

- Bir önceki, performans kritik olmayan zamanda verileri sıralayın.

- Yalnızca gerçekten gerekli verileri parçası sıralama sıralama.

Bazı durumlarda, sıralanmış bir listede oluşturabilirsiniz. Sıralı düzende veri eklemek gerekiyorsa, İsabetsiz Önbellek okuma sayısı ve sayfa hataları için önde gelen düşük konumu, başvurunun ile daha karmaşık bir veri yapısı gerektirebilecek dikkatli. Her durumda çalıştığından bir yaklaşım yoktur. Çeşitli yaklaşımlar deneyebilirsiniz ve farkları ölçün.

Sıralama için genel bazı ipuçları şunlardır:

- Hataları en aza indirmek için stok bir sıralama kullanın.

- Önceden sıralama karmaşıklığını azaltmak için yapabileceğiniz herhangi bir iş faydalı olur. Bir kerelik geçişi verileriniz üzerinde karşılaştırmalar basitleştirir ve sıralama için O(n) O (log n n) azaltır, olasılıkla önceden gelir.

- Yerleşim Sıralama algoritması ve çalıştırmak için beklediğiniz verileri başvurunun düşünün.

Daha az alternatifleri için sıralama arar vardır. Arama zaman açısından kritik bir ikili arama veya karma tablosu aramasında neredeyse her zaman en iyi ise, ancak sıralama ile gibi yerleşim yeri dikkat etmeniz gerekir. Doğrusal Arama küçük bir dizi aracılığıyla, ikili arama sayfa hataları neden olan çok sayıda işaretçiler veri yapısı üzerinden daha hızlı bir şekilde veya önbelleği isabetsizlikleri.

##  <a name="_core_mfc_and_class_libraries"></a> MFC ve sınıf kitaplıkları

Microsoft Foundation Classes (MFC), kod yazma büyük ölçüde basitleştirebilir. Zaman açısından kritik kod yazarken, sınıfların bazıları devralınan yükü haberdar olmanız gerekir. Performans gereksinimlerinizi karşılıyorsa görmek için zaman açısından kritik kod kullanan MFC kodu inceleyin. Aşağıdaki listede, MFC sınıfları ve işlevleri bilincinde olmanız gereken tanımlanmaktadır:

- `CString` MFC için bellek ayırmak için C çalışma zamanı kitaplığı çağıran bir [CString](../atl-mfc-shared/reference/cstringt-class.md) dinamik olarak. Genel olarak bakıldığında, `CString` herhangi dinamik olarak ayrılan bir dize olarak etkilidir. Bir dinamik olarak ayrılan dize olarak dinamik ayırma ve serbest bırakma getirdiği ek yüke sahiptir. Genellikle, bir basit `char` yığında dizi aynı amaca hizmet eder ve daha hızlıdır. Kullanmayan bir `CString` bir sabit dize depolamak için. Bunun yerine `const char *` kullanın. Gerçekleştirdiğiniz ile herhangi bir işlem bir `CString` nesnenin bazı ek yükler vardır. Çalışma Zamanı Kitaplığı kullanarak [dize işlevleri](../c-runtime-library/string-manipulation-crt.md) daha hızlı olabilir.

- `CArray` A [CArray](../mfc/reference/carray-class.md) normal bir dizi değil, ancak programınızın, gerekmeyebilir esneklik sağlar. Dizi için belirli sınırlar biliyorsanız, bunun yerine genel bir sabit dizi kullanabilirsiniz. Kullanırsanız `CArray`, kullanın `CArray::SetSize` boyutuna kurmak ve kullandığı büyüdüğü bir reallocation gerekli olduğunda öğelerin sayısını belirtin. Aksi takdirde, öğeleri ekleyerek, dizinizi sık bırakılan ve kopyalanır, verimsiz ve bellek parçası neden olabilir. Ayrıca unutmayın, bir diziye bir öğe eklerseniz, `CArray` bellekte sonraki öğeleri taşır ve dizi büyütmede ihtiyacınız. Bu Eylemler, İsabetsiz Önbellek okuma sayısı ve sayfa hataları neden olabilir. MFC kullanan kod bakarsanız, daha belirli bir şeyi performansını artırmak için kendi senaryonuza yazabilirsiniz görebilirsiniz. Bu yana `CArray` sağlıyor olabilir gibi bir şablon olduğunu `CArray` uzmanlıkları belirli türler için.

- `CList` [CList](../mfc/reference/clist-class.md) öğe ekleme baş hızlı silmelere izin verir bağlı bir liste olduğundan sonu ve bilinen bir konuma (`POSITION`) listesinde. Değeri veya dizin tarafından öğeyi bakan, sıralı aramaya, ancak olabilen liste uzunsa yavaş gerektirir. Kodunuzu karakteriyle bağlı bir liste gerektirmiyorsa kullanarak yeniden gözden geçir isteyebilirsiniz `CList`. Tek bağlı bir liste kullanarak tüm işlemler için ek bir işaretçi yanı sıra bu işaretçiyi belleği güncelleştirme yükü kaydeder. Ek bellek harika değil, ancak İsabetsiz Önbellek okuma sayısı veya sayfa hataları için başka bir fırsat olduğu.

- `IsKindOf` Bu işlev, birçok çağrıları oluşturmak ve çok miktarda bellek başvurusu hatalı yerleşim yeri önde gelen farklı veri alanlarında erişin. Hata ayıklama yapısında (örneğin bir onay araması) kullanışlıdır ancak bir sürüm yapıda kullanarak kaçınmaya çalışın.

- `PreTranslateMessage` Kullanım `PreTranslateMessage` Windows'un belirli bir ağaç farklı klavye Hızlandırıcılar gerektiğinde veya ileti pompası ileti işleme eklediğinizde. `PreTranslateMessage` MFC gönderme iletilerini değiştirir. Kılarsanız `PreTranslateMessage`, bu nedenle yalnızca düzeyinde gerekli. Örneğin, geçersiz kılmak gerekli değildir `CMainFrame::PreTranslateMessage` yalnızca belirli bir görünümün alt öğelerine giden iletiler ilgilendiğiniz durumunda. Geçersiz kılma `PreTranslateMessage` sınıf görünümü için bunun yerine.

   Normal dağıtım yolu kullanarak aşmak değil `PreTranslateMessage` herhangi bir pencereye gönderilen tüm iletisini işlemek için. Kullanım [pencere yordamları](../mfc/registering-window-classes.md) ve MFC ileti bu amaca yönelik eşler.

- `OnIdle` Boş olaylar meydana gelebilir bazen değil beklediğiniz gibi arasında `WM_KEYDOWN` ve `WM_KEYUP` olayları. Zamanlayıcılar kodunuzu tetiklemek için daha etkili bir yolu olabilir. Doğrulayamıyorsa `OnIdle` false iletileri oluşturarak veya her zaman döndürerek tekrar tekrar çağrılan `TRUE` geçersiz kılma gelen `OnIdle`, hiçbir zaman izin veren uyku durumuna, iş parçacığı. Tekrar bir zamanlayıcı veya ayrı bir iş parçacığı daha uygun olabilir.

##  <a name="vcovrsharedlibraries"></a> Paylaşılan kitaplıklar

Kod yeniden kullanımını tercih edilir. Ancak, başkasının kod kullanacaksanız, tam olarak bunu performansı için kritik olduğu durumlarda gördüğünüze emin olmalısınız. Bunu anlamak için en iyi kaynak kod içerisinde ilerlemeye tarafından ya da PView veya Performans İzleyicisi gibi araçlarla ölçme yoludur.

##  <a name="_core_heaps"></a> Yığınlar

Birden çok yığınlar takdirine bağlı olarak birlikte kullanın. Oluşturulan ek yığınlar `HeapCreate` ve `HeapAlloc` yönetmek ve ardından ilgili ayırmaları birtakım dispose izin verir. Çok fazla bellek işleme yok. Birden çok yığınlar kullanıyorsanız, özel başlangıçta işlenen bellek miktarı dikkat edin.

Birden çok yığınlar yerine kodunuzu ve varsayılan öbek arasında arabirim oluşturmak için yardımcı işlevleri kullanabilirsiniz. Yardımcı İşlevler, uygulamanızın performansını iyileştirebilir özel ayırma stratejisi kolaylaştırır. Örneğin, sık küçük ayırmaları gerçekleştirirseniz, varsayılan yığının bir bölümü bu ayırmaları yerelleştirmek isteyebilirsiniz. Büyük bir bellek bloğunu ayırın ve ardından o suballocate için yardımcı işlevini kullanın. Bunu yaparsanız dışında varsayılan yığın ayırma geliyor olduğundan kullanılmayan belleği ile ek yığınlar olmaz.

Bazı durumlarda, ancak varsayılan yığını kullanarak başvuru yeri azaltabilir. Yığın yığın nesneleri taşıma etkilerini ölçmek için işlem Görüntüleyici, Spy ++ veya Performans İzleyicisi'ni kullanın.

Her ayırma için yığın üzerinde hesap için yığın ölçün. C çalışma zamanı kullanmak [hata ayıklama yığın rutinleri](/visualstudio/debugger/crt-debug-heap-details) denetim noktasına ve, yığın dökümü. Microsoft Excel gibi bir elektronik tablo programına çıktıyı okuma ve sonuçları görüntülemek için Özet Tablo kullanın. Toplam sayısı, boyutu ve dağıtım ayırmaların unutmayın. Çalışma kümesi boyutu ile karşılaştırın. Ayrıca kümeleme ilgili boyutlu nesnelerin arayın.

Performans sayaçları, bellek kullanımını izlemek için de kullanabilirsiniz.

##  <a name="_core_threads"></a> İş parçacıkları

Arka plan görevleri için olayların etkili boşta işleme iş parçacıkları kullanmaktan daha hızlı olabilir. Tek iş parçacıklı bir programda başvuru yeri anlamak kolaydır.

İyi bir kural karşısında hakkında engelleyin bir işletim sistemi bildirim arka plan iş kökünde ise bir iş parçacığı kullanmaktır. Bir olay ana iş parçacığını engellemek için pratik, çünkü iş parçacığı böyle bir durumda en iyi çözümdür.

İş parçacığı iletişim sorunlarını da sunar. İletilerin veya ayırma ve paylaşılan bellek kullanarak bir liste, iş parçacıkları arasında iletişim bağlantısı yönetmeniz gerekir. İletişim bağlantı genellikle yönetme yarış durumlarını önlemek ve kilitlenme sorunları için eşitleme gerektirir. Bu karmaşıklığı, hataları ve performans sorunlarını kolayca etkinleştirebilirsiniz.

Daha fazla bilgi için [boşta döngü işleme](../mfc/idle-loop-processing.md) ve [çoklu iş parçacığı kullanımı](../parallel/multithreading-support-for-older-code-visual-cpp.md).

##  <a name="_core_small_working_set"></a> Küçük çalışma kümesi

Daha küçük çalışma kümeleri başvuru daha iyi bir yerleşim yeri, daha az sayfa hataları ve daha fazla önbellek isabet anlamına gelir. İşlem çalışma kümesini başvuru yeri ölçmek için işletim sistemini doğrudan sağlayan en yakın unsurdur.

- Çalışma kümesi alt ve üst sınırlarını ayarlamak için kullanın [SetProcessWorkingSetSize](/windows/desktop/api/winbase/nf-winbase-getprocessworkingsetsize).

- Çalışma kümesi, üst ve alt sınırları almak için kullanın [GetProcessWorkingSetSize](/windows/desktop/api/winbase/nf-winbase-setprocessworkingsetsize).

- Çalışma kümesi boyutu görüntülemek için Spy ++ kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Kodunuzu İyileştirme](optimizing-your-code.md)

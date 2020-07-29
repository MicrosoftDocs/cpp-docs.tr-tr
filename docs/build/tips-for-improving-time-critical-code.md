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
ms.openlocfilehash: a2cc8062368b89e38b5f96b3134742123af24310
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231487"
---
# <a name="tips-for-improving-time-critical-code"></a>Zamana Bağlı Kodu Geliştirme İpuçları

Hızlı kod yazma, uygulamanızın tüm yönlerini ve sistemle etkileşimini anlamak için gereklidir. Bu konuda, kodunuzun zaman kritik bölümlerinin önemli olmasını sağlamanıza yardımcı olmak için daha belirgin kodlama tekniklerinden bazılarının alternatifleri önerilir.

Özetlemek gerekirse, zaman açısından kritik kodu iyileştirmek için şunları yapmanız gerekir:

- Programınızın hangi bölümlerinin hızlı olması gerektiğini öğrenin.

- Kodunuzun boyutunu ve hızını öğrenin.

- Yeni özelliklerin maliyetini öğrenin.

- İşi gerçekleştirmek için gereken en düşük işi öğrenin.

Kodunuzun performansı hakkında bilgi toplamak için performans izleyicisi 'ni (perfmon.exe) kullanabilirsiniz.

## <a name="sections-in-this-article"></a>Bu makaledeki bölümler

- [Önbellek Isabetsizliği ve sayfa hataları](#_core_cache_hits_and_page_faults)

- [Sıralama ve arama](#_core_sorting_and_searching)

- [MFC ve sınıf kitaplıkları](#_core_mfc_and_class_libraries)

- [Paylaşılan kitaplıklar](#vcovrsharedlibraries)

- [Yığınlar](#_core_heaps)

- [İş Parçacıkları](#_core_threads)

- [Küçük çalışma kümesi](#_core_small_working_set)

## <a name="cache-misses-and-page-faults"></a><a name="_core_cache_hits_and_page_faults"></a>Önbellek Isabetsizliği ve sayfa hataları

Hem iç hem de dış önbellekte bulunmayan önbellek isabetlerinin yanı sıra sayfa hataları (program yönergeleri ve verileri için ikincil depolamaya giden) bir programın performansını yavaşlatır.

CPU önbelleğinde isabet, programınızın 10-20 saat döngülerine ücret verebilir. Dış önbellek okuması maliyet 20-40 saat döngülerine sahip olabilir. Bir sayfa hatası 1.000.000 saat döngülerine sahip olabilir (500.000.000 yönergelerini/saniyeyi ve bir sayfa hatası için 2 milisaniyelik saati işleyen bir işlemcinin olduğu varsayılarak). Bu nedenle, eksik önbellek isabetlerinin ve sayfa hatalarının sayısını azaltacak kod yazmak için program yürütmesinin en iyi şekilde ilgilenmiş olması gerekir.

Yavaş programların bir nedeni, daha fazla sayfa hatası sürme veya önbelleği gerekenden daha sık kaçırmalarıdır. Bunu önlemek için, ilgili şeyleri bir araya getirirken, doğru başvuru olarak veri yapılarını kullanmak önemlidir. Bazen büyük ölçüde başvuru olması nedeniyle harika bir şekilde görünen bir veri yapısı, bazı durumlarda ters değer doğru olabilir. Aşağıda iki örnek verilmiştir:

- Dinamik olarak ayrılan bağlantılı listeler, bir öğe ararken veya bir listenin sonuna kadar geçiş yaparken, atlanan her bağlantı önbelleği kaçırarak veya bir sayfa hatasına neden olabileceği için program performansını azaltabilir. Basit dizileri temel alan bir liste uygulama, daha iyi önbelleğe alma ve daha az sayfa hatası nedeniyle bile daha hızlı olabilir; böylece dizi büyüdükçe daha hızlı olabilir.

- Dinamik olarak ayrılan bağlantılı listeler kullanan karma tablolar, performansı düşürebilir. Uzantıya göre, içeriklerini depolamak için dinamik olarak ayrılan bağlantılı listeleri kullanan karma tablolar önemli ölçüde daha kötüleşme edebilir. Aslında, son analizde, bir dizi aracılığıyla basit bir doğrusal arama gerçekten daha hızlı olabilir (koşullara bağlı olarak). Dizi tabanlı karma tablolar (yani, "kapalı karma" olarak adlandırılır), genellikle üstün performansa sahip olan, sık olmayan bir uygulama olur.

## <a name="sorting-and-searching"></a><a name="_core_sorting_and_searching"></a>Sıralama ve arama

Sıralama, çok sayıda tipik işlem ile karşılaştırıldığında doğal olarak zaman alır. Gereksiz yavaşlama yapmanın en iyi yolu, önemli zamanlarda sıralama yapmaktan kaçınmaktır. Şunları yapabilirsiniz:

- Performans açısından kritik olmayan bir zamana kadar sıralamayı erteleyin.

- Verileri daha önce ve performans açısından kritik olmayan bir zamanda sıralayın.

- Yalnızca gerçekten sıralama gerektiren verilerin bir kısmını sıralayın.

Bazen listeyi sıralanmış sırada oluşturabilirsiniz. Dikkatli olun, çünkü verileri sıralanmış düzende eklemeniz gerekiyorsa, daha karmaşık bir veri yapısına başvuru, ön bellek isabetsizlik ve sayfa hatalarına göre daha karmaşık bir veri yapısı gerekebilir. Her durumda işe yarar bir yaklaşım yoktur. Birkaç yaklaşım deneyin ve farklılıkları ölçün.

Sıralama için bazı genel ipuçları aşağıda verilmiştir:

- Hataları en aza indirmek için bir stok sıralaması kullanın.

- Sıralamanın karmaşıklığını azaltmak için başlamadan önce yapabileceğiniz tüm işler de çalışır. Verilerinizin üzerinde bir kerelik geçiş, karşılaştırmaları basitleştirir ve O (n günlük n) ile O (n) arasında sıralamayı azaltır, neredeyse kesinlikle devam edersiniz.

- Sıralama algoritmasındaki başvurunun ve üzerinde çalışmasını bekleyen verilerin yer aldığı yeri düşünün.

Sıralamaya kıyasla daha az sayıda arama vardır. Arama zaman açısından önemliyse, bir ikili arama veya karma tablo araması neredeyse her zaman en iyisidir, ancak sıralamada olduğu gibi, yerleşim göz önünde bulundurmanız gerekir. Küçük bir dizi üzerinden doğrusal arama, sayfa hatalarına veya önbellek isabetlerine neden olan çok sayıda işaretçileri olan bir veri yapısı aracılığıyla bir ikili aramadan daha hızlı olabilir.

## <a name="mfc-and-class-libraries"></a><a name="_core_mfc_and_class_libraries"></a>MFC ve sınıf kitaplıkları

Microsoft Foundation Sınıfları (MFC) kod yazmayı büyük ölçüde basitleştirir. Zaman açısından kritik kod yazarken, bazı sınıflarda bulunan ek yükün farkında olmanız gerekir. Zaman açısından kritik kodunuzun, performans gereksinimlerinizi karşılayıp karşılamadığını görmek için kullandığı MFC kodunu inceleyin. Aşağıdaki listede, bilmeniz gereken MFC sınıfları ve işlevleri tanımlanmaktadır:

- `CString`MFC, dinamik olarak bir [CString](../atl-mfc-shared/reference/cstringt-class.md) için bellek ayırmak üzere C çalışma zamanı kitaplığını çağırır. Genel olarak, `CString` diğer tüm dinamik olarak ayrılan dizeler kadar etkilidir. Dinamik olarak ayrılan herhangi bir dizede olduğu gibi, dinamik ayırma ve yayınlama ek yüküne sahiptir. Genellikle, yığındaki basit bir **`char`** dizi aynı amaca sunabilir ve daha hızlıdır. `CString`Sabit bir dizeyi depolamak için kullanmayın. Bunun yerine `const char *` kullanın. Bir nesneyle gerçekleştirdiğiniz tüm işlemler `CString` bazı ek yüke sahiptir. Çalışma zamanı kitaplık [dizesi işlevlerinin](../c-runtime-library/string-manipulation-crt.md) kullanılması daha hızlı olabilir.

- `CArray`Bir [CArray](../mfc/reference/carray-class.md) , normal bir dizinin olmadığı esnekliği sağlar, ancak programınız bunun için gerekli olmayabilir. Dizi için belirli sınırları biliyorsanız bunun yerine genel sabit bir dizi kullanabilirsiniz. Kullanıyorsanız `CArray` , `CArray::SetSize` boyutunu oluşturmak için kullanın ve bir yeniden tahsisat gerektiğinde artarak büyüdüğü öğe sayısını belirtin. Aksi takdirde, öğeleri eklemek, dizinizi sık aralıklarla yeniden tahsis edebilir ve kopyalanabilir, bu da verimsiz olan ve belleği parçalara ayırabilecek. Ayrıca bir diziye bir öğe eklerseniz, `CArray` sonraki öğeleri bellekte taşıdıysanız ve diziyi büyütmeniz gerekebilir. Bu eylemler, önbellek isabetsizliği ve sayfa hatalarına neden olabilir. MFC 'nin kullandığı koda bakarsanız, performansı artırmak için senaryonuza özgü bir şey yazabilmenize bakabilirsiniz. , `CArray` Örneğin, bir şablon olduğundan, `CArray` belirli türler için Uzmanlıklar sağlayabilirsiniz.

- `CList`[CList](../mfc/reference/clist-class.md) , benzer bir şekilde bağlanmış bir liste olduğundan, öğe ekleme işlemi baş, kuyruklu ve listedeki bilinen bir konumda () hızlı bir şekilde `POSITION` . Değere veya dizine göre öğe aramak için sıralı bir arama gerekir, ancak liste uzunsa bu yavaş olabilir. Kodunuz, kullanmayı yeniden düşünmek isteyebileceğiniz, daha zengin bağlantılı bir liste gerektirmiyorsa `CList` . Listedir bağlantılı bir liste kullanmak, tüm işlemler için ek bir işaretçi ve bu işaretçi için bellek güncelleştirme yükünü kaydeder. Ek bellek harika değildir, ancak önbellek isabetsizliği veya sayfa hataları için başka bir fırsattır.

- `IsKindOf`Bu işlev, çok sayıda çağrı oluşturabilir ve farklı veri alanlarında çok fazla belleğe erişebilir, bu da hatalı başvuru yer kaplar. Hata ayıklama derlemesi (örneğin, bir onaylama çağrısında) için kullanışlıdır, ancak bunu bir yayın derlemesi içinde kullanmaktan kaçının.

- `PreTranslateMessage``PreTranslateMessage`Belirli bir Windows ağacının farklı klavye hızlandırıcılara ihtiyacı olduğunda veya ileti göndericisinin ileti işleme eklemeniz gerektiğinde kullanın. `PreTranslateMessage`MFC dağıtım iletilerini değiştirir. Geçersiz kıldıysanız `PreTranslateMessage` , bunu yalnızca gerekli düzeyde yapın. Örneğin, `CMainFrame::PreTranslateMessage` yalnızca belirli bir görünümün alt öğelerine giden iletilerde ilgileniyorsanız, üzerine yazmak gerekli değildir. `PreTranslateMessage`Bunun yerine görünüm sınıfı için geçersiz kılın.

   `PreTranslateMessage`Herhangi bir pencereye gönderilen iletileri işlemek için kullanarak normal dağıtım yolunu atlamayın. Bu amaçla [pencere yordamlarını](../mfc/registering-window-classes.md) ve MFC ileti eşlemelerini kullanın.

- `OnIdle`Boştaki olaylar, ve olayları gibi beklenmez `WM_KEYDOWN` `WM_KEYUP` . Süreölçerler, kodunuzun tetiklenmesi için daha verimli bir yol olabilir. `OnIdle`Yanlış iletiler oluşturarak veya her zaman `TRUE` bir geçersiz `OnIdle` kılmaya dönerek, iş parçacığınız uyku moduna neden olmayacak şekilde, tekrar tekrar çağrılabilir şekilde zorlamayın. Bir zamanlayıcı veya ayrı bir iş parçacığı daha uygun olabilir.

## <a name="shared-libraries"></a><a name="vcovrsharedlibraries"></a>Paylaşılan kitaplıklar

Kod yeniden kullanımı tercih edilir. Bununla birlikte, başka birinin kodunu kullanacaksanız, performansın sizin için önemli olduğu durumlarda tam olarak ne yaptığını bildiğinizden emin olmalısınız. Bunu anlamanın en iyi yolu, kaynak kodu aracılığıyla veya PView veya Performance Monitor gibi araçlarla ölçüleyerek.

## <a name="heaps"></a><a name="_core_heaps"></a>Yığınlar

Birden çok Heap 'yi dikkatli kullanın. İle oluşturulan ek Heap 'ler, `HeapCreate` `HeapAlloc` ilgili bir ayırma kümesini yönetmenizi ve sonra atmayı sağlar. Çok fazla bellek oluşturmayın. Birden çok Heap kullanıyorsanız, başlangıçta taahhüt edilen bellek miktarına özel bir dikkat ödeyin.

Birden çok Heap yerine, kodunuz ve varsayılan yığın arasında arabirim sağlamak için yardımcı işlevleri kullanabilirsiniz. Yardımcı işlevler, uygulamanızın performansını iyileştirebilecek özel ayırma stratejilerini kolaylaştırır. Örneğin, sık sık küçük ayırmalar gerçekleştirirseniz, bu ayırmaları varsayılan yığının bir bölümü için yerelleştirmek isteyebilirsiniz. Büyük bir bellek bloğu ayırabilir ve sonra bu bloğundan alt ayırmak için bir yardımcı işlevi kullanabilirsiniz. Bunu yaparsanız, ayırma varsayılan yığından geldiği için kullanılmayan belleğe sahip ek yığınlara sahip olmayacaktır.

Ancak, bazı durumlarda, varsayılan yığını kullanmak başvurunun yer aldığı yeri azaltabilir. Nesneleri öbekten yığına taşımaya yönelik etkileri ölçmek için Işlem Görüntüleyicisi, Spy + + ya da performans Izleyicisini kullanın.

Yığındaki her ayırma için hesap yapabilmeniz için Heap 'larınızı ölçün. Denetim noktası ve yığın dökümünü almak için C çalışma zamanı [hata ayıklama yığın yordamlarını](/visualstudio/debugger/crt-debug-heap-details) kullanın. Çıktıyı Microsoft Excel gibi bir elektronik tablo programında okuyabilir ve özet tabloları kullanarak sonuçları görüntüleyebilirsiniz. Ayırmaların toplam sayısını, boyutunu ve dağılımını aklınızda yapın. Bunları çalışma kümelerinin boyutuyla karşılaştırın. Ayrıca, ilgili boyutlu nesnelerin kümelemesine bakın.

Ayrıca, bellek kullanımını izlemek için performans sayaçlarını da kullanabilirsiniz.

## <a name="threads"></a><a name="_core_threads"></a>Akışları

Arka plan görevleri için, olayların etkin boşta işlenmesi iş parçacıklarını kullanmaktan daha hızlı olabilir. Tek iş parçacıklı bir programda başvurunun yerinin anlaşılması daha kolay.

Parmak izi iyi bir kuralı yalnızca, bloke ettiğiniz bir işletim sistemi bildirimi arka plan işinin kökünde olduğunda bir iş parçacığı kullanmaktır. Bir olayda ana iş parçacığını engellemek pratik olduğundan, bu durumda iş parçacıkları en iyi çözümdür.

İş parçacıkları iletişim sorunları da sunar. İş parçacıklarınız arasında bir ileti listesi ile veya paylaşılan belleği ayırarak ve kullanarak iletişim bağlantısını yönetmeniz gerekir. İletişim bağlantısını yönetmek, yarış koşullarından ve kilitlenme sorunlarından kaçınmak için genellikle eşitleme gerektirir. Bu karmaşıklık, hataları ve performans sorunlarını kolayca açabilir.

Daha fazla bilgi için bkz. [boşta döngüsü işleme](../mfc/idle-loop-processing.md) ve [Çoklu iş parçacığı](../parallel/multithreading-support-for-older-code-visual-cpp.md).

## <a name="small-working-set"></a><a name="_core_small_working_set"></a>Küçük çalışma kümesi

Daha küçük çalışma kümeleri başvuru, daha az sayfa hatası ve daha fazla önbellek okuması anlamına gelir. İşlem çalışma kümesi, işletim sisteminin başvuru yerinin ölçü için doğrudan sağladığı en yakın ölçümdür.

- Çalışma kümesinin üst ve alt sınırlarını ayarlamak için [SetProcessWorkingSetSize](/windows/win32/api/winbase/nf-winbase-getprocessworkingsetsize)kullanın.

- Çalışma kümesinin üst ve alt sınırlarını almak için [GetProcessWorkingSetSize](/windows/win32/api/winbase/nf-winbase-setprocessworkingsetsize)kullanın.

- Çalışma kümesinin boyutunu görüntülemek için Spy + + kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Kodunuzu iyileştirme](optimizing-your-code.md)

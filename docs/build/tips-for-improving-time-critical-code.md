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
ms.openlocfilehash: 039b86eec024daf8e3473bba5d89f190507f3cfd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335450"
---
# <a name="tips-for-improving-time-critical-code"></a>Zamana Bağlı Kodu Geliştirme İpuçları

Hızlı kod yazmak, uygulamanızın tüm yönlerini ve sistemle nasıl etkileşimde olduğunu anlamanızı gerektirir. Bu konu, kodunuzu zaman açısından kritik bölümlerinin tatmin edici bir şekilde performans göstermesini sağlamanıza yardımcı olmak için daha belirgin kodlama tekniklerinden bazılarına alternatifler önerir.

Özetlemek gerekirse, zaman açısından kritik kodu geliştirmek şunları gerektirir:

- Programınızın hangi bölümlerinin hızlı olması gerektiğini bilin.

- Kodunuzu boyutunu ve hızını bilin.

- Yeni özelliklerin maliyetini bilin.

- İşi başarmak için gereken minimum işi bilin.

Kodunuzu performansı hakkında bilgi toplamak için performans monitörünü (perfmon.exe) kullanabilirsiniz.

## <a name="sections-in-this-article"></a>Bu Makaledeki Bölümler

- [Önbellek Misses ve Sayfa Hataları](#_core_cache_hits_and_page_faults)

- [Sıralama ve Arama](#_core_sorting_and_searching)

- [MFC ve Sınıf Kütüphaneleri](#_core_mfc_and_class_libraries)

- [Paylaşılan Kitaplıklar](#vcovrsharedlibraries)

- [Yığın](#_core_heaps)

- [İş Parçacıkları](#_core_threads)

- [Küçük Çalışma Seti](#_core_small_working_set)

## <a name="cache-misses-and-page-faults"></a><a name="_core_cache_hits_and_page_faults"></a>Önbellek Misses ve Sayfa Hataları

Cevapsız önbellek isabetleri, hem iç hem de dış önbellek, hem de sayfa hataları (program talimatları ve veriler için ikincil depolama gidiyor) bir programın performansını yavaşlatır.

CPU önbellek isabet programınızı 10-20 saat döngüleri mal olabilir. Harici önbellek isabet 20-40 saat döngüleri mal olabilir. Bir sayfa hatası bir milyon saat döngüsüne mal olabilir (bir sayfa hatası için 500 milyon talimat/saniye ve 2 milisaniyelik bir süre işleyen bir işlemci varsayarsak). Bu nedenle, cevapsız önbellek isabetleri ve sayfa hataları sayısını azaltacak kod yazmak için program yürütme en iyi yararınadır.

Yavaş programların bir nedeni, daha fazla sayfa hatası almak veya daha sık gerekli önbelleği özledim olmasıdır. Bunu önlemek için, ilgili şeyleri bir arada tutmak anlamına gelen iyi referans yerelliğine sahip veri yapılarını kullanmak önemlidir. Bazen harika görünen bir veri yapısı, referansın zayıf yerelliği nedeniyle korkunç olduğu ortaya çıkar, bazen ise tersi doğrudur. Aşağıda iki örnek verilmiştir:

- Dinamik olarak ayrılmış bağlantılı listeler program performansını azaltabilir, çünkü bir öğeyi aradığınızda veya bir listeyi sonuna kadar geçtiğinde, atlanan her bağlantı önbelleği kaçırabilir veya bir sayfa hatasına neden olabilir. Basit dizilere dayalı bir liste uygulaması aslında daha iyi önbelleğe alma ve hatta daha az sayfa hataları nedeniyle çok daha hızlı olabilir - dizi büyümek zor olurdu gerçeği için izin, hala daha hızlı olabilir.

- Dinamik olarak ayrılmış bağlantılı listeleri kullanan karma tablolar performansı düşürebilir. Uzantısı olarak, içeriklerini depolamak için dinamik olarak ayrılmış bağlantılı listeleri kullanan karma tablolar önemli ölçüde daha kötü performans gösterebilir. Aslında, son çözümlemede, bir dizi üzerinden basit bir doğrusal arama aslında (koşullara bağlı olarak) daha hızlı olabilir. Dizi tabanlı karma tablolar (sözde "kapalı karma"), sık sık üstün performansa sahip genellikle gözden kaçan bir uygulamadır.

## <a name="sorting-and-searching"></a><a name="_core_sorting_and_searching"></a>Sıralama ve Arama

Sıralama, birçok tipik işlemle karşılaştırıldığında doğal olarak zaman alıcıdır. Gereksiz yavaşlamayı önlemenin en iyi yolu kritik zamanlarda sıralamayapmaktan kaçınmaktır. Şunları yapabileceksiniz:

- Sıralamayı performans açısından kritik olmayan bir zamana kadar ertele.

- Verileri daha önceki, performans açısından kritik olmayan bir zamanda sıralayın.

- Verilerin yalnızca gerçekten ayıklanması gereken kısmını sıralayın.

Bazen, listeyi sıralanmış sırayla oluşturabilirsiniz. Dikkatli olun, çünkü verileri sıralı sırayla eklemeniz gerekiyorsa, önbellek eksikliklerine ve sayfa hatalarına yol açan, başvurunun kötü yerelliğine sahip daha karmaşık bir veri yapısına ihtiyaç duyabilirsiniz. Her durumda işe yarayan bir yaklaşım yoktur. Birkaç yaklaşım deneyin ve farklılıkları ölçün.

Sıralama için bazı genel ipuçları aşağıda verilmiştir:

- Hataları en aza indirmek için stok sıralaması kullanın.

- Bu tür karmaşıklığı azaltmak için önceden yapabileceğiniz herhangi bir iş değerlidir. Verilerinizin üzerinden tek seferlik bir geçiş karşılaştırmaları basitleştirir ve O(n log n)'den O(n)'e sıralamayı azaltırsa, kesinlikle öne geçecektir.

- Sıralama algoritmasının başvuru nun bulunduğu yer ve çalışmasını beklediğiniz verileri düşünün.

Aramalar için sıralamadan daha az alternatif vardır. Arama zaman açısından kritikse, ikili arama veya karma tablo araması hemen hemen her zaman en iyisidir, ancak sıralamada olduğu gibi, yerelliği aklınızda tutmanız gerekir. Küçük bir dizide doğrusal arama, sayfa hatalarına veya önbellek kaçırmalarına neden olan çok sayıda işaretçiiçeren bir veri yapısı nda ikili aramadan daha hızlı olabilir.

## <a name="mfc-and-class-libraries"></a><a name="_core_mfc_and_class_libraries"></a>MFC ve Sınıf Kütüphaneleri

Microsoft Hazırlık Sınıfları (MFC) kod yazmayı büyük ölçüde basitleştirebilir. Zaman açısından kritik kod yazarken, bazı sınıfların doğasında bulunan ek yükün farkında olmalısınız. Performans gereksinimlerinizi karşılayıp karşılamadığını görmek için zaman açısından kritik kodunuzu kullandığı MFC kodunu inceleyin. Aşağıdaki liste, dikkat edilmesi gereken MFC sınıflarını ve işlevlerini tanımlar:

- `CString`MFC, [cstring](../atl-mfc-shared/reference/cstringt-class.md) için belleği dinamik olarak ayırmak için C çalışma zamanı kitaplığını çağırır. Genel olarak `CString` konuşursak, diğer dinamik olarak ayrılmış dize kadar verimlidir. Herhangi bir dinamik ayrılmış dize olduğu gibi, dinamik ayırma ve serbest bırakma yükü vardır. Genellikle, yığın `char` üzerinde basit bir dizi aynı amaca hizmet edebilir ve daha hızlıdır. Sabit bir dize depolamak için a `CString` kullanmayın. Bunun yerine `const char *` kullanın. Bir nesneyle gerçekleştirdiğiniz herhangi bir `CString` işlemin bazı genel merkezleri vardır. Çalışma zamanı kitaplık [dize işlevlerini](../c-runtime-library/string-manipulation-crt.md) kullanmak daha hızlı olabilir.

- `CArray`[CArray,](../mfc/reference/carray-class.md) normal bir dizinin olmadığı esneklik sağlar, ancak programınızın buna ihtiyacı olmayabilir. Dizi için belirli sınırları biliyorsanız, bunun yerine genel bir sabit dizi kullanabilirsiniz. Kullanıyorsanız, `CArray`boyutunu `CArray::SetSize` oluşturmak ve yeniden ayırma gerektiğinde büyüyecek öğelerin sayısını belirtmek için kullanın. Aksi takdirde, öğeler eklemek dizinizin sık sık yeniden tahsis edilmesine ve kopyalanmasına neden olabilir, bu da verimsizdir ve belleği parçalayabilir. Ayrıca, bir öğeyi bir diziye eklerseniz, `CArray` sonraki öğeleri bellekte taşır ve diziyi büyütmeniz gerekebilir. Bu eylemler önbellek misses ve sayfa hataları neden olabilir. MFC'nin kullandığı koda bakarsanız, performansı artırmak için senaryonuza daha özel bir şey yazabileceğinizi görebilirsiniz. Örneğin `CArray` bir şablon olduğundan, belirli `CArray` türler için uzmanlıklar sağlayabilirsiniz.

- `CList`[CList](../mfc/reference/clist-class.md) iki kat bağlantılı bir listedir, bu nedenle eleman ekleme, listede ki baş, kuyruk ve bilinen bir konumda ()`POSITION`hızlıdır. Bir öğeyi değere veya dizine göre aramak, liste uzunsa yavaş olabilecek sıralı bir arama gerektirir. Kodunuz iki kat bağlantılı bir liste gerektirmiyorsa, `CList`'yi kullanarak yeniden düşünmek isteyebilirsiniz. Tek başına bağlı bir liste kullanmak, tüm işlemler için ek bir işaretçiyi güncelleştirmenin yanı sıra işaretçi için bellek kaydeder. Ek bellek büyük değildir, ancak önbellek misses veya sayfa hataları için başka bir fırsattır.

- `IsKindOf`Bu işlev birçok çağrı oluşturabilir ve farklı veri alanlarında çok fazla belleğe erişebilir ve bu da başvurunun kötü bir yerelliğine yol açabilir. Hata ayıklama yapısı (örneğin, bir ASSERT çağrısında) için yararlıdır, ancak bir sürüm yapısında kullanmaktan kaçınmaya çalışın.

- `PreTranslateMessage`Belirli `PreTranslateMessage` bir pencere ağacının farklı klavye hızlandırıcılarına ihtiyacı olduğunda veya ileti iletisi iletisi iletisi iletisini ileti pompasına eklemeniz gerektiğinde kullanın. `PreTranslateMessage`MFC gönderme iletilerini değiştirir. Geçersiz kılarsanız, `PreTranslateMessage`bunu yalnızca gereken düzeyde yapın. Örneğin, yalnızca belirli bir görünümdeki çocuklara giden iletilerle ilgileniyorsanız geçersiz kılmanız `CMainFrame::PreTranslateMessage` gerekmez. Bunun `PreTranslateMessage` yerine görünüm sınıfı için geçersiz kılma.

   Herhangi bir pencereye gönderilen herhangi `PreTranslateMessage` bir iletiyi işlemek için kullanarak normal gönderme yolunu aşmayın. Bu amaçla [pencere yordamlarını](../mfc/registering-window-classes.md) ve MFC ileti eşlemlerini kullanın.

- `OnIdle`Boşta kalan olaylar, ara `WM_KEYDOWN` lar ve `WM_KEYUP` olaylar gibi beklemediğiniz zamanlarda oluşabilir. Zamanlayıcılar kodunuzu tetiklemek için daha etkili bir yol olabilir. Yanlış iletiler oluşturarak veya iş parçacığınızın uyku moduna `TRUE` girmesine asla `OnIdle`izin vermeyecek olan geçersiz kılmadan her zaman geri dönerek tekrar tekrar çağrılmaya zorlamayın. `OnIdle` Yine, bir zamanlayıcı veya ayrı bir iş parçacığı daha uygun olabilir.

## <a name="shared-libraries"></a><a name="vcovrsharedlibraries"></a>Paylaşılan Kitaplıklar

Kod yeniden kullanımı arzu edilir. Ancak, başka birinin kodunu kullanacaksanız, performansın sizin için kritik öneme geldiği durumlarda tam olarak ne yaptığını bildiğinizden emin olmalısınız. Bunu anlamanın en iyi yolu kaynak kodu geçmek veya PView veya Performance Monitor gibi araçlarla ölçüm yapmaktır.

## <a name="heaps"></a><a name="_core_heaps"></a>Yığın

Takdir yetkisiile birden fazla yığın kullanın. İlgili bir dizi `HeapCreate` ayırmayı yönetmenize ve `HeapAlloc` elden çıkarmanıza izin vermek için oluşturulan ek yığınlar. Çok fazla hafıza verme. Birden çok yığın kullanıyorsanız, başlangıçta işlenen bellek miktarına özel olarak dikkat edin.

Birden çok yığın yerine, kodunuz ve varsayılan yığın arasında ara birim için yardımcı işlevleri kullanabilirsiniz. Yardımcı işlevler, uygulamanızın performansını artırabilecek özel ayırma stratejilerini kolaylaştırır. Örneğin, sık sık küçük ayırmalar gerçekleştirirseniz, bu ayırmaları varsayılan yığının bir bölümüne yerelleştirmek isteyebilirsiniz. Büyük bir bellek bloğu ayırabilir ve sonra bu bloktan alt ayırmak için bir yardımcı işlev kullanabilirsiniz. Bunu yaparsanız, ayırma varsayılan yığından çıktığı için kullanılmayan bellekle ek yığınlar olmaz.

Ancak bazı durumlarda, varsayılan yığın kullanmak başvurunun yerelliğini azaltabilir. Nesneleri yığından yığına taşımanın etkilerini ölçmek için Process Viewer, Spy++veya Performance Monitor'u kullanın.

Yığındaki her tahsisat için hesap verebilmeniz için yığınlarınızı ölçün. Denetim noktası ve yığın dökümü için C çalışma zamanı [hata ayıklama yordamları](/visualstudio/debugger/crt-debug-heap-details) kullanın. Çıktıyı Microsoft Excel gibi bir elektronik tablo programında okuyabilir ve sonuçları görüntülemek için özet tabloları kullanabilirsiniz. Toplam sayıya, boyuta ve ayırmaların dağılımına dikkat edin. Bunları çalışma kümelerinin boyutuyla karşılaştırın. Ayrıca, ilgili boyutlu nesnelerin kümeleme bakın.

Bellek kullanımını izlemek için performans sayaçlarını da kullanabilirsiniz.

## <a name="threads"></a><a name="_core_threads"></a>Iş parçacığı

Arka plan görevleri için, olayların etkin boşta kullanımı iş parçacığı kullanmaktan daha hızlı olabilir. Tek iş parçacığı lı bir programda başvurunun yerelliğini anlamak daha kolaydır.

İyi bir başparmak kuralı, yalnızca engellediğiniz bir işletim sistemi bildirimi arka plan çalışmasının kökündeyse iş parçacığı kullanmaktır. Bir olay üzerinde bir ana iş parçacığı engellemek için pratik olduğundan iş parçacıkları böyle bir durumda en iyi çözümdür.

İş parçacıkları da iletişim sorunları sunar. İletilerin listesiyle veya paylaşılan belleği ayırıp kullanarak iş parçacıklarınız arasındaki iletişim bağlantısını yönetmeniz gerekir. İletişim bağlantısını yönetmek genellikle yarış koşullarını ve kilitlenme sorunlarını önlemek için eşitleme gerektirir. Bu karmaşıklık kolayca hatalara ve performans sorunlarına dönüşebilir.

Daha fazla bilgi için Bkz. [Boşalma Döngüsü İşleme](../mfc/idle-loop-processing.md) ve [Çoklu İş Parçacığı.](../parallel/multithreading-support-for-older-code-visual-cpp.md)

## <a name="small-working-set"></a><a name="_core_small_working_set"></a>Küçük Çalışma Seti

Daha küçük çalışma kümeleri, başvurunun daha iyi yerelliği, daha az sayfa hatası ve daha fazla önbellek isabeti anlamına gelir. İşlem çalışma kümesi, işletim sisteminin doğrudan başvuru nun yerelliğini ölçmek için sağladığı en yakın metriktir.

- Çalışma kümesinin üst ve alt sınırlarını ayarlamak için [SetProcessWorkingSetSize'ı](/windows/win32/api/winbase/nf-winbase-getprocessworkingsetsize)kullanın.

- Çalışma kümesinin üst ve alt sınırlarını almak için [GetProcessWorkingSetSize'ı](/windows/win32/api/winbase/nf-winbase-setprocessworkingsetsize)kullanın.

- Çalışma kümesinin boyutunu görüntülemek için Spy++'ı kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Kodunuzu İyileştirme](optimizing-your-code.md)

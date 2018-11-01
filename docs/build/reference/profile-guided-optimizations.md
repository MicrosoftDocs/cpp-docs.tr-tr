---
title: Profil Temelli İyileştirmeler
ms.date: 03/14/2018
helpviewer_keywords:
- profile-guided optimizations
- optimization, profile-guided [C++]
ms.assetid: 2225c307-d3ae-42c1-8345-a5a959d132dc
ms.openlocfilehash: eb23d91de210ddc9e12886924af3450ce67330d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632563"
---
# <a name="profile-guided-optimizations"></a>Profil Temelli İyileştirmeler

Profil temelli iyileştirme burada iyileştirici .exe veya .dll dosyasının test çalıştırmalarını verileri kullanan bir çıktı dosyası iyileştirmenize olanak tanır. Verilerin nasıl program bir üretim ortamında gerçekleştirmek büyük olasılıkla temsil eder.

Profil temelli iyileştirmeler yalnızca x86 veya x64 yerel hedefler için kullanılabilir. Profil temelli iyileştirmeler, ortak dil çalışma zamanı üzerinde çalışan Çıkış dosyalarını kullanılabilir değil. Bir derleme ile karışık yerel ve yönetilen kod üretmek olsa bile (kullanarak **/CLR** derleyici seçeneği), yalnızca yerel kod profil temelli iyileştirme kullanamazsınız. IDE içinde ayarlamak Bu seçeneklere sahip bir projeyi oluşturmayı denerseniz, bir yapı hatası oluşur.

> [!NOTE]
> Test çalıştırmalarını profil oluşturmadan toplanan bilgileri geçersiz kılar belirtirseniz, aksi takdirde etkili olacak en iyi duruma getirme **/Ob**, **/Os**, veya **/Ot**. Daha fazla bilgi için [/Ob (satır içi işlev genişletmesi)](../../build/reference/ob-inline-function-expansion.md) ve [/Os, /Ot (küçük koda, ayrıcalık hızlı koda ayrıcalık tanı)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md).

## <a name="steps-to-optimize-your-app"></a>Uygulamanızı iyileştirme adımları

Profil temelli iyileştirme kullanmak için uygulamanızı en iyi duruma getirmek için aşağıdaki adımları izleyin:

- Bir veya daha fazla kaynak kod dosyalarını içeren derleme [/GL](../../build/reference/gl-whole-program-optimization.md).

   Her modülü ile oluşturulmuş **/GL** çalışma zamanı davranışını yakalamak için profil temelli iyileştirme test çalıştırmaları sırasında incelenebilir. Profil temelli iyileştirme derlemedeki her bir modüle ile derlenmiş gerekmez **/GL**. İle derlenmiş Modüller yalnızca ancak **/GL** profil temelli iyileştirmeler belgelenmiş ve daha sonra kullanılabilir.

- Kullanarak bağlantıyı [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) ve [/genprofıle veya fastgenprofıle](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md).

   Her ikisini de kullanarak **/LTCG** ve **/genprofıle** veya **fastgenprofıle** izleme eklenmiş uygulama çalıştırıldığında bir .pgd dosyası oluşturur. .Pgd dosyası için test çalıştırması veri eklendikten sonra sonraki bağlantı adım (en iyi duruma getirilmiş görüntü oluşturma) giriş olarak kullanılabilir. Belirtirken **/genprofıle**, isteğe bağlı olarak ekleyebileceğiniz bir **PGD =**_filename_ bağımsız değişkenin bir varsayılan olmayan ad veya konum için .pgd dosyası belirtin. Birleşimi **/LTCG** ve **/genprofıle** veya **fastgenprofıle** bağlayıcı seçenekleri değiştirir kullanım dışı **/LTCG:PGINSTRUMENT** bağlayıcı seçeneği.

- Uygulama profili.

   Her zaman, profili oluşturulmuş bir EXE oturumu sona erer veya profili oluşturulmuş bir DLL yüklenmemiş bir *appname*! # .pgc dosyası oluşturulur. .Pgc dosyası, belirli uygulama testi hakkında bilgi içerir. #, diğer sayısına göre artırılır 1 ile başlayan bir sayıdır *appname*! # .pgc dosyaları dizini. Test çalıştırması en iyi duruma getirmek istediğiniz bir senaryoyu temsil etmeyen bir .pgc dosyası silebilirsiniz.

   Bir test çalıştırması sırasında açık .pgc dosyası kapatılmasını ve yeni bir .pgc dosyası ile oluşturulmasını zorlayabilirsiniz [pgosweep](../../build/reference/pgosweep.md) (örneğin, bir testi senaryosu sonuna uygulama kapatma değil çakıştığında) yardımcı programı.

   Uygulamanız da doğrudan bir PGO işlevi çağırabilirsiniz [PgoAutoSweep](pgoautosweep.md).pgc dosyası olarak çağrısı noktasında profil verilerini yakalamak için. Bu, yakalanan verileri .pgc dosyaları tarafından kapsanan kod üzerinde daha ince denetim verebilirsiniz. Bu işlevi kullanmak nasıl bir örnek için bkz [PgoAutoSweep](pgoautosweep.md) belgeleri.

   Varsayılan olarak, izleme eklenmiş bir derleme oluşturduğunuzda, daha hızlıdır ancak tamamen doğru olmayabilir, iş parçacığı güvenli olmayan modda veri toplama gerçekleştirilir. Kullanarak **EXACT** bağımsız değişkeni **/genprofıle** veya **fastgenprofıle**, daha yavaş ancak daha doğru olan iş parçacığı açısından güvenli modda veri koleksiyonu belirtin. Bu seçenek, ayrıca kullanım dışı ayarlarsanız kullanılabilir [PogoSafeMode](environment-variables-for-profile-guided-optimizations.md#pogosafemode) ortam değişkeni veya kullanım dışı **/POGOSAFEMODE** Araçlı derlemenizi oluştururken bağlayıcı seçeneği.

- Kullanarak bağlantıyı **/LTCG** ve **/USEPROFILE**.

   İkisi de **/LTCG** ve [/USEPROFILE](useprofile.md) iyileştirilmiş görüntü oluşturmak için bağlayıcı seçenekleri. Bu adım alır .pgd dosyası girin. Belirttiğinizde **/USEPROFILE**, isteğe bağlı olarak ekleyebileceğiniz bir **PGD =**_filename_ bağımsız değişkenin bir varsayılan olmayan ad veya konum için .pgd dosyası belirtin. Kullanım dışı'ı kullanarak bu ad ayrıca belirtebilirsiniz **/PGD** bağlayıcı seçeneği. Birleşimi **/LTCG** ve **/USEPROFILE** kullanım dışı değiştirir **/LTCG:PGOPTIMIZE** ve **/LTCG:PGUPDATE** bağlayıcı seçenekleri.

En iyi duruma getirilmiş çıkış dosyası oluşturmak ve daha sonra ek profil oluşturma daha iyileştirilmiş bir görüntü oluşturmak kullanışlı olurdu olduğunu belirlemek bile mümkündür. Alet düzeni görüntüsü ve .pgd dosyası varsa, ek test çalıştırmaları yapın ve aynı kullanarak yeni .pgd dosyası ile iyileştirilmiş görüntü yeniden **/LTCG** ve **/USEPROFILE** bağlayıcı seçenekleri .

## <a name="optimizations-performed-by-pgo"></a>PGO tarafından gerçekleştirilen iyileştirmeleri

Profil temelli iyileştirmeler listesi verilmiştir:

- **Satır içi kullanım** - Örneğin, bir işlev sık B, işlev çağrıları ve B işlevi görece küçük sonra profil temelli iyileştirmeler olacak işlevde A. B satır içi işlevi bir varsa

- **Sanal çağrı Spekülasyon** -belirli bir işlev sanal bir çağrı veya diğer çağrı bir işlev işaretçisi aracılığıyla sık olmasını istiyorsanız, bir profil temelli iyileştirme sık hedeflenen işlevi koşullu olarak yürütülen doğrudan çağrı ekleyebilirsiniz ve doğrudan çağrı satır içine alınmış olabilir.

- **Ayırma kaydetme** - daha iyi register ayırma profil verisi sonuçlarının ile en iyi duruma getirme.

- **Temel blok iyileştirme** -temel blok iyileştirme düşünülebilir (konumu) sayfaların aynı kümesine yerleştirilmesi için belirli bir çerçeve içinde yürütülen yaygın olarak yürütülen temel blokları sağlar. Bu nedenle bellek yükünü en aza kullanılan sayfa sayısını en aza indirir.

- **Boyutu/hızını en iyi duruma getirme** -burada çok zaman harcadığı program işlevleri hızı iyileştirilebilir.

- **İşlev Düzen** - çağrı graf üzerinde temel ve çağıran/çağrılan davranış profili aynı yürütme yolda olma eğilimindedir işlevleri aynı bölümde yerleştirilir.

- **Koşullu dalı iyileştirme** - değer araştırmaları, profil temelli iyileştirmeler, belirli bir değeri bir switch deyiminde diğer değerlere daha sık kullanılan bulabilirsiniz.  Bu değer, ardından switch deyimini çekilebilir.  Aynı ile if/else yönergeleri burada iyileştirici sıralayabilirsiniz yapılabilir if/else böylece ya da Eğer veya başka bir blok yerleştirilir ilk bağlı olarak hangi blok daha sık değer true şeklindedir.

- **Ölü kod ayırma** -bölümleri kümesini sonuna eklenen özel bir bölümü için profil oluşturma sırasında çağrılmaz kod taşınır. Bu etkili bir şekilde bu bölümde sık kullanılan sayfaları dışında tutar.

- **EH kod ayırma** -EH kod olağanüstü yürütülmekte olan, genellikle taşınabilir ayrı bir bölüme profil temelli iyileştirmeler özel durumlar'ın üzerinde yalnızca özel durumları ortaya karar verirken.

- **Bellek yapı içleri** -bir iç öğe genellikle çağrılırsa belirlenebilir, yapı içleri genişletilmesi daha iyi karar. Bir iç öğe Ayrıca taşıma veya kopya blok boyutuna göre iyileştirilebilir.

Visual Studio 2013 kullanıyorsanız, otomatik kullanabilirsiniz [profil destekli iyileştirme eklentisi](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md) performans ve tanılama hub'ı Visual Studio'dan en iyi duruma getirme işlemini kolaylaştırmak ve Visual C++ için. Bu eklenti, Visual Studio'nun sonraki sürümlerinde kullanılamaz.

## <a name="next-steps"></a>Sonraki adımlar

Bu ortam değişkenleri, İşlevler ve araçlar hakkında daha fazla profil temelli iyileştirmeler kullanabilirsiniz:

[Profil Temelli İyileştirmeler için Ortam Değişkenleri](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>
Bu değişkenler senaryoları test çalışma zamanı davranışını belirtmek için kullanılabilir. Yeni bağlayıcı seçenekleri yerine kaldırılmıştır; Bu, bağlayıcı seçenekleri ortam değişkenlerinden taşımanıza yardımcı olmak için okuyun.

[PgoAutoSweep](pgoautosweep.md)<br/>
Bir işlev ayrıntılı .pgc dosyası veri yakalama denetim sağlamak için uygulamanıza ekleyebilirsiniz.

[pgosweep](../../build/reference/pgosweep.md)<br/>
Tüm profil verilerini yazar .pgc dosyası için bir komut satırı yardımcı programını .pgc dosyası kapatır ve yeni bir .pgc dosyası açılır.

[pgomgr](../../build/reference/pgomgr.md)<br/>
Profil verileri, bir veya daha fazla .pgc dosyaları için .pgd dosyası ekler. bir komut satırı yardımcı programı.

[Nasıl Yapılır: Birden Çok PGO Profilini Tek Profilde Birleştirme](../../build/reference/how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)<br/>
Örnekleri **pgomgr** kullanım.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Araçları](../../build/reference/c-cpp-build-tools.md)

---
title: Profil temelli iyileştirmeler
ms.date: 04/23/2019
helpviewer_keywords:
- profile-guided optimizations
- optimization, profile-guided [C++]
ms.assetid: 2225c307-d3ae-42c1-8345-a5a959d132dc
ms.openlocfilehash: 46619e77861b6a3a78d74ce6c6d9173a3a5f270f
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64857322"
---
# <a name="profile-guided-optimizations"></a>Profil temelli iyileştirmeler

Profil temelli iyileştirme (PGO) burada .exe veya .dll dosyasının test çalıştırmalarını verilerden iyileştirici kullanan tüm yürütülebilir bir dosya, iyileştirmenize olanak tanır. Verileri bir üretim ortamında programının olası performans temsil eder.

Profil temelli iyileştirmeler yalnızca x86 veya x64 yerel hedefler için kullanılabilir. Profil temelli iyileştirmeler, ortak dil çalışma zamanı üzerinde çalışan yürütülebilir dosyalar için kullanılamaz. Bir derleme ile karışık yerel ve yönetilen kod üretmek olsa bile (kullanarak **/CLR** derleyici seçeneği), yalnızca yerel kod profil temelli iyileştirme kullanamazsınız. IDE içinde ayarlamak Bu seçeneklere sahip bir projeyi oluşturmayı denerseniz, bir yapı hatası oluşur.

> [!NOTE]
> Test çalıştırmalarını profil oluşturmadan toplanan bilgileri geçersiz kılar belirtirseniz, aksi takdirde etkili olacak en iyi duruma getirme **/Ob**, **/Os**, veya **/Ot**. Daha fazla bilgi için [/Ob (satır içi işlev genişletmesi)](reference/ob-inline-function-expansion.md) ve [/Os, /Ot (küçük koda, ayrıcalık hızlı koda ayrıcalık tanı)](reference/os-ot-favor-small-code-favor-fast-code.md).

## <a name="steps-to-optimize-your-app"></a>Uygulamanızı iyileştirme adımları

Profil temelli iyileştirme kullanmak için uygulamanızı en iyi duruma getirmek için aşağıdaki adımları izleyin:

- Bir veya daha fazla kaynak kod dosyalarını içeren derleme [/GL](reference/gl-whole-program-optimization.md).

   Her modülü ile oluşturulmuş **/GL** çalışma zamanı davranışını yakalamak için profil temelli iyileştirme test çalıştırmaları sırasında incelenebilir. Profil temelli iyileştirme derlemedeki her bir modüle ile derlenmiş gerekmez **/GL**. İle derlenmiş Modüller yalnızca ancak **/GL** profil temelli iyileştirmeler belgelenmiş ve daha sonra kullanılabilir.

- Kullanarak bağlantıyı [/LTCG](reference/ltcg-link-time-code-generation.md) ve [/genprofıle veya fastgenprofıle](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md).

   Her ikisini de kullanarak **/LTCG** ve **/genprofıle** veya **fastgenprofıle** oluşturur bir `.pgd` dosya izleme eklenmiş uygulama çalıştırıldığında. Test çalıştırması veri eklendikten sonra `.pgd` dosyası (en iyi duruma getirilmiş görüntü oluşturma), sonraki bağlantı adım giriş olarak kullanılabilir. Belirtirken **/genprofıle**, isteğe bağlı olarak ekleyebileceğiniz bir **PGD =**_filename_ varsayılan olmayan adı veya konumu belirtmek için bağımsız değişken `.pgd` dosya. Birleşimi **/LTCG** ve **/genprofıle** veya **fastgenprofıle** bağlayıcı seçenekleri değiştirir kullanım dışı **/LTCG:PGINSTRUMENT** bağlayıcı seçeneği.

- Uygulama profili.

   Her zaman, profili oluşturulmuş bir EXE oturumu sona erer veya profili oluşturulmuş bir DLL yüklenmemiş bir `appname!N.pgc` dosyası oluşturulur. A `.pgc` dosyası, belirli uygulama testi hakkında bilgi içerir. *Appname* uygulamanızın adıdır ve *N* sayı bir artırılır 1'den başlayarak, diğer sayısına göre belirlenmektedir `appname!N.pgc` dizindeki dosyalar. Silebilirsiniz bir `.pgc` dosyası test çalıştırması en iyi duruma getirmek istediğiniz bir senaryoyu temsil etmez.

   Bir test çalıştırması sırasında kapanışın şu anda açık olan zorlayabilirsiniz `.pgc` dosya ve yeni bir oluşturulmasını `.pgc` ile dosya [pgosweep](pgosweep.md) (örneğin, bir testi senaryosu sonuna uygulamayla değil çakıştığında yardımcı programı Kapatma).

   Uygulamanız da doğrudan bir PGO işlevi çağırabilirsiniz [PgoAutoSweep](pgoautosweep.md)çağrısı noktasında profil verilerini yakalamak için bir `.pgc` dosya. Yakalanan verileri tarafından kapsanan kod üzerinde daha hassas bir denetim, verebilirsiniz, `.pgc` dosyaları. Bu işlevi kullanmak nasıl bir örnek için bkz [PgoAutoSweep](pgoautosweep.md) belgeleri.

   Varsayılan olarak, izleme eklenmiş bir derleme oluşturduğunuzda, daha hızlı ancak kesin olmayan iş parçacığı güvenli olmayan modda, veri toplama gerçekleştirilir. Kullanarak **EXACT** bağımsız değişkeni **/genprofıle** veya **fastgenprofıle**, daha hassas, iş parçacığı açısından güvenli modda veri toplama belirtebilirsiniz ancak daha yavaş. Bu seçenek, ayrıca kullanım dışı ayarlarsanız kullanılabilir [PogoSafeMode](environment-variables-for-profile-guided-optimizations.md#pogosafemode) ortam değişkeni veya kullanım dışı **/POGOSAFEMODE** Araçlı derlemenizi oluştururken bağlayıcı seçeneği.

- Kullanarak bağlantıyı **/LTCG** ve **/USEPROFILE**.

   İkisi de **/LTCG** ve [/USEPROFILE](reference/useprofile.md) iyileştirilmiş görüntü oluşturmak için bağlayıcı seçenekleri. Bu adım alır giriş `.pgd` dosya. Belirttiğinizde **/USEPROFILE**, isteğe bağlı olarak ekleyebileceğiniz bir **PGD =**_filename_ varsayılan olmayan adı veya konumu belirtmek için bağımsız değişken `.pgd` dosya. Kullanım dışı'ı kullanarak bu ad ayrıca belirtebilirsiniz **/PGD** bağlayıcı seçeneği. Birleşimi **/LTCG** ve **/USEPROFILE** kullanım dışı değiştirir **/LTCG:PGOPTIMIZE** ve **/LTCG:PGUPDATE** bağlayıcı seçenekleri.

En iyi duruma getirilmiş yürütülebilir dosyayı oluşturmak ve daha sonra ek profil oluşturma daha iyileştirilmiş bir görüntü oluşturmak kullanışlı olurdu olduğunu belirlemek bile mümkündür. Varsa Alet düzeni görüntüsü ve kendi `.pgd` dosya kullanılabiliyorsa, ek test çalıştırmaları yapın ve yeni en iyi duruma getirilmiş görüntüyle yeniden `.pgd` kullanarak aynı dosyayı **/LTCG** ve **/USEPROFILE** bağlayıcı seçenekleri.

## <a name="optimizations-performed-by-pgo"></a>PGO tarafından gerçekleştirilen iyileştirmeleri

Profil temelli iyileştirmeler bu denetimleri ve geliştirmeleri içerir:

- **Satır içi kullanım** - Örneğin, bir işlev, A B sık işlev çağrıları ve işlev B, a işlevindeki görece küçük sonra profil temelli iyileştirmeler satır içi işlev B

- **Sanal çağrı Spekülasyon** -belirli bir işlev sanal bir çağrı veya diğer çağrı bir işlev işaretçisi aracılığıyla sık olmasını istiyorsanız, bir profil temelli iyileştirme sık hedeflenen işlevi koşullu olarak yürütülen doğrudan çağrı ekleyebilirsiniz ve doğrudan çağrı satır içine alınmış olabilir.

- **Ayırma kaydetme** -iyileştirme daha iyi profil verisi sonuçlarının göre ayırma kaydedin.

- **Temel blok iyileştirme** -temel blok iyileştirme düşünülebilir (konumu) sayfaların aynı kümesine yerleştirilmesi için belirli bir çerçeve içinde yürütülen yaygın olarak yürütülen temel blokları sağlar. Bellek Yükü en aza indirir kullanılan sayfaların sayısını en aza indirir.

- **Boyutu/hızını en iyi duruma getirme** -burada program harcadığı en fazla yürütme zamanı işlevleri hızı iyileştirilebilir.

- **İşlev Düzen** - çağrı graf üzerinde temel ve çağıran/çağrılan davranış profili aynı yürütme yolda olma eğilimindedir işlevleri aynı bölümde yerleştirilir.

- **Koşullu dalı iyileştirme** - değer araştırmaları, profil temelli iyileştirmeler, belirli bir değeri bir switch deyiminde diğer değerlere daha sık kullanılan bulabilirsiniz.  Bu değer, ardından switch deyimini çekilebilir.  Aynı ile yapılabilir `if`... `else` yönergeleri burada iyileştirici sipariş `if`... `else` bu nedenle, ya da `if` veya `else` blok yerleştirilir ilk olarak, hangi blok bağlı olarak daha sık değer true şeklindedir.

- **Ölü kod ayırma** -bölümleri kümesini sonuna eklenen özel bir bölümü için profil oluşturma sırasında çağırılır değil kod taşınır. Etkili bir şekilde, bu bölümde sık kullanılan sayfaları dışında tutar.

- **EH kod ayırma** -EH çünkü kod yalnızca olağanüstü yürütüldüğünde, genellikle ayrı bir bölüme taşınabilir. Profil temelli iyileştirmeler özel durumlar'ın üzerinde yalnızca özel durumları ortaya karar verirken taşınır.

- **Bellek yapı içleri** - veya bir iç genişletmek için mi, sık çağrıldığına bağlıysa olup olmadığını. Bir iç öğe Ayrıca taşıma veya kopya blok boyutuna göre iyileştirilebilir.

## <a name="next-steps"></a>Sonraki adımlar

Bu ortam değişkenleri, İşlevler ve araçlar hakkında daha fazla profil temelli iyileştirmeler kullanabilirsiniz:

[Profil temelli iyileştirmeler için ortam değişkenleri](environment-variables-for-profile-guided-optimizations.md)<br/>
Bu değişkenler senaryoları test çalışma zamanı davranışını belirtmek için kullanıldı. Bunlar artık kullanımdan kaldırıldı ve yeni bağlayıcı seçenekleri tarafından değiştirildi. Bu belge, ortam değişkenlerinden taşıma için bağlayıcı seçenekleri gösterilir.

[PgoAutoSweep](pgoautosweep.md)<br/>
Bir işlev ayrıntılı sağlamak için uygulamanıza ekleyebilirsiniz `.pgc` dosya verilerini yakalama denetimi.

[pgosweep](pgosweep.md)<br/>
Tüm profil verilerini Yazar bir komut satırı yardımcı programını `.pgc` dosyası kapanır `.pgc` dosyasını açın ve yeni bir açılır `.pgc` dosya.

[pgomgr](pgomgr.md)<br/>
Bir veya daha fazla profil verileri ekleyen bir komut satırı yardımcı programını `.pgc` dosyaları `.pgd` dosya.

[Nasıl yapılır: Birden çok PGO profilini tek profilde birleştirme](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)<br/>
Örnekleri **pgomgr** kullanım.

## <a name="see-also"></a>Ayrıca bkz.

[Ek MSVC derleme araçları](reference/c-cpp-build-tools.md)

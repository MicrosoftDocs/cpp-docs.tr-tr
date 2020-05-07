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

Profil temelli iyileştirme (PGO), iyileştiricinin. exe veya. dll dosyasının test çalıştırmalarının verilerini kullandığı bir yürütülebilir dosyanın tamamını iyileştirmenize olanak tanır. Veriler, programın bir üretim ortamında olası performansını temsil eder.

Profil temelli iyileştirmeler yalnızca x86 veya x64 yerel hedefleri için kullanılabilir. Profil temelli iyileştirmeler, ortak dil çalışma zamanında çalışan yürütülebilir dosyalar için kullanılamaz. Karma yerel ve yönetilen kodla ( **/clr** derleyici seçeneği kullanılarak) bir derleme üretseniz bile, yalnızca yerel kodda profil temelli iyileştirme kullanamazsınız. IDE 'de bu seçeneklerle ayarlanmış bir proje oluşturmaya çalışırsanız, derleme hatası oluşur.

> [!NOTE]
> Profil oluşturma testinizden toplanan bilgiler, **/ob**, **/OS**veya **/ot**belirtirseniz, aksi takdirde geçerli olacak iyileştirmeleri geçersiz kılar. Daha fazla bilgi için bkz. [/ob (satır Içi Işlev genişletmesi)](reference/ob-inline-function-expansion.md) ve [/OS,/ot (küçük koda öncelik ver, hızlı kodu](reference/os-ot-favor-small-code-favor-fast-code.md)tercih et).

## <a name="steps-to-optimize-your-app"></a>Uygulamanızı iyileştirmek için gereken adımlar

Profil temelli iyileştirme kullanmak için, uygulamanızı iyileştirmek üzere aşağıdaki adımları izleyin:

- [/GL](reference/gl-whole-program-optimization.md)ile bir veya daha fazla kaynak kodu dosyası derleyin.

   **/GL** ile derlenen her modül, çalışma zamanı davranışını yakalamak için profil temelli iyileştirme testi çalıştırmaları sırasında incelenebilir. Profil temelli iyileştirme derlemesinde bulunan her modülün **/GL**ile derlenmesi gerekmez. Ancak, yalnızca **/GL** ile derlenen modüller işaretlenir ve daha sonra profil temelli iyileştirmeler için kullanılabilir.

- [/LTCG](reference/ltcg-link-time-code-generation.md) ve [/genprofile veya/fastgenprofile](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)kullanarak bağlantı.

   Hem **/LTCG** hem de **/genprofile** veya **/fastgenprofile** kullanılması, `.pgd` izlenen uygulama çalıştırıldığında bir dosya oluşturur. Test çalıştırma verileri `.pgd` dosyaya eklendikten sonra, bir sonraki bağlantı adımında (iyileştirilmiş görüntü oluşturma) giriş olarak kullanılabilir. **/Genprofile**belirtirken, isteğe bağlı olarak, `.pgd` dosyanın varsayılan adını veya konumunu belirtmek için bir **PGD =**_filename_ bağımsız değişkeni ekleyebilirsiniz. **/LTCG** ve **/genprofile** veya **/fastgenprofile** bağlayıcı seçeneklerinin birleşimi, kullanım DıŞı bırakılan **/LTCG: PGINSTRUMENT** bağlayıcı seçeneğinin yerini alır.

- Uygulamanın profilini yapın.

   Profili oluşturulan her bir EXE oturumu sona erdiğinde veya profili oluşturulmuş bir DLL kaldırıldığında, bir `appname!N.pgc` dosya oluşturulur. Bir `.pgc` dosya belirli bir uygulama testi çalıştırması hakkında bilgi içerir. *appname* , uygulamanızın adıdır ve *N* , dizindeki diğer `appname!N.pgc` dosya sayısına göre arttırılan 1 ile başlayan bir sayıdır. Test çalıştırması iyileştirmek istediğiniz `.pgc` bir senaryoyu temsil ediyorsa bir dosyayı silebilirsiniz.

   Bir test çalıştırması sırasında, şu anda açık `.pgc` olan dosyanın kapatılmasını ve `.pgc` [pgosüpürme](pgosweep.md) yardımcı programıyla yeni bir dosya oluşturmayı zorlayabilirsiniz (örneğin, bir test senaryosunun sonu uygulama kapatma ile kesişmezse).

   Uygulamanız [Ayrıca, çağrı](pgoautosweep.md)bir `.pgc` dosya olarak arama noktasındaki profil VERILERINI yakalamak için PGO işlevini doğrudan çağırabilir. `.pgc` Dosyalarınızda yakalanan verilerin kapsamına giren kod üzerinde daha ayrıntılı bir denetim sağlayabilir. Bu işlevi nasıl kullanacağınızı gösteren bir örnek için bkz. [Pgooto tarama](pgoautosweep.md) belgeleri.

   Araçlı yapınızı oluştururken, varsayılan olarak, veri toplama işlemi iş parçacığı güvenli olmayan modda yapılır, ancak bu daha hızlıdır, ancak daha hızlı olabilir. **/Genprofile** veya **/Fastgenprofile** **tam** bağımsız değişkenini kullanarak, veri toplamayı daha kesin olan ancak daha yavaş olan iş parçacığı güvenli modunda belirtebilirsiniz. Bu seçenek, işaretlenmiş yapınızı oluştururken kullanım dışı [PogoSafeMode](environment-variables-for-profile-guided-optimizations.md#pogosafemode) ortam değişkenini veya kullanım dışı **/POGOSAFEMODE** bağlayıcı seçeneğini ayarlarsanız de kullanılabilir.

- **/LTCG** ve **/useprofile**kullanarak bağlantı.

   İyileştirilmiş görüntü oluşturmak için **/LTCG** ve [/useprofile](reference/useprofile.md) bağlayıcı seçeneklerini kullanın. Bu adım, `.pgd` dosyayı giriş olarak alır. **/USEPROFILE**belirttiğinizde, `.pgd` dosyanın varsayılan olmayan bir adını veya konumunu belirtmek için Isteğe bağlı olarak bir **PGD =**_filename_ bağımsız değişkeni ekleyebilirsiniz. Bu adı, kullanım dışı bırakılan **/PGD** bağlayıcı seçeneğini kullanarak da belirtebilirsiniz. **/LTCG** ve **/USEPROFILE** birleşimi, kullanım dışı BıRAKıLAN **/LTCG: PGOPTIMIZE** ve **/LTCG: pgupdate** bağlayıcı seçeneklerinin yerini alır.

En iyi duruma getirilmiş yürütülebilir dosyayı oluşturmak ve daha sonra daha iyileştirilmiş bir görüntü oluşturmak için ek profil oluşturmanın yararlı olacağını tespit etmek bile mümkündür. Belgelenmiş görüntü ve `.pgd` dosya kullanılabiliyorsa, aynı **/LTCG** ve **/useprofile** bağlayıcı seçeneklerini kullanarak ek test çalıştırmaları gerçekleştirebilir ve iyileştirilmiş görüntüyü daha yeni `.pgd` dosyayla yeniden oluşturabilirsiniz.

## <a name="optimizations-performed-by-pgo"></a>PGO tarafından gerçekleştirilen iyileştirmeler

Profil temelli iyileştirmeler, bu denetimleri ve geliştirmeleri içerir:

- **Satır** içi-Örneğin, bir Işlev genellikle b işlevini çağırırsa ve b işlevi görece küçükse profil temelli iyileştirmeler satır Içi işlev b, a işlevinde.

- **Sanal çağrı** göstergesi-sanal bir çağrı veya bir işlev işaretçisi aracılığıyla başka bir çağrı, genellikle belirli bir işlevi hedefliyorsa, profil temelli iyileştirme, sıklıkla hedeflenen işleve koşullu olarak yürütülen doğrudan çağrı ekleyebilir ve doğrudan çağrı satır içine alınabilir.

- **Kayıt ayırmayı kaydetme** , profil verilerine göre en iyi duruma getirme işlemi, daha iyi kayıt ayırmaya neden

- **Temel blok iyileştirmesi** -temel blok iyileştirmesi, belirli bir çerçeve içinde yürütülen yaygın olarak yürütülen temel blokların aynı sayfa kümesine (konum) yerleştirilmesi için zamana bağlı sağlar. Kullanılan sayfa sayısını en aza indirir, bu da bellek yükünü en aza indirir.

- **Boyut/hız iyileştirmesi** -programın en çok yürütme süresini harcadığı işlevler hız için en iyi duruma getirilebilir.

- **Işlev düzeni** -çağrı grafiğine ve profili oluşturulmuş arayan/çağrılan davranışına göre, aynı yürütme yolu üzerinde olmaya yönelik işlevler aynı bölüme yerleştirilir.

- **Koşullu dal iyileştirmesi** -değer yoklamaları ile, bir switch deyimindeki verilen değerin diğer değerlerden daha sık kullanılması durumunda profil temelli iyileştirmeler bulunabilir.  Bu değer daha sonra switch ifadesinin dışına çekgeçebilir.  Aynı işlem, ile `if`yapılabilir... `else` iyileştiricinin şunları sıraya geçirebileceği yönergeler `if`... `else` `if` ya `else` da bloğunun ilk olarak, hangi bloğa daha sık doğru olduğuna bağlı olarak yerleştirilir.

- **Ölü kod ayrımı** -profil oluşturma sırasında çağrılmayan kod, Bölüm kümesinin sonuna eklenen özel bir bölüme taşınır. Bu bölümü, sık kullanılan sayfalardan etkili bir şekilde korur.

- **Eh kod ayrımı** -Eh kodu yalnızca beklenen bir şekilde yürütüldüğü için, genellikle ayrı bir bölüme taşınabilir. Profil temelli iyileştirmeler özel durumların yalnızca olağanüstü koşullarda gerçekleşeceğini tespit ettiğinde taşınır.

- **Bellek** iç bilgileri-bir iç genişletilmesinin yapılıp yapılmayacağını belirtir. Bir iç öğe, taşınmaların veya kopyaların blok boyutuna göre de iyileştirilebilir.

## <a name="next-steps"></a>Sonraki adımlar

Profil temelli iyileştirmeler için kullanabileceğiniz bu ortam değişkenleri, işlevleri ve araçları hakkında daha fazla bilgi edinin:

[Profil temelli iyileştirmeler için ortam değişkenleri](environment-variables-for-profile-guided-optimizations.md)<br/>
Bu değişkenler, test senaryolarının çalışma zamanı davranışını belirtmek için kullanılmıştır. Artık kullanım dışıdır ve yeni bağlayıcı seçenekleriyle değiştirilirler. Bu belgede ortam değişkenlerinden bağlayıcı seçeneklerine nasıl taşınacağı gösterilmektedir.

[PgoAutoSweep](pgoautosweep.md)<br/>
Ayrıntılı `.pgc` dosya verileri yakalama denetimi sağlamak için uygulamanıza ekleyebileceğiniz bir işlev.

[pgosweep](pgosweep.md)<br/>
Tüm profil verilerini `.pgc` dosyaya yazan, `.pgc` dosyayı kapatan ve yeni `.pgc` bir dosya açan bir komut satırı yardımcı programı.

[pgomgr](pgomgr.md)<br/>
`.pgd` Dosyaya bir veya daha fazla `.pgc` dosyadan profil verileri ekleyen bir komut satırı yardımcı programı.

[Nasıl yapılır: birden çok PGO profilini tek bir profilde birleştirme](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)<br/>
**Pgomgr** kullanımı örnekleri.

## <a name="see-also"></a>Ayrıca bkz.

[Ek MSVC derleme araçları](reference/c-cpp-build-tools.md)

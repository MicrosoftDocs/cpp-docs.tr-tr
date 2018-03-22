---
title: Profil temelli iyileştirmeler | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- profile-guided optimizations
- optimization, profile-guided [C++]
ms.assetid: 2225c307-d3ae-42c1-8345-a5a959d132dc
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ca4c79fd46954d59a8fdd892fabbd53d4bc985f
ms.sourcegitcommit: ee7d74683af7631441c8c7f65ef5ceceaee4a5ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="profile-guided-optimizations"></a>Profil Temelli İyileştirmeler

Profil temelli iyileştirme burada iyileştirici test çalışmalarını .exe veya .dll dosyasının verilerini kullanır bir çıktı dosyası en iyi hale getirmenize olanak tanır. Verileri nasıl program bir üretim ortamında gerçekleştirmek büyük olasılıkla temsil eder.

Profil temelli iyileştirmeler yalnızca x86 veya x64 yerel hedefler için kullanılabilir. Profil temelli iyileştirmeler, ortak dil çalışma zamanı üzerinde çıktı dosyaları kullanılabilir değil. Karışık yerel ve yönetilen kod ile bir derlemeyi üretmek olsa bile (kullanarak **/CLR** derleyici seçeneği), yalnızca yerel kod profil temelli iyileştirme kullanamazsınız. IDE içinde ayarlama Bu seçeneklere sahip bir projeyi derleme çalışırsanız, bir derleme hatası oluşur.

> [!NOTE]
> Test çalışmaları profil toplanan bilgileri geçersiz kılmalar belirtirseniz, aksi takdirde etkili olacak en iyi duruma getirme **/Ob**, **/Os**, veya **/Ot**. Daha fazla bilgi için bkz: [/Ob (satır içi işlev genişletmesi)](../../build/reference/ob-inline-function-expansion.md) ve [/Os, /Ot (küçük koda, ayrıcalık hızlı koda ayrıcalık tanı)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md).

## <a name="steps-to-optimize-your-app"></a>Uygulamanızı en iyi duruma getirme adımları

Profil temelli iyileştirme kullanmak için uygulamanızı en iyi duruma getirmek için aşağıdaki adımları izleyin:

- Bir veya daha fazla kaynak kodu dosyaları ile derleme [/GL](../../build/reference/gl-whole-program-optimization.md).

   İle oluşturulan her modül **/GL** çalışma zamanı davranışını yakalamak için profil temelli iyileştirme test çalışmaları sırasında incelenebilir. Her bir profil temelli iyileştirme yapı modülünde ile derlenmek zorunda değildir **/GL**. Ancak, yalnızca bu ile koda derlenmiş modüller **/GL** Araçlı ve daha sonra kullanılabilir profil temelli iyileştirmeler.

- Kullanarak bağlantı [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) ve [/GENPROFILE veya /FASTGENPROFILE](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md).

   Her ikisini de kullanarak **/LTCG** ve **/GENPROFILE** veya **/FASTGENPROFILE** Araçlı uygulama çalıştırıldığında bir .pgd dosyası oluşturur. Test çalıştırma veri .pgd dosyasına eklendikten sonra sonraki bağlantı adım (en iyi duruma getirilmiş görüntü oluşturma) giriş olarak kullanılabilir. Belirtirken **/GENPROFILE**, isteğe bağlı olarak ekleyebileceğiniz bir **PGD =**_filename_ değişkenini kullanarak bir varsayılan olmayan adı veya .pgd dosyası için konumu belirtin. Birleşimi **/LTCG** ve **/GENPROFILE** veya **/FASTGENPROFILE** bağlayıcı seçenekleri değiştirir kullanım dışı **/LTCG:PGINSTRUMENT** bağlayıcı seçeneği.

- Uygulama profili.

   Her zaman bir profili EXE oturumu sona erer veya profili DLL kaldırılmadan bir *appname*! # .pgc dosyası oluşturulur. .Pgc dosya belirli bir uygulama testi hakkında bilgi içerir. # olduğu diğer numarasına göre artırılır 1 ile başlayan bir sayı *appname*! dizinindeki # .pgc dosyaları. Test çalışmasını en iyi duruma getirmek istediğiniz bir senaryoyu temsil etmeyen .pgc dosya silebilirsiniz.

   Testi sırasında şu anda açık .pgc dosyasının Kapatılmak üzere ve yeni bir .pgc dosya ile oluşturulmasını zorlayabilirsiniz [pgosweep](../../build/reference/pgosweep.md) (örneğin, bir test senaryosu sonuna uygulama kapatma değil çakıştığında) yardımcı programı.

   Uygulamanız da doğrudan PGO işlevi çağırma [PgoAutoSweep](pgoautosweep.md).pgc dosyası olarak çağrı noktasında profil verilerini yakalamak için. Bu, yakalanan verileri .pgc dosyalarında kapsamındaki kod üzerinde daha hassas denetim verebilirsiniz. Bu işlevi kullanmak nasıl bir örnek için bkz: [PgoAutoSweep](pgoautosweep.md) belgeleri.

   Varsayılan olarak işaretlenmiş yapınızın oluşturduğunuzda, veri toplama hızlıdır ancak tamamen doğru olmayabilir iş parçacığı güvenli modda gerçekleştirilir. Kullanarak **tam** bağımsız değişkeni **/GENPROFILE** veya **/FASTGENPROFILE**, ancak daha yavaş daha doğru iş parçacığı açısından güvenli modda veri toplama belirtebilirsiniz. Bu seçenek ayrıca kullanım dışı ayarlarsanız kullanılabilir [PogoSafeMode](environment-variables-for-profile-guided-optimizations.md#pogosafemode) ortam değişkeni veya kullanım dışı **/POGOSAFEMODE** Araçlı yapınızın oluşturduğunuzda, bağlayıcı seçeneği.

- Kullanarak bağlantı **/LTCG** ve **/USEPROFILE**.

   Her ikisini de kullanmanız **/LTCG** ve [/USEPROFILE](useprofile.md) en iyi duruma getirilmiş görüntüsü oluşturmak için bağlayıcı seçenekleri. Bu adım alır giriş .pgd dosyası. Belirttiğinizde **/USEPROFILE**, isteğe bağlı olarak ekleyebileceğiniz bir **PGD =**_filename_ değişkenini kullanarak bir varsayılan olmayan adı veya .pgd dosyası için konumu belirtin. Kullanım dışı kullanarak bu ad ayrıca belirtebilirsiniz **/PGD** bağlayıcı seçeneği. Birleşimi **/LTCG** ve **/USEPROFILE** kullanım dışı değiştirir **/LTCG:PGOPTIMIZE** ve **/LTCG:PGUPDATE** bağlayıcı seçenekleri.

En iyi duruma getirilmiş çıktı dosyası oluşturun ve daha sonra ek profil daha iyileştirilmiş bir görüntü oluşturmak yararlı olabilecek olduğunu belirlemek bile mümkündür. İzleme eklenmiş görüntü ve .pgd dosyası varsa, ek test çalışmalarını yapın ve en iyi duruma getirilmiş görüntünün aynı kullanarak, daha yeni .pgd dosyasıyla yeniden oluşturulması **/LTCG** ve **/USEPROFILE** bağlayıcı seçenekleri .

## <a name="optimizations-performed-by-pgo"></a>PGO tarafından gerçekleştirilen en iyi duruma getirme

Profil temelli iyileştirmeler listesi aşağıdadır:

- **Satır içi kullanım** - Örneğin, bir işlev B, sık işlev çağrıları ve B işlevi görece küçük ardından profil temelli iyileştirmeler olacak A. işlevindeki satır içi işlev B A varsa

- **Sanal çağrısı Spekülasyon** -belirli bir işlevi veya diğer yapılan bir işlev işaretçisi aracılığıyla sanal bir çağrı sık hedefler, profil temelli iyileştirme sık hedeflenen işlevi koşullu yürütülebilir doğrudan çağrısı ekleyebilirsiniz ve doğrudan çağrı içermesinden olabilir.

- **Ayırma kaydetmek** - profili verisi sonuçlarının daha iyi yazmaç ayırma ile en iyi duruma getirme.

- **Temel blok iyileştirme** -temel blok iyileştirme sayfaları (konum) aynı kümesinde yerleştirilecek verilen çerçevesinde geçici olarak execute yaygın olarak yürütülen temel blokları sağlar. Bu nedenle bellek yükünü en aza kullanıldığında, sayfa sayısını en aza indirir.

- **Boyutu/hızı en iyi duruma getirme** -burada program harcadığı çok zaman işlevler hızı için iyileştirilebilir.

- **İşlev düzeni** - çağrı grafik üzerinde temel ve arayan/aranan davranış profili aynı yürütme yol boyunca olma eğilimindedir işlevleri, aynı bölümde yerleştirilir.

- **Koşullu dal iyileştirme** - profil temelli değeri araştırmalar ile en iyi duruma getirme, anahtar deyimi içinde belirli bir değeri diğer değerleri daha sık kullanılan bulabilir.  Bu değer daha sonra switch deyimi dışında çekebilir.  Aynı, eğer/else yönergeleri burada iyileştirici sıralayabilirsiniz yapılabilir IF/başka böylece ya da Eğer veya başka blok yerleştirilir ilk bağlı olarak hangi blok daha sık true.

- **Ölü kod ayrımı** -bölümleri kümesinin sonuna eklenen özel bir bölüm için profil oluşturma sırasında çağrılmaz kod taşındı. Bu etkili bir şekilde bu bölümde sık kullanılan sayfaları dışında tutar.

- **EH kod ayrımı** -EH kod, olağanüstü yürütülmekte genellikle değiştirilebileceği için ayrı bir bölümde profil temelli iyileştirmeler özel durumlar yalnızca olağanüstü koşullara ortaya karar verirken.

- **Bellek iç bilgileri** -bir iç sık çağrıldıysa belirlenemediğinden, iç bilgileri genişletme daha iyi karar. Bir iç da taşır veya kopya blok boyutuna göre iyileştirilebilir.

Visual Studio 2013 kullanıyorsanız, otomatik kullanabilirsiniz [profil temelli iyileştirme eklentisi](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md) performans ve tanılama hub'ı basitleştirmek ve Visual Studio içinde en iyi duruma getirme işlemini kolaylaştırmak için Visual C++ için. Bu eklenti Visual Studio sonraki sürümlerinde kullanılabilir değil.

## <a name="next-steps"></a>Sonraki adımlar

Bu ortam değişkenleri, İşlevler ve araçları hakkında daha fazla profil temelli iyileştirmeler kullanabilirsiniz:

[Profil Temelli İyileştirmeler için Ortam Değişkenleri](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>
Bu değişkenler senaryolarınızı test çalışma zamanı davranışını belirtmek için kullanılabilir. Bunlar lehinde kaldıran yeni bağlayıcı seçenekleri kullanım dışı bırakıldı; ortam değişkenlerinin bağlayıcı seçenekleri taşımanıza yardımcı olmak için bunu okuyun.

[PgoAutoSweep](pgoautosweep.md)<br/>
Bir işlev hassas .pgc dosya veri yakalama denetimi sağlamak için uygulamanızın ekleyebilirsiniz.

[pgosweep](../../build/reference/pgosweep.md)<br/>
Tüm profil verilerini .pgc dosyasına yazar bir komut satırı yardımcı programı .pgc dosyayı kapatır ve yeni bir .pgc dosyası açar.

[pgomgr](../../build/reference/pgomgr.md)<br/>
Profil verileri bir veya daha fazla .pgc dosyalarından .pgd dosyasına ekler. bir komut satırı yardımcı programı.

[Nasıl yapılır: birleştirme birden çok PGO profilini tek profilde içine](../../build/reference/how-to-merge-multiple-pgo-profiles-into-a-single-profile.md) örnekleri **pgomgr** kullanımı.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Araçları](../../build/reference/c-cpp-build-tools.md)

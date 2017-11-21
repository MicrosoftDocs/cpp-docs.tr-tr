---
title: "Profil temelli iyileştirmeler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- profile-guided optimizations
- optimization, profile-guided [C++]
ms.assetid: 2225c307-d3ae-42c1-8345-a5a959d132dc
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 467888dc773a8d84e5a1b3fc1fd2c337b06654be
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="profile-guided-optimizations"></a>Profil Temelli İyileştirmeler
Profil temelli iyileştirme burada iyileştirici test çalışmalarını .exe veya .dll dosyasının verilerini kullanır bir çıktı dosyası en iyi hale getirmenize olanak tanır. Verileri nasıl program bir üretim ortamında gerçekleştirmek büyük olasılıkla temsil eder.  
  
 Profil temelli iyileştirmeler için x86 kullanılabilir yalnızca veya [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] yerel hedefler. Profil temelli iyileştirmeler, ortak dil çalışma zamanı üzerinde çalışacak çıktı dosyaları kullanılabilir değil. Karışık yerel ve yönetilen kod ile bir derlemeyi üretmek olsa bile (ile derleme **/CLR**), yalnızca yerel kod profil temelli iyileştirme kullanamazsınız. IDE içinde ayarlama Bu seçeneklere sahip bir projeyi derleme çalışırsanız, bir yapı hatasına neden olur.  
  
> [!NOTE]
>  Test çalışmaları profil toplanan bilgileri geçersiz kılma belirtirseniz, aksi takdirde etkili olacak en iyi duruma getirme **/Ob**, **/Os**, veya **/Ot**. Daha fazla bilgi için bkz: [/Ob (satır içi işlev genişletmesi)](../../build/reference/ob-inline-function-expansion.md) ve [/Os, /Ot (küçük koda, ayrıcalık hızlı koda ayrıcalık tanı)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md).  
  
 Otomatik profil temelli iyileştirme için Visual C++ performans ve tanılama hub'ı Eklenti basitleştirmek ve Visual Studio içinde en iyi duruma getirme işlemini kolaylaştırmak için kullanabileceğiniz ya da en iyi duruma getirme adımları el ile Visual Studio içinde veya üzerinde gerçekleştirebileceğiniz komut satırı. Kullanımı daha kolay olduğundan eklenti öneririz. Eklenti Al ve uygulamanızı en iyi duruma getirme kullanma hakkında daha fazla bilgi için bkz: [profil temelli iyileştirme eklentisi](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md).  
  
 Her iki profil temelli iyileştirme eklentisi ve el ile profil temelli iyileştirme uygulamanızı en iyi duruma getirmek için aşağıdaki adımları izleyin:  
  
-   Bir veya daha fazla kaynak kodu dosyaları ile derleme [/GL](../../build/reference/gl-whole-program-optimization.md).  
  
     /GL ile oluşturulan her bir modülü çalışma zamanı davranışını yakalamak için profil temelli iyileştirme test çalışmaları sırasında incelenebilir. Her bir profil temelli iyileştirme yapı modülünde /GL. ile derlenmek zorunda değildir Ancak, yalnızca /GL ile derlenmiş modüller Araçlı ve profil temelli iyileştirmeler için daha sonra kullanılabilir olacaktır.  
  
-   Kullanarak bağlantı [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) ve [/GENPROFILE](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md).  
  
     /LTCG ve /GENPROFILE kullanarak bir boş .pgd dosyası oluşturur. Test çalıştırma veri .pgd dosyasına eklendikten sonra sonraki bağlantı adım (en iyi duruma getirilmiş görüntü oluşturma) giriş olarak kullanılabilir. /GENPROFILE belirtirken, isteğe bağlı olarak ekleyebilirsiniz: PGD =`filename` varsayılan olmayan ad veya .pgd dosyası için konumu belirtin.  
  
-   Uygulama profili.  
  
     Her zaman bir profili EXE oturumu sona erer veya profili DLL kaldırılmadan bir *appname*! # .pgc dosyası oluşturulur. .Pgc dosya belirli bir uygulama testi hakkında bilgi içerir. # olduğu diğer numarasına göre artırılır 1 ile başlayan bir sayı *appname*! dizinindeki # .pgc dosyaları. Test çalışmasını en iyi duruma getirmek istediğiniz bir senaryoyu temsil etmeyen .pgc dosya silebilirsiniz.  
  
     Testi sırasında şu anda açık .pgc dosyasının Kapatılmak üzere ve yeni bir .pgc dosya ile oluşturulmasını zorlayabilirsiniz [pgosweep](../../build/reference/pgosweep.md) (örneğin, bir test senaryosu sonuna uygulama kapatma değil çakıştığında) yardımcı programı.  
  
     Kullanabileceğiniz `PogoSafeMode` seçeneğini uygulamanıza profil. Bu seçenek, güvenli mod veya hızlı mod uygulamada profil isteyip istemediğinizi belirtmenizi sağlar. Bu modları hakkında daha fazla bilgi için bkz: [PogoSafeMode](../../build/reference/pogosafemode.md).  
  
-   /LTCG ve /USEPROFILE kullanarak bağlayın.  
  
     /LTCG ve /USEPROFILE kullanarak en iyi duruma getirilmiş görüntüsü oluşturur. Bu adım alır giriş .pgd dosyası. /USEPROFILE belirtirken, isteğe bağlı olarak ekleyebilirsiniz: PGD =`filename` varsayılan olmayan ad veya .pgd dosyası için konumu belirtin. Daha fazla bilgi için bkz: [/LTCG](../../build/reference/ltcg-link-time-code-generation.md).  
  
 En iyi duruma getirilmiş çıktı dosyası oluşturun ve daha sonra ek profil daha iyileştirilmiş bir görüntü oluşturmak yararlı olabilecek olduğunu belirlemek bile mümkündür. İzleme eklenmiş görüntü ve .pgd dosyası varsa, ek test çalışmalarını yapabilirsiniz ve en iyi duruma getirilmiş görüntü yeni .pgd dosyasıyla yeniden.  
  
 Profil temelli iyileştirmeler listesi aşağıdadır:  
  
-   **Satır içi kullanım** - Örneğin, bir işlev B, sık işlev çağrıları ve B işlevi görece küçük ardından profil temelli iyileştirmeler olacak A. işlevindeki satır içi işlev B A varsa  
  
-   **Sanal çağrısı Spekülasyon** -belirli bir işlevi veya diğer yapılan bir işlev işaretçisi aracılığıyla sanal bir çağrı sık hedefler, profil temelli iyileştirme sık hedeflenen işlevi koşullu yürütülebilir doğrudan çağrısı ekleyebilirsiniz ve doğrudan çağrı içermesinden olabilir.  
  
-   **Ayırma kaydetmek** - profili verisi sonuçlarının daha iyi yazmaç ayırma ile en iyi duruma getirme.  
  
-   **Temel blok iyileştirme** -temel blok iyileştirme sayfaları (konum) aynı kümesinde yerleştirilecek verilen çerçevesinde geçici olarak execute yaygın olarak yürütülen temel blokları sağlar. Bu nedenle bellek yükünü en aza kullanıldığında, sayfa sayısını en aza indirir.  
  
-   **Boyutu/hızı en iyi duruma getirme** -burada program harcadığı çok zaman işlevler hızı için iyileştirilebilir.  
  
-   **İşlev düzeni** - çağrı grafik üzerinde temel ve arayan/aranan davranış profili aynı yürütme yol boyunca olma eğilimindedir işlevleri, aynı bölümde yerleştirilir.  
  
-   **Koşullu dal iyileştirme** - profil temelli değeri araştırmalar ile en iyi duruma getirme, anahtar deyimi içinde belirli bir değeri diğer değerleri daha sık kullanılan bulabilir.  Bu değer daha sonra switch deyimi dışında çekebilir.  Aynı, eğer/else yönergeleri burada iyileştirici sıralayabilirsiniz yapılabilir IF/başka böylece ya da Eğer veya başka blok yerleştirilir ilk bağlı olarak hangi blok daha sık true.  
  
-   **Ölü kod ayrımı** -bölümleri kümesinin sonuna eklenen özel bir bölüm için profil oluşturma sırasında çağrılmaz kod taşındı. Bu etkili bir şekilde bu bölümde sık kullanılan sayfaları dışında tutar.  
  
-   **EH kod ayrımı** -EH kod, olağanüstü yürütülmekte genellikle değiştirilebileceği için ayrı bir bölümde profil temelli iyileştirmeler özel durumlar yalnızca olağanüstü koşullara ortaya karar verirken.  
  
-   **Bellek iç bilgileri** -bir iç sık çağrıldıysa belirlenemediğinden, iç bilgileri genişletme daha iyi karar. Bir iç da taşır veya kopya blok boyutuna göre iyileştirilebilir.  
  
 IDE içinde gerçekleştirme el ile iyileştirme veya komut satırında daha fazla bilgi için bkz [profil temelli iyileştirme eklentisi](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Profil temelli iyileştirme eklentisi](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)  
  
 [El ile profil temelli iyileştirme için araçları](../../build/reference/tools-for-manual-profile-guided-optimization.md)  
  
 [Nasıl yapılır: birden çok PGO profilini tek profilde birleştirme](../../build/reference/how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ derleme araçları](../../build/reference/c-cpp-build-tools.md)
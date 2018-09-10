---
title: Visual C++ değişiklik geçmişi 2003-2015 | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2017
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- breaking changes [C++]
ms.assetid: b38385a9-a483-4de9-99a6-797488bc5110
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04e331da219f0c7a3996dda69d53769ea443b55e
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44319103"
---
# <a name="visual-c-change-history-2003---2015"></a>Visual C++ değişiklik geçmişi 2003-2015

Bu makalede, Visual Studio 2015 için Visual Studio 2003 ve bu makalede "yeni davranış" koşulları yukarıda bahsedilen tüm bozucu değişiklikleri açıklar veya Visual Studio 2015'e ve daha sonra "Şimdi" bakın. Koşulları "eski davranışı" ve "önce" Visual Studio 2013 ve önceki sürümleri için bkz.

Visual Studio 2017 hakkında daha fazla bilgi için bkz: [Visual Studio 2017'deki Visual c++ yenilikleri](../what-s-new-for-visual-cpp-in-visual-studio.md) ve [Visual Studio 2017'de Visual c++ uyumluluk geliştirmeleri](../cpp-conformance-improvements-2017.md). 

> [!NOTE]
> Visual Studio 2015 ve Visual Studio 2017 arasında yeni değişiklikler hiçbir ikili dosya vardır.

Visual Studio'nun yeni bir sürüme yükselttiğinizde, derleme ve/veya önceden derlenmiş ve düzgün çalışan kod çalışma zamanı hatalarıyla karşılaşabilirsiniz. Değişiklikleri yeni sürümde bu tür sorunlara neden olarak bilinir *bozucu değişiklikler*, ve bunlar tarafından C++ dil standardı, işlev imzaları veya bellekteki nesnelerin düzeni değişikliklerini genellikle gerekmesinden.

Algılanması ve tanılanması zor çalışma zamanı hatalarından kaçınmak için, derleyicinin farklı sürümleri kullanılarak derlenmiş ikili dosyalara hiçbir zaman statik bağlantı vermemenizi öneriyoruz. Ayrıca, bir EXE veya DLL projesini yükseltirken, bağlantı verdiği kitaplıkları da yükselttiğinizden emin olun. CRT (C çalışma zamanı) veya C++ Standart Kitaplığı (Standart C++ Kitaplığı) türleri kullanıyorsanız, bunları derleyicinin farklı sürümleri kullanılarak derlenmiş ikili (DLL'ler dahil) arasında geçirmeyin. Daha fazla bilgi için [olası hataları geçirme CRT nesnelerini DLL sınırlar boyunca](../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md).  
  
Ayrıca, COM arabirimi ya da POD projesi olmayan bir nesne için belirli bir düzeni temel alan kodları da asla yazmamanızı öneriyoruz. Bu tür bir kod yazarsanız, yükseltme sonrasında çalışmasını sağlamalısınız. Daha fazla bilgi için [ABI sınırlarında taşınabilirlik adresindeki](../cpp/portability-at-abi-boundaries-modern-cpp.md).  
  
Ayrıca, derleyici uyumluluğu yapılan sürekli geliştirmeler bazen nasıl derleyici mevcut kaynak kodunuzu anlar değiştirebilirsiniz. Bu durumda, derleme veya kodda, daha önce derlenmiş ve düzgün şekilde çalışması için olduğu görülüyor bile davranışsal farklılıklar sırasında yeni veya farklı hata karşılaşabilirsiniz. Bunlar bu belgede ele alınan olanlar gibi önemli değişiklikler değil olsa da, bu sorunları çözmek için kaynak kodu değişiklikleri gerekebilir:  
  
  
- [C çalışma zamanı (CRT) kitaplığı için bozucu değişiklikler](#BK_CRT)  
  
- [Standart C++ ve C++ Standart Kitaplığı bozucu değişiklikler](#BK_STL)  
  
- [MFC ve ATL bozucu değişiklikler](#BK_MFC)  
  
- [Eşzamanlılık Çalışma zamanı bozucu değişiklikler](#BK_ConcRT)  
  
## <a name="VC_2015"></a> Visual C++ 2015 uyumluluk değişiklikleri  
  
###  <a name="BK_CRT"></a> C çalışma zamanı kitaplığı (CRT)  
  
#### <a name="general-changes"></a>Genel değişiklikler  
  
- **İkili dosyaları yeniden düzenlenen** CRT kitaplığı yeniden düzenlenen bir iki farklı ikili dosyaları, bir evrensel standart işlevselliğinin büyük kısmını içeren CRT (ucrtbase) ve bir VC Çalışma zamanı derleyici ile ilgili içeren kitaplık (vcruntime) özel durum işleme ve yapı içleri gibi işlevleri. Varsayılan proje ayarlarını kullanıyorsanız, bağlayıcının yeni varsayılan kitaplıkları otomatik olarak kullanır bu yana sonra bu değişiklik, etkilemez. Projenin ayarlarsanız **bağlayıcı** özelliği **tüm varsayılan kitaplıkları Yoksay** için **Evet** veya kullanmakta olduğunuz `/NODEFAULTLIB` sonra komut satırında bağlayıcı seçeneği kitaplıkları listesini güncelleştirmeniz gerekir (içinde **ek bağımlılıklar** özelliği) yeni, işlenmiş kitaplıklarını eklemek. Eski CRT kitaplığı (LIBCMT.lib, lıbcmtd.lib, msvcrt.lib, msvcrtd.lib) eşdeğer UIMap'e yeniden işlenmiş kitaplıkları ile değiştirin. Her iki UIMap'e yeniden işlenmiş kitaplıklarının vardır (.lib) statik ve dinamik (.dll) ve sürümle (sonek) ve hata ayıklama sürümleri ("d" sonekiyle). Dinamik içeri aktarma kitaplığı ile bağlantı sürümlerde. İki UIMap'e yeniden işlenmiş kitaplıkları vardır ve evrensel CRT, özellikle ucrtbase.dll veya .lib, ucrtbased.dll dosyasını veya .lib ve VC Çalışma zamanı kitaplığı, libvcruntime.lib, vcruntime*sürüm*.dll ve libvcruntimed.lib vcruntimed*sürüm*.dll. *Sürüm* Visual Studio 2015 ve Visual Studio 2017 ', 140 değeri. Bkz: [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md).  
  
#### <a name="localeh"></a>\<Locale.h >  
  
- **localeconv** [localeconv](../c-runtime-library/reference/localeconv.md) bildirilen işlev locale.h şimdi çalışır doğru zaman [iş parçacığı başına yerel ayar](../parallel/multithreading-and-locales.md) etkinleştirilir. Kitaplığı önceki sürümlerinde, lconv verileri değil iş parçacığı yerel ayarı genel yerel ayar için bu işlevi döndürür.  
  
     İş parçacığı yerel ayarı kullanıyorsanız, kodunuzun lconv veri genel yerel ayar için döndürülen varsayar, görmek için localeconv kullanımını denetlemek ve uygun şekilde değiştirmek gerekir.  
  
#### <a name="mathh"></a>\<Math.h >  
  
- **C++ aşırı matematik kitaplığı işlevi** önceki sürümlerinde, \<math.h > bazı, tümü değil, C++ aşırı yüklemeleri matematik kitaplığı işlevi için tanımlı. \<cmath > overloads biri dahil etmek için gereken şekilde almak için diğer aşırı yüklemeler, tanımlanan \<cmath > Üstbilgi. Bu işlev aşırı yükleme çözümü yalnızca dahil kod ile ilgili sorunların LED'i \<math.h >. Şimdi tüm C++ aşırı yüklemeler kaldırılmış olan \<math.h > yalnızca artık mevcutsa \<cmath >.  
  
     Hataları gidermek için dahil \<cmath > öğesinden kaldırılan işlevlerin bildirimleri almak için \<math.h >. Aşağıdaki tabloda, taşınan işlevleri listeler.  
  
     Taşınan İşlevler:  
  
    - çift abs(double) ve kayan nokta abs(float)  
  
    - çift pow (double, int), float pow (float, float) pow (float, int), float pow (long double, long double)'uzun çift, pow (uzun çift int)'uzun çift  
  
    - Kayan ve noktası işlevleri acos, acosh, asin, asinh, atan, atanh, atan2, cbrt, copysign, cos, ceil kayan uzun çift sürümlerini cosh, erf, erfc, exp, exp2, expm1, fabs, fdim, floor, fma, fmax, fmin, fmod, frexp, hypot, ilogb, ldexp, lgamma, llrint, llround, günlük , log10, log1p, log2, lrint, lround, modf, nearbyint, nextafter, nexttoward, kalan, remquo, azdır, hepsini, scalbln, scalbn, sin, sinh, sqrt, Bronz, tanh, tgamma, trunc  
  
     Sahip kodu kullanan abs ile bir kayan nokta, yalnızca math.h üstbilgi türüne, kayan nokta sürümleri Hayır bile kayan ile çağrı işaret edecek şekilde bağımsız değişkeni artık kullanılabilir durumda, artık abs(int) için çözümler. Bu hata oluşturur:  
  
    ```Output  
    warning C4244: 'argument' : conversion from 'float' to 'int', possible loss of data  
    ```  
  
     Bu uyarıyı düzeltme çağrısı değiştirmektir `abs` ile bir kayan noktası sürümünü `abs`, gibi `fabs` çift bir bağımsız değişkeni veya `fabsf` bir float bağımsız değişkeni veya cmath üstbilgisi içerir ve kullanmaya devam `abs`.  
  
- **Kayan nokta uyumluluğu** IEEE 754 ve C11 Annex F belirtimlerine göre NaN'ler ve sonsuz gibi özel büyük girişlerdeki uyumluluğu artırmak için matematik kitaplığı çok fazla değişiklik yapılmıştır. Örneğin, genellikle kitaplığının önceki sürümlerinde hata olarak kabul, sessiz NaN girişleri artık hata olarak kabul edilir. Bkz: [IEEE 754 standart](http://grouper.ieee.org/groups/754) ve Annex F, [C11 standart](http://www.iso-9899.info/wiki/The_Standard).  
  
     Bu değişiklikler, derleme zamanı hatalarına neden olmaz, ancak programların standardına göre farklı şekilde ve daha doğru bir şekilde davranmasına neden olabilir.  
  
- **FLT_ROUNDS** içinde Visual Studio 2013, yuvarlama modunu çağıran fesetround tarafından çalışma zamanında, örneğin, yapılandırılabilir olduğundan, yanlış bir sabit ifadesine genişletilmiş FLT_ROUNDS makrosu. FLT_ROUNDS makrosu artık dinamik ve geçerli yuvarlama modu doğru olarak yansıtır.  
  
#### <a name="new-and-newh"></a>\<Yeni > ve \<new.h >  
  
- **Yeni ve Sil** kitaplığı önceki sürümlerinde, uygulama tanımlı new işleci ve delete işlevleri Çalışma Zamanı Kitaplığı'ndan (örneğin, msvcr120.dll) DLL dışarı aktarıldı. Bu işleç işlevleri artık statik olarak her zaman ikili dosyalarınıza, çalışma zamanı kitaplığı DLL'leri kullanırken bile bağlanır.  
  
     Bu yerel veya karma kod için bir değişiklik değil (`/clr`), ancak olarak derlenmiş kod [/CLR: pure](../build/reference/clr-common-language-runtime-compilation.md), bu, kodunuzu derlemek başarısız olmasına neden olabilir. Kod olarak derlerseniz `/clr:pure`, eklemeniz gerekebilir `#include <new>` veya `#include <new.h>` bu değişiklikten dolayı derleme hataları gidermek için. Unutmayın `/clr:pure` Visual Studio 2015'te kullanım dışıdır ve Visual Studio 2017'de desteklenmiyor. "Saf" olması gereken kod C# için unity'nin.  
  
#### <a name="processh"></a>\<Process.h >  
  
- **_beginthread ve _beginthreadex** [_beginthread](../c-runtime-library/reference/beginthread-beginthreadex.md) ve [_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md) işlevleri artık bir iş parçacığı yordamı süresince tanımlanır modülü başvurusu tutun iş parçacığı. Bu bir iş parçacığı çalıştırılıp tamamlandıktan kadar modülleri kaldırılmış olmadığını sağlamaya yardımcı olur.  
  
#### <a name="stdargh"></a>\<stdarg.h >  
  
- **va_start ve başvuru türleri** C++ kodunu derlerken [va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) artık kendisine geçirilen bağımsız değişken başvuru türünde değil. derleme zamanı sırasında doğrular. Başvuru türü bağımsız değişkenleri C++ standardı tarafından yasaktır.  
  
#### <a name="stdioh-and-conioh"></a>\<stdio.h > ve \<conio.h >  
  
- **Printf ve scanf ailesindeki işlevlerin artık tanımlanan satır içi.** Printf ve scanf işlevlerin tümü tanımlarını içine taşınan satır içi silinmiş \<stdio.h >, \<conio.h > ve diğer CRT üstbilgileri. Bu, bir bağlayıcı hatası (LNK2019, çözümlenmemiş dış sembol) götüren bir değişiklik uygun CRT üst bilgiler dahil olmak üzere bu işlevleri yerel olarak bildirilen tüm programları içindir. Mümkünse, CRT üstbilgileri dahil etmek için kodu güncelleştirmeniz gerekir (diğer bir deyişle, ekleme `#include <stdio.h>`) ve satır içi işlevler, ancak bu başlık dosyaları dahil etmek için kodunuzu değiştirmek istemiyorsanız, alternatif bir çözüm, bağlayıcı için bir ek kitaplık eklemek için Giriş, legacy_stdio_definitions.lib.  
  
     Bu kitaplık IDE'de bağlayıcı giriş eklemek için proje düğümü için bağlam menüsünü açın, **özellikleri**, ardından **proje özellikleri** iletişim kutusunda **bağlayıcı**ve düzenleme **bağlayıcı girişi** eklemek için `legacy_stdio_definitions.lib` ayırmanın-noktalı virgülle ayrılmış listesi.
     Bağlayıcı, projenizi Visual Studio 2015'den önceki bir sürümü ile derlenmiş olan statik kitaplıklar ile bağlanıyorsa, bir çözümlenmemiş dış sembol bildirebilir. Bu hatalar iç stdio tanımlarında _iob, _iob_func veya belirli stdio işlevleri biçiminde ilgili Imports başvurabilir\_*. Microsoft, bir projeyi yükselttiğinizde, tüm statik kitaplıklar ile C++ Derleyici en son sürümünü ve kitaplıkları derlemeniz önerir. Bir üçüncü taraf kitaplığı kitaplığıysa hangi kaynak kullanılamıyor için güncelleştirilmiş bir ikili üçüncü taraftan istek veya eski sürümü derleyici ve kitaplıkları ile derlemek için ayrı bir DLL içine bu kitaplığı kullanımını yalıtma .
  
    > [!WARNING]
    > Windows 8.1 SDK'sı veya önceki bağlanıyorsanız, bu çözümlenmemiş dış sembol hatalarla karşılaşabilirsiniz. Bu durumda, daha önce açıklandığı gibi giriş bağlayıcıya legacy_stdio_definitions.lib ekleyerek hata çözümlenmelidir.  
  
     Çözümlenmeyen sembol hataları gidermek için kullanmayı deneyebilirsiniz [dumpbin.exe](../build/reference/dumpbin-reference.md) ikili dosyada tanımlanan simgeleri incelemek için. Bir kitaplık tanımlanan semboller görüntülemek için şu komut satırını deneyin.  
  
    ```cpp  
    dumpbin.exe /LINKERMEMBER somelibrary.lib  
    ```  
  
- **Alınanlar ve _getws** [alır](../c-runtime-library/gets-getws.md) ve [_getws](../c-runtime-library/gets-getws.md) işlevleri kaldırıldı. Güvenli bir şekilde kullanılamadığı için C11 olarak standart C Kitaplığı gets işlevi kaldırıldı. _Getws işlevi eşdeğer bir Microsoft uzantısı olan alır ancak için çok geniş dizelerdir. Bu işlevlere alternatif, kullanımını göz önünde bulundurun [fgets](../c-runtime-library/reference/fgets-fgetws.md), [fgetws](../c-runtime-library/reference/fgets-fgetws.md), [gets_s](../c-runtime-library/reference/gets-s-getws-s.md), ve [_getws_s](../c-runtime-library/reference/gets-s-getws-s.md).  
  
- **_cgets ve _cgetws** [_cgets](../c-runtime-library/cgets-cgetws.md) ve [_cgetws](../c-runtime-library/cgets-cgetws.md) işlevleri kaldırıldı. Bu işlevlere alternatif, kullanımını göz önünde bulundurun [_cgets_s](../c-runtime-library/reference/cgets-s-cgetws-s.md) ve [_cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).  
  
- **Sonsuzluk ve NaN biçimlendirme** önceki sürümlerde, sonsuz ve NaN'ler MSVC özgü sentinel dizeler kümesi kullanılarak biçimlendirilir.  
  
    - Sonsuz: 1. #INF  
  
    - Sessiz bir NaN: 1. #QNAN  
  
    - Sinyal NaN: 1. #SNAN  
  
    - Belirsiz NaN: 1. #IND  
  
     Bunlardan birine bir işaretiyle önekli ve biraz daha farklı alan genişliğini ve duyarlık bağlı olarak biçimlendirilmiş olabilir (bazı durumlarda alışılmadık etkileri ile örn `printf("%.2f\n", INFINITY)` 1 yazdırır. #J #INF "2 basamaklı kesinliği için yuvarlanmasını çünkü"). C99 yeni gereksinimleri nasıl biçimlendirilmesi sonsuz ve NaN'ler olduğunuza kullanıma sunuldu. MSVC uygulama artık bu gereksinimlere uygun. Yeni dizeler aşağıdaki gibidir:  
  
    - Sonsuz: INF  
  
    - NaN quiet: nan  
  
    - NaN sinyal: nan(snan)  
  
    - Belirsiz NaN:nan(ind)  
  
     Bunlardan birine bir işaretiyle önekli. Sermaye biçim belirticisi ise dizeleri büyük harf (INF) yerine inf yazdırılır sonra (%f yerine %F) kullanılan olarak gereklidir.  
  
     [Scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) işlevleri gidiş dönüş printf ve scanf aracılığıyla bu dizeler olacak şekilde bu yeni dizelerini ayrıştırmak için değiştirilmiş olabilir.  
  
- **Kayan nokta biçimlendirme ve ayrıştırma** yeni kayan nokta biçimlendirme ve ayrıştırma algoritmaları kullanıma sunulmuştur doğruluğunu artırmak için. Bu değişiklik [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) ve [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) aileleri işlevleri yanı sıra, İşlevler, ister [strtod](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md).  
  
     Eski biçimlendirme algoritmalar yalnızca sınırlı sayıda basamak oluşturur, ardından kalan ondalık basamak sıfır ile doldurmanız. Gidiş dönüş geri özgün kayan noktalı değeri olacak dizeleri oluşturmak genellikle yeterince iyi budur ancak tam değeri (veya yapanın en yakın ondalık gösterim) istiyorsanız harika böyle değildir. Değeri temsil etmek için (veya belirtilen duyarlık doldurmak için) gibi çok sayıda basamak gerektiği gibi yeni biçimlendirme algoritmaları oluşturur. Geliştirme örnek olarak; sonuçları büyük ikinin yazdırırken göz önünde bulundurun:  
  
    ```cpp  
    printf("%.0f\n", pow(2.0, 80))  
    ```  
  
    ```Output  
        Old:  1208925819614629200000000    New:  1208925819614629174706176  
    ```  
  
     Eski ayrıştırma algoritmaları, Giriş dizesinin en çok 17 önemli rakamları dikkate alır ve kalan rakamları atar. Bu dize tarafından temsil edilen değeri çok yakın bir yaklaşığını oluşturmak yeterli ve genellikle çok yakın doğru yuvarlatılmış sonucu sonucudur. Yeni uygulama, tüm mevcut basamak göz önünde bulundurur ve doğru yuvarlak bir sonuç tüm girişlerin (uzunluğu en fazla 768 basamak). Ayrıca, bu işlevler, artık (fesetround denetlenebilir) yuvarlama modu uyar.  Bu potansiyel olarak yeni, bu işlevler, farklı sonuçlar çıkış çünkü davranışını değiştirin. Yeni sonucu her zaman daha fazla olan eski sonuçları daha doğru.  
  
- **Onaltılık ve sonsuzluk/NaN kayan noktası ayrıştırma** algoritmaları ayrıştırma kayan nokta onaltılık kayan nokta dizeleri (örneğin %a ve %A printf biçim belirticisi tarafından üretilen) artık ayrıştırır ve tüm sonsuzluk ve NaN dizelerde tarafından oluşturulan `printf` , yukarıda açıklanan şekilde çalışır.  
  
- **%A ve %a sıfır doldurma** %a ve %A biçim belirticileri kayan biçimlendirme bir onaltılık Mantis ve ikili nokta sayısı. Önceki sürümlerde, `printf` işlevleri yanlış sıfır paneli dizeleri gerekir. Örneğin, `printf("%07.0a\n", 1.0)` nerede bunu yazdırılacağını 0x01p + 0 00x1p + 0, yazdırır. Bu düzeltilmiştir.  
  
- **%A ve %a duyarlık** %A ve %a biçim belirleyicilerinin varsayılan duyarlık Kitaplığı'nın önceki sürümlerinde 6 oluştu. Varsayılan duyarlık C standardı ile uyum 13 sunulmuştur.  
  
     Bu çalışma zamanı davranışına çıktısı bir biçim dizesi %A veya % kullanan herhangi bir işlev olarak farklıdır bir. Eski davranışa %A belirticisi kullanılarak çıkış "1.1A2B3Cp + 111" olabilir. Çıkış için aynı değeri "1.1A2B3C4D5E6F7p + 111" sunulmuştur. Eski davranışı sağlamak için örneğin, %.6A duyarlık belirtebilirsiniz. Bkz: [duyarlık belirtimleri](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md#precision).  
  
- **%F belirticisi** %F biçimi/dönüştürme belirleyicisine artık desteklenmektedir. Sonsuz ve NaN'ler, büyük harfler kullanılarak biçimlendirilen dışında %f biçim belirticisi işlevsel olarak eşdeğerdir.  
  
     Önceki sürümlerde, F ve N uzunluk değiştirici ayrıştırmak için kullanılan uygulama. Bu davranış tarihli geri segmentli adres alanları yaşını: Bu uzunluğu değiştiriciler Fp % veya %Ns olduğu gibi uzak ve işaretçileri, yakın sırasıyla göstermek için kullanılan. Bu davranış kaldırıldı. %F karşılaşılırsa, artık %F biçim belirtici olarak kabul edilir; %N karşılaşılırsa, artık geçersiz bir parametre kabul edilir.  
  
- **Biçimlendirme üs** %e ve nokta numarası bir ondalık Mantis ve üs olarak kayan %E biçim belirticileri biçimi. %G ve %G biçim belirticileri ayrıca bazı durumlarda bu formda sayıları biçimlendirmek. Önceki sürümlerde, CRT her zaman üç basamaklı üsler dizelerle oluşturur. Örneğin, `printf("%e\n", 1.0)` 1.000000e + 000 yazdırır. Bu yanlış: C üs yalnızca bir veya iki basamak kullanarak gösterilebilir ise, ardından yalnızca iki basamağı yazdırılması olduğunu gerektirir.  
  
     Visual Studio 2005'te genel uyumluluğu anahtarı eklendi: [_set_output_format](../c-runtime-library/set-output-format.md). Bir program uyumlu üs yazdırmayı etkinleştirmek için bağımsız değişken _two_dıgıt_exponent ile bu işlevi çağırabilirsiniz. Standartlara uyan üs yazdırma modu için varsayılan davranışı değiştirildi.  
  
- **Biçim dizesi doğrulama** önceki sürümlerde printf ve scanf işlevleri sessizce bazen olağan dışı etkileri olan birçok geçersiz biçim dizesi kabul eder. Örneğin, % hlhlhld %d kabul edilir. Tüm geçersiz biçim dizeleri, artık geçersiz parametre olarak kabul edilir.  
  
- **fopen modu dize doğrulama**  
  
     Önceki sürümlerde, işlevlerin fopen ailesi sessizce bazı geçersiz mod dizeleri (ör r + b +) kabul edildi. Geçersiz mod dizeleri artık algılandı ve geçersiz parametre olarak kabul edilir.  
  
- **_O_U8TEXT modu**  
  
     [_Setmode](../c-runtime-library/reference/setmode.md) işlevi artık doğru şekilde rapor modu akışları in_O_U8TEXT modunda açılmış için. Kitaplığı önceki sürümlerinde, bu tür akışlar içinde _O_WTEXT açılmasını olarak rapor.  
  
     Kodunuzu burada UTF-8 kodlamasını, akışları _O_WTEXT modunu yorumlar durumunda bir değişiklik budur. Uygulamanızı UTF_8 desteklemiyorsa bu giderek ortak kodlaması için destek eklemeyi göz önünde bulundurun.  
  
- **snprintf ve vsnprintf** [snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) ve [vsnprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) işlevleri artık uygulanır. Eski kod genellikle tanımları makrosu bu işlevlerin sürümleri, CRT kitaplığı tarafından uygulanan değil, ancak bunlar artık daha yeni sürümlerde gereklidir çünkü sağlanır. Varsa [snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) veya [vsnprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) eklemeden önce bir makro tanımlanan \<stdio.h >, artık derleme makro tanımlandığı belirten bir hata ile başarısız olur.  
  
     Normalde, bu sorun için düzeltme tüm bildirimleri silmektir `snprintf` veya `vsnprintf` kullanıcı kodunda.  
  
- **tmpnam oluşturur kullanılabilir dosya adları** önceki sürümlerinde, `tmpnam` ve `tmpnam_s` işlevleri (örneğin, \sd3c.) sürücüsünün kök dosya adları oluşturulur. Bu işlevler, geçici dizinde artık kullanılabilir dosya adı yolları oluşturur.  
  
- **Dosya kapsülleme** önceki sürümlerinde, dosya türü tamamen tanımlandığı \<stdio.h >, bir dosyaya erişmek ve kendi iç yapıları değiştirmek, kullanıcı kodu mümkündü. Stdio kitaplığı, uygulama ayrıntılarını gizlemek için değiştirildi. Bunun bir parçası olarak tanımlanan dosya \<stdio.h > şimdi donuk bir türdür ve üyelerini CRT dışında erişilemez.  
  
- **_outp ve _inp** işlevleri [_outp](../c-runtime-library/outp-outpw-outpd.md), [_outpw](../c-runtime-library/outp-outpw-outpd.md), [_outpd](../c-runtime-library/outp-outpw-outpd.md), [_inp](../c-runtime-library/inp-inpw-inpd.md), [_inpw](../c-runtime-library/inp-inpw-inpd.md), ve [_inpd](../c-runtime-library/inp-inpw-inpd.md) kaldırıldı.  
  
#### <a name="stdlibh-malloch-and-sysstath"></a>\<stdlib.h >, \<malloc.h >, ve \<sys/stat.h >  
  
- **strtof ve wcstof** `strtof` ve `wcstof` işlevleri başarısız değeri gösterilebilir bir kayan noktalı olarak bulunmadığında errno ERANGE için ayarlanacak. Bu düzeltilmiştir. (Bu hata, bu iki işlev için; özel Not `strtod`, `wcstod`, `strtold`, ve `wcstold` işlevleri etkilenmez.) Yeni değişiklik bir çalışma zamanı budur.  
  
- **Ayırma işlevlerinin hizalı** önceki sürümlerinde, hizalanmış ayırma işlevleri (`_aligned_malloc`, `_aligned_offset_malloc`, vs.) sessiz bir hizalama 0 olan bir blok isteklerini kabul eder. İstenen hizalama ikinin hangi sıfıra eşit olmalıdır. Bu sabit ve istenen bir hizalama 0 artık geçersiz bir parametre kabul edilir. Yeni değişiklik bir çalışma zamanı budur.  
  
- **Yığın işlevleri** `_heapadd`, `_heapset`, ve `_heapused` işlevleri kaldırıldı. Bu işlevler, CRT Windows yığınını kullanmak üzere güncellendiğinden bu yana işlevsiz olmuştur.  
  
- **smallheap** `smalheap` bağlantı seçeneği kaldırılmıştır. Bkz: [bağlantı seçenekleri](../c-runtime-library/link-options.md).  
  
#### <a name="stringh"></a>\<String.h >  
  
- **wcstok** imzası `wcstok` işlevi, hangi C Standart tarafından gerekli eşleşecek şekilde değiştirildi. Kitaplığı önceki sürümlerinde, bu işlev imzası şöyleydi:  
  
    ```cpp  
    wchar_t* wcstok(wchar_t*, wchar_t const*)  
    ```  
  
     Bir iç, iş parçacığı başına bağlamı bitti olarak çağrılar arasında durumunu izlemek için kullanılan `strtok`. İşlev imzası sunuyor `wchar_t* wcstok(wchar_t*, wchar_t const*, wchar_t**)`ve üçüncü bir bağımsız değişken olarak işleve bağlamı geçirmek çağırıcı gerektirir.  
  
     Yeni bir `_wcstok` işlevi taşıma kolaylaştırmak için eski imza ile eklenmiştir. C++ kodu derlemiyorsanız olduğunda da bir satır içi aşırı yüklemesini `wcstok` eski imzaya sahip. Bu aşırı yüklemesi kullanım dışı olarak bildirildi. C kodu define_CRT_NON_CONFORMING_WCSTOK neden olabilecek `_wcstok` yerine kullanılacak `wcstok`.  
  
#### <a name="timeh"></a>\<TIME.h >  
  
- **Saat** önceki sürümlerinde, [saat](../c-runtime-library/reference/clock.md) işlevi uygulanan Windows API kullanarak [GetSystemTimeAsFileTime](https://msdn.microsoft.com/library/windows/desktop/ms724397.aspx). Clock işlevi bu uygulama ile Sistem saati hassas ve böylece mutlaka monoton değildi. Clock işlevi açısından reimplemented [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904.aspx) ve monoton sunulmuştur.  
  
- **fstat ve _utime** önceki sürümlerinde, [_stat](../c-runtime-library/reference/stat-functions.md), [fstat](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md), ve [_utime](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) işlevleri işlemek gün ışığından yararlanma saatine yanlış. Gün ışığından yararlanma saat içinde değilmiş gibi Visual Studio 2013'ten önce bu işlevlerin tümü yanlış Standart Saati kez ayarlanmış.  
  
     Visual Studio 2013'te, sorun giderilmiştir **_stat** ailesi işlevleri, ancak benzer sorunlar **fstat** ve **_utime** işlev aileleri düzeltilemedi. Bu sorunların tutarsızlık nedeniyle işlevler arasında gerektiriyordu. **Fstat** ve **_utime** aileleri işlevlerin artık düzeltilmiştir bu işlevlerin tümü artık gün ışığından yararlanma saatine doğru ve tutarlı bir şekilde işlemek için.  
  
- **asctime** önceki sürümlerinde, [asctime](../c-runtime-library/reference/asctime-wasctime.md) işlevi paneli tek basamaklı gün önünde sıfır ile örneğin: Cuma Haz 06 08:00:00 2014. Böyle gün önde gelen bir boşluk ile örn Haz Cuma 6 azsa gerektiğini belirtilmesini gerektiriyor 08:00:00 2014. Bu düzeltilmiştir.  
  
- **strftime ve wcsftime** `strftime` ve `wcsftime` işlevleri artık %C desteği, %D, %e, %F, g %, %G, %s, %n, %r, %R, %t, %T, %u ve %V biçim belirleyiciler. Ayrıca, E ve O değiştiriciler yoksayıldı ancak bu ayrıştırılır.  
  
     %C biçim belirticisi, geçerli yerel ayarı için bir "uygun tarih ve Saat Gösterimi" üretme olarak belirtilir. C yerel ayarında, bu gösterim %a %b %e %Y %T ile aynı olması gerekir. Bu aynı asctime tarafından oluşturulduğundan biçimidir. Önceki sürümlerde, DD/MM/YY ss gösterimi kullanarak %c biçim tanımlayıcısı yanlış biçimlendirilmiş. Bu düzeltilmiştir.  
  
- **timespec ve TIME_UTC** \<TIME.h > Üstbilgi artık tanımlar `timespec` türü ve `timespec_get` işlevden C11 standart. Ayrıca, ile kullanılmak üzere TIME_UTC makrosu `timespec_get` işlev, artık tanımlanır. Çakışan bir tanım aşağıdakilerden herhangi biri için olan kod için bir değişiklik budur.  
  
- **CLOCKS_PER_SEC** CLOCKS_PER_SEC makro genişler artık bir tamsayı türü `clock_t`gerektirdiği gibi C dili tarafından.  
  
####  <a name="BK_STL"></a> C++ Standart Kitaplığı  
Yeni iyileştirmeleri ve hata ayıklama denetimlerini etkinleştirmek için, C++ Standart Kitaplığı'nın Visual Studio uygulaması bir sürümden sonraki bir sürüme ikili uyumluluğu kasıtlı olarak bozar. Bu nedenle, C++ Standart Kitaplığı kullanıldığında, farklı sürümlerin kullanımıyla derlenmiş nesne dosyaları ve statik kitaplıklar tek bir ikili dosya (EXE veya DLL) halinde karma yapılabilir ve C++ Standart Kitaplığı nesneleri, farklı sürümler kullanılarak derlenmiş ikili dosyalar arasında geçirilemez. Bu tür karmalar, _MSC_VER uyuşmazlıklarıyla ilgili bağlayıcı hataları verir. (_MSC_VER, derleyicinin ana sürümünü içeren makrodur olan — Örneğin, Visual Studio 2013 için 1800.) Bu denetim DLL karmasını algılayamaz ve Visual Studio 2008 veya önceki bir sürümü içeren karmasını algılayamaz.  
  
- **C++ Standart Kitaplığı ekleme kodu dosyalarının** C++ Standart Kitaplığı üst bilgileri Ekle yapısında bazı değişiklikler yapılmıştır. C++ Standart Kitaplığı üst bilgileri birbirlerine belirtilmeyen şekillerde dahil izin verilir. Genel olarak, kod yazma, böylece dikkatli bir şekilde tüm C++ standardına göre gerekir ve hangi C++ Standart Kitaplığı üstbilgi hangi, diğer bir C++ Standart Kitaplığı üst bilgilerini içeren üzerinde içermez üst bilgi içerir. Bu kod taşınabilir sürümleri ve platformlar arasında sağlar. Visual Studio 2015'te en az iki üstbilgi değişiklikler, kullanıcı kodu etkiler. İlk olarak, \<dizesi > artık içerir \<yineleyici >. İkinci olarak, \<tanımlama grubu > artık bildirir `std::array` tüm dahil olmak üzere olmadan \<dizi >, aşağıdaki kod yapıları birleşimi kodlardan bozabilir: kodunuzu "array" adlı bir değişken ve using yönergesi sahip " ' using namespace std; ", ve C++ Standart Kitaplığı üst bilgisi içerir (gibi \<işlevsel >) içeren \<demet >, şimdi bildirir `std::array`.  
  
- **steady_clock** \<chrono > uygulaması [steady_clock](../standard-library/steady-clock-struct.md) steadiness ve monotonicity C++ Standart gereksinimlerini karşılayacak şekilde değişti. `steady_clock` artık üzerinde temel [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904.aspx) ve `high_resolution_clock` için bir typedef sunulmuştur `steady_clock`. Sonuç olarak, Visual Studio'da `steady_clock::time_point` için bir typedef sunulmuştur `chrono::time_point<steady_clock>`; ancak bu zorunlu diğer uygulamaları için geçerli değildir.  
  
- **ayırıcılar ve const** artık her iki tarafında const bağımsız değişkenleri kabul etmek için eşitlik/eşitsizlik karşılaştırma ayırıcı isteriz.  Ayırıcılar, bu işleçler gibi tanımlarsanız:  
  
    ```cpp  
    bool operator==(const MyAlloc& other)  
    ```  
  
     Bunlar bunları const üye olarak bildirmek için güncelleştirmeniz gerekir.  
  
    ```cpp  
    bool operator==(const MyAlloc& other) const  
    ```  
  
- **const öğeleri** C++ Standart const öğelerin kapsayıcıları her zaman Yasak içeriyor (vektör gibi\<const T > veya\<const T >). Visual Studio 2013 veya önceki gibi kapsayıcılar kabul edildi. Geçerli sürümde bu tür kapsayıcıları derleme başarısız.  
  
- **Std::Allocator:: serbest** Visual Studio 2013 ve önceki sürümlerde `std::allocator::deallocate(p, n)` geçirilen bağımsız değişken yok sayıldı *n*.  C++ Standart her zaman zorunlu *n* çağırmayı ilk bağımsız değişkeni ayırmak gibi döndürülen geçirilen değere eşit olması *p*. Ancak, geçerli sürümde, değerini *n* Denetlenmekte. Bağımsız değişkenler için geçen kod *n* ne standart çalışma zamanında kilitlenebilir gerektirir öğesinden farklı.  
  
- **hash_map ve hash_set** standart üst bilgi dosyaları hash_map hash_set Visual Studio 2015'te kullanım dışıdır ve gelecek sürümde kaldırılacak. Unordered_map ve unordered_set kullanın.  
  
- **karşılaştırıcıların ve operator()** ilişkilendirilebilir kapsayıcılar ( \<harita > Aile) artık const çağrılabilir işlevi çağrı işleçleri olan kendi karşılaştırıcıların gerektirir. Bir karşılaştırıcı sınıf bildiriminde artık aşağıdaki kodu derlemek başarısız olur:  
  
    ```cpp  
    bool operator()(const X& a, const X& b)  
    ```  
  
     Bu hatayı gidermek için işlev bildirimi için değiştirin:  
  
    ```cpp  
    bool operator()(const X& a, const X& b) const  
    ```  
  
- **türü nitelikler** C++ taslak standardı'nın önceki bir sürümünden tür özellikleri için eski adları kaldırıldı. Bu, C ++ 11'de değiştirilmiş ve C ++ 11 değerleri Visual Studio 2015'te şekilde güncelleştirildi. Aşağıdaki tablo, eski ve yeni adları gösterir.  
  
    |Eski adı|Yeni ad|  
    |--------------|--------------|  
    |add_reference|add_lvalue_reference|  
    |has_default_constructor|is_default_constructible|  
    |has_copy_constructor|is_copy_constructible|  
    |has_move_constructor|is_move_constructible|  
    |has_nothrow_constructor|is_nothrow_default_constructible|  
    |has_nothrow_default_constructor|is_nothrow_default_constructible|  
    |has_nothrow_copy|is_nothrow_copy_constructible|  
    |has_nothrow_copy_constructor|is_nothrow_copy_constructible|  
    |has_nothrow_move_constructor|is_nothrow_move_constructible|  
    |has_nothrow_assign|is_nothrow_copy_assignable|  
    |has_nothrow_copy_assign|is_nothrow_copy_assignable|  
    |has_nothrow_move_assign|is_nothrow_move_assignable|  
    |has_trivial_constructor|is_trivially_default_constructible|  
    |has_trivial_default_constructor|is_trivially_default_constructible|  
    |has_trivial_copy|is_trivially_copy_constructible|  
    |has_trivial_move_constructor|is_trivially_move_constructible|  
    |has_trivial_assign|is_trivially_copy_assignable|  
    |has_trivial_move_assign|is_trivially_move_assignable|  
    |has_trivial_destructor|is_trivially_destructible|  
  
- **Launch::ANY ve launch::sync ilkeleri** kullanıldı `launch::any` ve `launch::sync` ilkeleri kaldırıldı. Bunun yerine, için `launch::any`, kullanın `launch:async | launch:deferred`. `launch::sync` için `launch::deferred`'i kullanın. Bkz: [launch numaralandırması](../standard-library/future-enums.md#launch).  
  
####  <a name="BK_MFC"></a> MFC ve ATL  
  
- **Microsoft Foundation Classes (MFC)** artık Visual Studio'nun "Tipik" bir yüklemede nedeniyle büyük boyutuna dahildir. MFC yüklemek için seçin **özel** seçeneği Visual Studio 2015 kurulumunda yüklediniz. Visual Studio 2015'i zaten varsa, MFC yeniden çalıştırarak yükleyebilirsiniz **Visual Studio** seçerek, Kurulum **özel** seçeneğini yüklemek ve seçerek **Microsoft Foundation Sınıflar**. Yeniden çalıştırabileceğiniz **Visual Studio** Kurulumu'nu **Denetim Masası**, **programlar ve Özellikler**, veya yükleme medyasından.  
  
     Visual C++ Yeniden Dağıtılabilir Paketi'nde bu kitaplık halen yer almaktadır.  
  
####  <a name="BK_ConcRT"></a> Eşzamanlılık Çalışma zamanı  
  
- **Makro Windows.h concurrency::Context::Yield ile çakışan gelen yield** eşzamanlılık daha önce kullanılan çalışma zamanı `#undef` Windows.h h ve tanımlanmışYieldmakrosuarasındakiçakışmalarıönlemeYieldmakrotanımınıkaldırmaya`concurrency::Context::Yield`işlevi. Bu `#undef` kaldırıldı ve bir yeni çakışmayan eşdeğer API çağrısı [concurrency::Context::YieldExecution](../parallel/concrt/reference/context-class.md#yieldexecution) eklendi. Yield ile çakışıyor geçici olarak çözmek için ya da çağırmak için kodunuzu güncelleştirebilirsiniz `YieldExecution` işlevini veya çevreleyen `Yield` siteleri çağrıda parantezli işlev adı, aşağıdaki örnekte olduğu gibi:  
  
    ```cpp  
    (concurrency::Context::Yield)();  
    ```  
  
## <a name="compiler-conformance-improvements-in-visual-studio-2015"></a>Visual Studio 2015'te derleyici uyumluluk geliştirmeleri  

Kod, önceki sürümlerinden yükselttiğinizde, Visual Studio 2015'te yapılan uyumluluk geliştirmeleri nedeniyle derleyici hataları da karşılaşabilirsiniz. Bu geliştirmeler, Visual Studio'nun önceki sürümlerinden ikili uyumluluğu bölmediğinizden, ancak burada Hiçbiri önce yayılan derleyici hataları oluşturabilir. Daha fazla bilgi için [Visual C++ neler yeni 2003 ile 2015 arasındaki](../porting/visual-cpp-what-s-new-2003-through-2015.md).  
  
Visual Studio 2015'te nasıl derleyici mevcut kaynak kodunuzu anlar derleyici uyumluluğu yapılan sürekli geliştirmeler bazen değiştirebilirsiniz. Bu durumda, derleme veya kodda, daha önce derlenmiş ve düzgün şekilde çalışması için olduğu görülüyor bile davranışsal farklılıklar sırasında yeni veya farklı hata karşılaşabilirsiniz.  
  
Neyse ki, bu farklılıkları çok az kayıpla veya hiç kaynak kodunuzun çoğunu etkisi ve bu farklar ele almak için kaynak kodu veya başka değişiklikler gerektiğinde, düzeltmeleri genellikle küçük ve rahatça. Daha önce kabul edilebilir kaynak kodunun değiştirilmesi gerekebilir birçok örnekler ekledik *(önce)* ve bunları düzeltmeye yönelik düzeltmeler *(sonra)*.  
  
Bu farklılıklar, kaynak kodu veya diğer derleme yapıtlarının etkileyebilir olsa da, bunların güncelleştirmelerini Visual Studio sürümleri arasında ikili uyumluluğu etkilemez. Değişiklik, daha ciddi bir tür *değişiklik* ikili uyumluluğu etkileyebilir, ancak ikili uyumluluğu sonları bu tür yalnızca temel Visual Studio sürümleri arasında oluşur. Örneğin, Visual Studio 2013 ve Visual Studio 2015 arasında. Visual Studio 2015 ve Visual Studio 2013 arasında gerçekleşen bozucu değişiklikler hakkında daha fazla bilgi için bkz: [Visual Studio 2015 uyumluluk değişiklikleri](#VC_2015).  
  
- [Visual Studio 2015'te uyumluluk geliştirmeleri](#VS_RTM)  
  
- [Güncelleştirme 1'de uyumluluk geliştirmeleri](#VS_Update1)  
  
- [Güncelleştirme 2'de uyumluluk geliştirmeleri](#VS_Update2)  
  
- [Güncelleştirme 3, uyumluluk geliştirmeleri](#VS_Update3)  
  
###  <a name="VS_RTM"></a> Visual Studio 2015'te uyumluluk geliştirmeleri  
  
- /ZC:forScope-seçeneği  
  
     Derleyici seçeneği `/Zc:forScope-` kullanım dışıdır ve gelecek sürümde kaldırılacak.  
  
    ```cpp  
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release  
    ```  
  
     Seçeneği, genellikle, standardına göre kapsam dışına sahiplikten noktadan sonra değişkenleri kullanır döngü standart olmayan koda izin ver için kullanıldı. İle derlerken yalnızca gerekli `/Za` beri seçeneği olmadan `/Za`kullanarak bir döngünün sonunu her zaman izin verilir sonra Döngü değişkeninin. (Örneğin, kodunuz için taşınabilir diğer derleyicileri için tasarlanmamıştır) standartları uyumluluğu hakkında İlgilenmiyor, devre dışı `/Za` seçeneği (veya **dil uzantılarını devre dışı** özelliğini **yok** ). Taşınabilir, standartlara uyumlu kod yazma hakkında dikkatli olun, böylece bir noktaya döngü dışında bir tür değişken bildirimi taşıyarak standardına uygun kodunuzu yeniden yazmalıdır.  
  
    ```cpp  
    // C2065 expected  
    int main() {  
        // Uncomment the following line to resolve.  
        // int i;  
        for (int i = 0; i < 1; i++);  
        i = 20;   // i has already gone out of scope under /Za  
    }  
    ```  
  
- `/Zg` derleyici seçeneği  
  
     `/Zg` Derleyici seçeneği (işlev prototipleri oluşturma) kullanılabilir artık. Bu derleyici seçeneği önceden kullanım dışı bırakıldı.  
  
- Artık birim testleri C + ile çalıştırabileceğiniz +/ CLI ile mstest.exe komut satırı üzerinden. Bunun yerine, vstest.console.exe kullanın. Bkz: [VSTest.Console.exe komut satırı seçenekleri](/devops-test-docs/test/vstest-console-exe-command-line-options).  
  
- **mutable anahtar sözcüğü**  
  
     **Değişebilir** depolama sınıfı tanımlayıcısı burada daha önce derlenmiş hatasız yerde artık verilir. Şimdi, derleyici hatası C2071 verir (depolama sınıfı). Standardına göre **değişebilir** belirticisi yalnızca sınıf veri üyeleri adlarına uygulanan ve const veya statik bildirilen adlarına uygulanan ve üyeleri başvurmak için uygulanamaz.  
  
     Örneğin, aşağıdaki kodu düşünün:  
  
    ```cpp  
    struct S   
    {  
        mutable int &r;  
    };  
    ```  
  
     Bu derleyicinin önceki sürümler kabul, ancak şimdi derleyici, aşağıdaki hatayı verir:  
  
    ```Output  
    error C2071: 'S::r': illegal storage class  
    ```  
  
     Hatayı düzeltmek için yedekli kaldırmanız **değişebilir** anahtar sözcüğü.  
  
- **char_16_t ve char32_t**  
  
     Bundan böyle kullanabileceğinizi `char16_t` veya `char32_t` adlarda olarak bir **typedef**, bu tür artık yerleşik kabul edilir. Kullanıcılar ve tanımlamak için kitaplık yazarları için ortak `char16_t` ve `char32_t` diğer adlarını olarak `uint16_t` ve `uint32_t`sırasıyla.  
  
    ```cpp  
    #include <cstdint>  
  
    typedef uint16_t char16_t; //C2628  
    typedef uint32_t char32_t; //C2628  
  
    int main(int argc, char* argv[])  
    {  
        uint16_t x = 1; uint32_t y = 2;  
        char16_t a = x;  
        char32_t b = y;  
        return 0;  
    }  
    ```  
  
     Kodunuzu güncelleştirmek için kaldırma **typedef** bildirimleri ve bu adları birbiriyle çakışır herhangi bir tanımlayıcıya yeniden adlandırın.  
  
- **Türü olmayan şablon parametreleri**  
  
     Açık şablon bağımsız değişkenleri sağlayın, tür olmayan şablon parametreleri içeren belirli kod artık doğru tür uyumluluğu için denetlenir. Visual Studio'nun önceki sürümlerinde hatasız derlenir. Örneğin, aşağıdaki kodu.  
  
    ```cpp  
    struct S1  
    {  
        void f(int);  
        void f(int, int);  
    };  
  
    struct S2  
    {  
        template <class C, void (C::*Function)(int) const> void f() {}  
    };  
  
    void f()  
    {  
        S2 s2;  
        s2.f<S1, &S1::f>();  
    }  
    ```  
  
     Geçerli derleyici şablon parametre türü, şablon bağımsız değişkeni eşleşmediği için doğru bir hata verir. (bir const üye işaretçisi parametredir, ancak const olmayan işlev f):  
  
    ```Output  
    error C2893: Failed to specialize function template 'void S2::f(void)'note: With the following template arguments:note: 'C=S1'note: 'Function=S1::f'  
    ```  
  
     Kodunuzda bu hatayı gidermek için kullandığınız şablon bağımsız değişken türünü bildirilen şablon parametresinin türünü eşleştiğinden emin olun.  
  
- **__declspec(align)**  
  
     Derleyici artık kabul `__declspec(align)` işlevleri. Bu her zaman yoksayıldı, ancak artık, bir derleyici hatası oluşturur.  
  
    ```cpp  
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations  
    ```  
  
     Bu sorunu gidermek için kaldırın `__declspec(align)` gelen işlev bildirimi. Etkiye sahip olduğundan, kaldırarak her şeyi değiştirmez.  
  
- **Özel durum işleme**  
  
     Birkaç özel durum işleme için değişiklik vardır. İlk olarak, özel durum nesneleri kopyalanabilir ya da taşınabilir olması gerekir. Aşağıdaki kod, Visual Studio 2013'te derlenmiş, ancak Visual Studio 2015'te derleme yapmaz:  
  
    ```cpp  
    struct S  
    {  
    public:  
        S();  
    private:  
        S(const S &);  
    };  
  
    int main()  
    {  
        throw S(); // error  
    }  
    ```  
  
     Nesne kopyalanamaz, bir özel durum işleme normal kursun olduğu sürece bu nedenle, kopya oluşturucu özel sorunudur. Kopya Oluşturucu bildirildiğinde da aynı şekilde geçerlidir **açık**.  
  
    ```cpp  
    struct S  
    {  
        S();  
        explicit S(const S &);  
    };  
  
    int main()  
    {  
        throw S(); // error  
    }  
    ```  
  
     Kodunuzu güncelleştirmek için özel durum nesnesi için kopya Oluşturucu olduğundan emin olun **genel** ve işaretlenmemiş **açık**.  
  
     Değere göre bir özel durum yakalama, özel durum nesnesi kopyalanabilir olmasını gerektirir. Aşağıdaki kod, Visual Studio 2013'te derlenmiş, ancak Visual Studio 2015'te derleme yapmaz:  
  
    ```cpp  
    struct B  
    {  
    public:  
        B();  
    private:  
        B(const B &);  
    };  
  
    struct D : public B {};  
  
    int main()  
    {  
        try  
        {  
        }  
        catch (D d) // error  
        {  
        }  
    }  
    ```  
  
     Parametre türü değiştirerek bu sorunu düzeltebilirsiniz **catch** bir başvuru.  
  
    ```cpp  
    catch (D& d)  
    {  
    }  
    ```  
  
- **Makroları tarafından izlenen bir dize değişmez değerleri**  
  
     Derleyici kullanıcı tanımlı değişmez değerler artık desteklemektedir. Müdahalede bulunan tüm boşluk olmadan makroları ardından dize değişmez değerleri, hatalar veya beklenmeyen sonuçlar üretebilir kullanıcı tanımlı değişmez değer olarak, sonuç olarak yorumlanır. Örneğin, aşağıdaki kod önceki derleyicilerde başarıyla derlenir:  
  
    ```cpp  
    #define _x "there"  
    char* func() {  
        return "hello"_x;  
    }  
    int main()  
    {  
        char * p = func();  
        return 0;  
    }  
    ```  
  
     Derleyici bunun bir dize olarak değişmez değer olarak "hello"var"genişletilir, bir makro tarafından izlenen" yorumlanan ve ardından iki dize değişmez değerleri birine art arda eklenmiş. Visual Studio 2015'te derleyici kullanıcı tanımlı değişmez değer olarak, bu yorumlar, ancak tanımlı hiçbir eşleşen kullanıcı tanımlı değişmez değer _x olduğundan, bir hata verir.  
  
    ```Output  
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found  
    note: Did you forget a space between the string literal and the prefix of the following string literal?  
    ```  
  
     Bu sorunu gidermek için dize sabit değeri ve makro arasına boşluk ekleyin.  
  
- **Bitişik dize değişmez değerleri**  
  
     Benzer şekilde önceki dize ayrıştırma, ilgili değişiklikleri nedeniyle için herhangi bir boşluk olmadan (ya da geniş veya dar karakter dize sabit değerleri) bitişik dize değişmez değerleri tek bir birleştirilmiş dizeyi Visaul C++'ın önceki sürümlerinde yorumlanan. Visual Studio 2015'te artık iki dizenin arasında boşluk eklemeniz gerekir. Örneğin, aşağıdaki kod değiştirilmelidir:  
  
    ```cpp  
    char * str = "abc""def";  
    ```  
  
     İki dizenin aralığındaki bir alan eklemeniz yeterlidir.  
  
    ```cpp  
    char * str = "abc" "def";  
    ```  
  
- **Yerleştirme yeni ve Sil**  
  
     İçin bir değişiklik yapılmadığını **Sil** , C ++ 14 standart ile uyumluluk duruma getirmek için işleci. Standartlar değişiklik ayrıntılarını bulunabilir [C++ boyutlandırılmış ayırmayı kaldırma](http://isocpp.org/files/papers/n3778.html). Genel form değişiklikleri ekleme **Sil** boyutu parametresi alır. işleci. Operatör daha önce kullandıysanız olan değişiklik **Sil** aynı imzayla (karşılayacak şekilde bir **yerleştirme yeni** işleci), bir derleyici hatasına (gerçekleşen C2956, alırsınız Burada yeni yerleştirme kullanılmışsa, derleyici nerede çalışırsa uygun eşleşen tanımlamak için kod konumda olduğundan bir noktada **Sil** işleci).  
  
     İşlev `void operator delete(void *, size_t)` olduğu bir **yerleştirme silme** karşılık gelen işleci **yerleştirme yeni** işlevi `void * operator new(size_t, size_t)` C ++ 11'de. C ++ 14 boyutlandırılmış ayırmayı kaldırma ile artık bu silme işlev, bir *normal ayırmayı kaldırma işlevi* (genel **Sil** işleci). Standart, yeni bir yerleştirme kullanımını karşılık gelen bir delete işlevi arar ve bulduğu her zamanki ayırmayı kaldırma işlevi, programın hatalı oluşturulmuş olması gerekir.  
  
     Örneğin, kodunuzu hem tanımladığını bir **yerleştirme yeni** ve **yerleştirme silme**:  
  
    ```cpp  
    void * operator new(std::size_t, std::size_t);  
    void operator delete(void*, std::size_t) noexcept;  
    ```  
  
     Sorun, işlev imzaları arasında değiştirme dizininde eşleşmenin nedeniyle oluşur. bir **yerleştirme silme** tanımladığınız işleci ve yeni genel boyutta **Sil** işleci. Farklı bir tür dışında kullanıp kullanmayacağınızı düşünmeniz `size_t` herhangi **yerleştirme yeni** ve **Sil** işleçleri.  Unutmayın türü `size_t` **typedef** derleyici bağımlıdır; bu bir **typedef** için **işaretsiz int** MSVC içinde. Bunun gibi bir listeden seçimli türü kullanmak iyi bir çözümdür:  
  
    ```cpp  
    enum class my_type : size_t {};  
    ```  
  
     Ardından, tanımınız değiştirin **yerleştirme yeni** ve **Sil** bu tür yerine ikinci bağımsız değişken olarak kullanmak için `size_t`. Ayrıca yeni türü geçirmek için yeni yerleştirme çağrıları güncelleştirmeniz gerekir (kullanarak örneğin, `static_cast<my_type>` tamsayı değerini dönüştürmek için) ve tanımı güncelleştirme **yeni** ve **Sil** geri dönüştürmek için tamsayı türü için. Kullanmanız gerekmez bir **enum** ; bunun için bir sınıf türü ile bir `size_t` üyesi da çalışır.  
  
     Ortadan kaldırmak mümkün olabilir, alternatif bir çözüm olan **yerleştirme yeni** tamamen. Kodunuzu kullanıyorsa **yerleştirme yeni** burada yerleşimi bağımsız değişken nesnesi olma ayrılmış veya silinmiş boyutudur, ardından boyutlandırılmış ayırmayı kaldırma özelliği, kendi özel bellek havuzu kodunuzu değiştirmek uygun olabilir bir bellek havuzunda uygulamak için yerleştirme işlevlerini kurtulabilirsiniz ve yalnızca kendi iki bağımsız kullanın ve **Sil** yerleştirme işlevleri yerine işleci.  
  
     Kodunuzu hemen güncelleştirmek istemiyorsanız, derleyici seçeneğini kullanarak eski davranışı için döndürebilirsiniz `/Zc:sizedDealloc-`. Bu seçeneği kullanırsanız, iki bağımsız silme işlevleri yok ve bir çakışma ile neden olmaz, **yerleştirme silme** işleci.  
  
- **Birleşim veri üyesi**  
  
     Veri üyeleri birleşimler artık başvuru türlerine sahip olabilir. Aşağıdaki kod, Visual Studio 2013'te başarıyla derlenir, ancak Visual Studio 2015'te bir hata oluşturur.  
  
    ```cpp  
    union U1   
    {  
        const int i;  
    };  
    union U2  
    {  
        int & i;  
    };  
    union U3  
    {  
        struct { int & i; };  
    };  
    ```  
  
     Yukarıdaki kod, aşağıdaki hatalar oluşturur:  
  
    ```Output  
    test.cpp(67): error C2625: 'U2::i': illegal union member; type 'int &' is reference type  
    test.cpp(70): error C2625: 'U3::i': illegal union member; type 'int &' is reference type  
    ```  
  
     Bu sorunu gidermek için başvuru türleri bir işaretçi veya bir değeri değiştirin. Bir işaretçi türü değiştirme birlik alanı kullanan kod değişiklikleri gerektirir. Kod bir değerle değiştirmeyi birleşim türleri alanları aynı bellek paylaşmak için bu durum diğer alanları etkiler birleşimde depolanan verileri değiştirin. Değer boyutuna bağlı olarak, bu Birleşimdeki boyutu değişebilir.  
  
- Anonim birleşimler, standart için daha fazla uyumluluğunu sunulmuştur. Önceki derleyici sürümleri, bir açık oluşturucu ve yıkıcı anonim birleşimler için oluşturulur. Bu, Visual Studio 2015'te silinir.  
  
    ```cpp  
    struct S   
    {  
        S();  
    };  
  
    union   
    {  
        struct   
        {  
            S s;  
        };  
    } u; // C2280  
    ```  
  
     Yukarıdaki kod, Visual Studio 2015'te aşağıdaki hata oluşturur:  
  
    ```cpp  
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function  
    note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here  
    ```  
  
     Bu sorunu çözmek için oluşturucu ve/veya yıkıcıya kendi tanımlarını sağlar.  
  
    ```cpp  
    struct S   
    {  
        // Provide a default constructor by adding an empty function body.  
        S() {}  
    };  
  
    union   
    {  
        struct   
        {  
            S s;  
        };  
    } u;  
    ```  
  
- **Anonim yapılar ile birleşimler**  
  
     Standart uymak için anonim yapılar Birleşimlerdeki üye için çalışma zamanı davranışı değişti. Böyle bir birleşim oluşturulduğunda bir birleşim içindeki anonim Yapı üyeleri Oluşturucusu artık örtük olarak çağrılır. Ayrıca, bir birleşim içindeki anonim Yapı üyeleri için yok edici birleşim kapsam dışına çıktığında, artık örtük olarak çağrılır. Aşağıdaki kod, bir birleşim U bir yok Edicisi olan bir adlandırılmış yapısı S olan bir üyeyi içeren anonim bir yapı içeren göz önünde bulundurun.  
  
    ```cpp  
    #include <stdio.h>  
    struct S   
    {  
        S() { printf("Creating S\n"); }  
        ~S() { printf("Destroying S\n"); }  
    };  
    union U   
    {  
        struct {  
            S s;  
        };  
        U() {}  
        ~U() {}  
    };  
  
    void f()  
    {  
        U u;  
        // Destructor implicitly called here.  
    }  
  
    int main()  
    {  
        f();  
  
        char s[1024];  
        printf("Press any key.\n");  
        gets_s(s);  
        return 0;  
    }  
    ```  
  
     Birleşim oluşturulur ve işlev f için yığın temizlendiği S yok Edicisi çağrılır Visual Studio 2013'te S için oluşturucu çağrılır. Ancak Visual Studio 2015'te oluşturucu ve yıkıcı değil çağrılır. Derleyici, bu davranış değişikliği hakkında bir uyarı verir.  
  
    ```Output  
    warning C4587: 'U::s': behavior change: constructor is no longer implicitly calledwarning C4588: 'U::s': behavior change: destructor is no longer implicitly called  
    ```  
  
     Özgün davranışı geri yüklemek için anonim yapının bir ad verin. Anonim olmayan yapılar çalışma zamanı davranışı, bir derleyici sürümünden bağımsız olarak aynıdır.  
  
    ```cpp  
    #include <stdio.h>  
  
    struct S   
    {  
        S() { printf("Creating S.\n"); }  
        ~S() { printf("Destroying S\n"); }  
    };  
    union U   
    {  
        struct   
        {  
            S s;  
        } namedStruct;  
        U() {}  
        ~U() {}  
    };  
  
    void f()  
    {  
        U u;  
    }  
  
    int main()  
    {  
        f();  
  
        char s[1024];  
        printf("Press any key.\n");  
        gets_s(s);  
        return 0;  
    }  
    ```  
  
     Alternatif olarak, yeni işlevler oluşturucunun ve yıkıcının kod taşımayı deneyin ve bu işlevlere aramaların oluşturucusu ve yok edici birleşim için ekleyin.  
  
    ```cpp  
    #include <stdio.h>  
  
    struct S   
    {  
        void Create() { printf("Creating S.\n"); }  
        void Destroy() { printf("Destroying S\n"); }  
    };  
    union U   
    {  
        struct   
        {  
            S s;  
        };  
        U() { s.Create(); }  
        ~U() { s.Destroy(); }  
    };  
  
    void f()  
    {  
        U u;  
    }  
  
    int main()  
    {  
        f();  
  
        char s[1024];  
        printf("Press any key.\n");  
        gets_s(s);  
        return 0;  
    }  
    ```  
  
- **Şablonu çözünürlüğü**  
  
     Şablonlar için ad çözümlemesi için değişiklikler yapıldı. Bir ad çözümlemesi için aday değerlendirirken C++'da, bu durum dikkate alınarak olası eşleşme olarak bir veya daha fazla adları geçersiz şablon örneklemesi oluşturur olabilir. Bu geçersiz örneklemeleri normalde SFINAE (değiştirme hatası olduğundan olmayan bir hata) bilinen bir ilkeye derleyici hataları neden olmaz.  
  
     Artık, bir sınıf şablonunun alt uzmanlaşması örneği oluşturmak için derleyicinin SFINAE gerektirir, bu işlem sırasında oluşan hataları derleyici hataları demektir. Önceki sürümlerde, derleyici bu tür hataları yoksayma. Örneğin, aşağıdaki kodu düşünün:  
  
    ```cpp  
    #include <type_traits>  
  
    template< typename T>  
    struct S  
    {  
        S() = default;  
        S(const S&);  
        S(S& &);  
  
        template< typename U, typename = typename std::enable_if< std::is_base_of< T, U> ::value> ::type>  
        S(S< U> & &);  
    };  
  
    struct D;  
  
    void f1()  
    {  
        S< D> s1;  
        S< D> s2(s1);  
    }  
  
    struct B  
    {  
    };  
  
    struct D : public B  
    {  
    };  
  
    void f2()  
    {  
        S< D> s1;  
        S< D> s2(s1);  
    }  
    ```  
  
     Geçerli bir derleyici ile derleme yaparsanız, aşağıdaki hatayı alıyorsunuz:  
  
    ```Output  
    type_traits(1110): error C2139: 'D': an undefined class is not allowed as an argument to compiler intrinsic type trait '__is_base_of'  
    ..\t331.cpp(14): note: see declaration of 'D'  
    ..\t331.cpp(10): note: see reference to class template instantiation 'std::is_base_of<T,U>' being compiled  
    with  
    [  
        T=D,  
        U=D  
    ]  
    ```  
  
     Bunun nedeni, ilk çağrısıysa is_base_of sınıfı noktasında `D` henüz tanımlanmadı.  
  
     Bu durumda, sınıfın tanımlı kadar bu tür nitelikler kullanmayacak şekilde açıklanmıştır. Tanımlarını taşırsanız `B` ve `D` kod dosyasının başına hata çözümlenir. Tanımları üstbilgi dosyalarında, sorunlu şablonları kullanılmadan önce herhangi bir sınıf tanımı derlenir emin olmak üst bilgi dosyaları dahil etme deyimlerini sırasını denetleyin.  
  
- **Kopya oluşturucuları**  
  
     Bu sınıfın kullanıcı tanımlı taşıma Oluşturucusu ancak hiçbir kullanıcı tanımlı kopya Oluşturucusu varsa Visual Studio 2013 ve Visual Studio 2015 derleyici bir sınıf için kopya Oluşturucu oluşturur. Dev14 içinde bu örtük olarak oluşturulan kopya Oluşturucu ayrıca işaretlenir "silme =".  

<!--From here to VS_Update1 added 04/21/2017-->

- **Ana extern "C" bir dönüş türü artık gerektirir bildirilmiş.**  

Aşağıdaki kod, şimdi C4430 üretir. 

```cpp
extern "C" __cdecl main(){} // C4430
```

Hatayı düzeltmek için dönüş türü ekleyin:

```cpp
extern "C" int __cdecl main(){} // OK
```

 - **TypeName bir üye Başlatıcısı içinde izin verilmiyor**  

Aşağıdaki kod, şimdi C2059 üretir:

```cpp
template<typename T>
struct S1 : public T::type
{
    S1() : typename T::type() // C2059
    {
    }
};

struct S2 {
    typedef S2 type;
};

S1<S2> s;
```

Hatayı düzeltmek için kaldırma `typename` başlatıcıdan:

```cpp
S1() : T::type() // OK
...
```

- **Depolama sınıfı açık uzmanlık üzerinde göz ardı edilir.** 

Aşağıdaki kodda, statik depolama sınıfı tanımlayıcısı yoksayıldı 

```cpp
template <typename T>
void myfunc(T h)
{
}

template<>
static void myfunc(double h) // static is ignored
{
}
```

- **Bir sabit bir static_assert bir sınıf şablonunun içinde kullanılan her zaman başarısız olur.**  

Aşağıdaki kod nedenleri `static_assert` her zaman başarısız:

```cpp
template <size_t some_value>
struct S1
{
    static_assert(false, "default not valid"); // always invoked

};

//other partial specializations here
```

Bu sorunu çözmek için değer kaydırma bir **yapı**:

```cpp
template <size_t some_value>
struct constant_false {
    static const bool value = false;
};

template <size_t some_value>
struct S1
{
    static_assert(constant_false<some_value>::value, "default not valid");
};

//other partial specializations here
```

- **Kuralları iletme bildirimleri için zorunlu tutulur. (Yalnızca c için geçerlidir)**  

Aşağıdaki kod, şimdi C2065 üretir:

```cpp
struct token_s;
typedef int BOOL;
typedef int INT;

typedef int(*PFNTERM)(PTOKEN, BOOL, INT); // C2065: 'PTOKEN' : undeclared identifier
```

Sorunu gidermek için uygun iletme bildirimleri ekleyin:

```cpp
struct token_s;
typedef int BOOL;
typedef int INT;

// forward declarations:
typedef struct token_s TOKEN; 
typedef TOKEN *PTOKEN;

typedef int(*PFNTERM)(PTOKEN, BOOL, INT);
```

- **İşlev işaretçi türlerinin daha tutarlı zorlama**  

Aşağıdaki kod, şimdi C2197 üretir:

```cpp
typedef int(*F1)(int);
typedef int(*F2)(int, int);

void func(F1 f, int v1, int v2)
{
    f(v1, v2); // C2197
}
```

- **Aşırı yüklenmiş işlevler belirsiz çağrı**  

Aşağıdaki kod artık C266 üretir: 'N::bind': aşırı yüklenmiş işleve belirsiz çağrı

```cpp 
template<typename R, typename T, typename T1, typename A1>
void bind(R(T::*)(T1), A1&&);

namespace N
{
    template <typename T, typename R, typename ... Tx>
    void bind(R(T::*)(Tx...), T* ptr);
}

using namespace N;

class Manager
{
public:
    void func(bool initializing);

    void mf()
    {
        bind(&Manager::func, this); //C2668
    }
};
```

Hatayı düzeltmek için tam çağrı belirtebilme `bind: N::bind(...)`. Bu değişiklik bildirimi aracılığıyla bildirilmemiş tanımlayıcı (C2065) ise, ancak ardından bunun ile bu sorunu gidermek uygun olabilir bir **kullanarak** bildirimi yerine.

Bu düzen ComPtr ve diğer türleri ile sık olur `Microsoft::WRL` ad alanı.

- **Yanlış adresini düzeltin**  

Aşağıdaki kod artık C2440 oluşturur: '=': dan dönüştürülemiyor ' türü *' için 'type'. Hata, değiştirme ve (tür) (yazmak için) gidermek için (ve f()) için (f()).
 
```cpp
\\ C
typedef void (*type)(void);
 
void f(int i, type p);
void g(int);
void h(void)
{
    f(0, &(type)g);
}
 
\\ C++
typedef void(*type)(void);
 
type f();
 
void g(type);
 
void h()
{
    g(&f());
}
```

- **Dize sabit değeri bir sabit bir dizidir**  

Aşağıdaki kod artık C2664 oluşturur: ' void f (void *)': 1 bağımsız değişkeninden dönüştürülemiyor ' const char (*) [2]' için ' void *'

```cpp
void f(void *);
 
void h(void)
{
    f(&__FUNCTION__); 
    void *p = &"";
}
```

Hatayı düzeltmek için işlevi parametre türüne değiştirme `const void*`, veya başka gövdesini değiştirin `h` şuna benzeyecektir:

```cpp
void h(void)
{
    char name[] = __FUNCTION__;
    f( name); 
    void *p = &"";
}

```

- **C ++ 11 UDL dizeleri**  

Aşağıdaki kod, şimdi hata C3688 oluşturur: Geçersiz sabit değerli son ek 'L'; sabit değer operatörü veya sabit değer operatörü Şablonu ' işleci "" L' bulunamadı

```cpp
#define MACRO

#define STRCAT(x, y) x\#\#y

int main(){

    auto *val1 = L"string"MACRO;
    auto *val2 = L"hello "L"world";

    std::cout << STRCAT(L"hi ", L"there");
}
```

Hatayı düzeltmek için kodu değiştirin:

```cpp
#define MACRO

// Remove ##. Strings are automatically
// concatenated so they are not needed
#define STRCAT(x, y) x y

int main(){
    //Add space after closing quote
    auto *val1 = L"string" MACRO;
    auto *val2 = L"hello " L"world";

    std::cout << STRCAT(L"hi ", L"there");
}
```

Yukarıdaki örnekte `MACRO` artık iki belirteçleri (makro tarafından izlenen bir dize) olarak ayrıştırılır.  Artık, tek bir belirteç UDL ayrıştırılır.  Aynı daha önce L ' ayrıştırıldı L "" L"" geçerlidir"" ve L "" ve artık L ayrıştırılır "" L ve "".

Dize birleştirme kurallarını da uyumlu anlamına gelir L "a", "b", "ab" L için eşdeğer standart hale getirilmiştir. Visual Studio'nun önceki sürümlerinde, farklı karakter genişliği ile dize birleştirme kabul etmedi.

- **C ++ 11 boş karakter kaldırıldı**  

Aşağıdaki kod hatası C2137 artık oluşturur: boş karakter sabiti

```cpp
bool check(wchar_t c){
    return c == L''; //implicit null character
}
```

Hatayı düzeltmek için kodu değiştirin:

```cpp
bool check(wchar_t c){
    return c == L'\0';
}
```

- **Kopyalanabilir olmadıklarından MFC özel durumları değere göre yakalanamaz**  

Artık bir MFC uygulaması aşağıdaki kodda hatası C2316 neden olur: 'D ': yok edici ve/veya kopya oluşturucusu, erişilemez veya silinmiş olarak yakalanamıyor

```cpp
struct B {
public:
    B();
private:
    B(const B &);
};

struct D : public B {
};

int main()
{
    try
    {
    }
    catch (D) // C2316
    {
    }
}
```

Bu kodu düzeltmek için catch bloğunun değiştirebilirsiniz `catch (const D &)` ancak daha iyi çözüm genellikle MFC TRY/CATCH makroları kullanmaktır.

- **alignof artık bir anahtar sözcüktür**  

Aşağıdaki kod hatası C2332 artık oluşturur: 'class': Etiket adı eksik. Kodu düzeltmek için sınıfı yeniden adlandırmak veya gerekir, yalnızca sınıf olarak alignof, aynı iş gerçekleştiriyorsa sınıfı new anahtar sözcüğü ile değiştirin.

```cpp
class alignof{}
```

- **constexpr artık bir anahtar sözcüktür**  

Aşağıdaki kod hatası C2059 artık oluşturur: söz dizimi hatası: ')'. Bu kodu düzeltmek için herhangi bir işlev veya "constexpr" adlı değişken adları yeniden adlandırmanız gerekir. 

```cpp
int constexpr() {return 1;}
```

- **Taşınabilir türleri sabit olamaz**  

Bir işlev taşınmasına yönelik bir türü döndürür, dönüş türü olmamalıdır **const**.

- **Silinen kopya oluşturucuları**  

Aşağıdaki kod artık C2280'ın üretir:: S(S &&)': silinmiş bir işleve başvurmaya çalışıyor:

```cpp
struct S{
    S(int, int);
    S(const S&) = delete;
    S(S&&) = delete;
};

S s2 = S(2, 3); //C2280
```

Hatayı düzeltmek için doğrudan başlatma için kullanın. `S2`:

```cpp
struct S{
    S(int, int);
    S(const S&) = delete;
    S(S&&) = delete;
};

S s2 = {2,3}; //OK
```

- **Yalnızca hiçbir lambda yakalama çalıştırdığınızda oluşturulan işlev işaretçisi dönüştürme**  

Aşağıdaki kod, Visual Studio 2015'te C2664 oluşturur. 

```cpp
void func(int(*)(int)) {}

int main() {

    func([=](int val) { return val; });
}
```

Hatayı düzeltmek için kaldırma `=` yakalama listeden.

- **Dönüştürme işleçleri içeren belirsiz çağrı**  

Aşağıdaki kod artık hatası C2440 oluşturur: 'tür cast': 'S2', 'S1'e dönüştürülemez:

```cpp 
struct S1 {
    S1(int);
};

struct S2 {
    operator S1();
    operator int();
};

void f(S2 s2)
{
    (S1)s2;
}
```

Hatayı düzeltmek için dönüştürme işleci açıkça çağırın:

```cpp
void f(S2 s2)
{
    //Explicitly call the conversion operator
    s2.operator S1();
    // Or
    S1((int)s2);
}
```

Aşağıdaki kod hatası C2593 artık oluşturur: ' işleci =' belirsiz:

```cpp
struct S1 {};

struct S2 {
    operator S1&();
    operator S1() const;
};

void f(S1 *p, S2 s)
{
    *p = s;
}
```

Hatayı düzeltmek için dönüştürme işleci açıkça çağırın:

```cpp
void f(S1 *p, S2 s)
{
       *p = s.operator S1&();
}
```

- **Statik olmayan veri üyesi başlatma (NSDMI) geçersiz kopya başlatma Düzelt**  

Aşağıdaki kod artık hatası C2664 oluşturur: 'S1::S1(S1 &&)': 'bool' dönüştürülemiyor bağımsız değişkeni 1 ' const S1 &':

```cpp
struct S1 {
    explicit S1(bool);
};

struct S2 {
    S1 s2 = true; // error
};
```

Hatayı düzeltmek için doğrudan başlatma kullanın:

```cpp
struct S2 {
S1 s1{true}; // OK
};
```

- **Decltype deyimleri içinde oluşturucular erişme**  

Aşağıdaki kod artık C2248 üretir: 'S::S': özel üye erişimi bildirilen sınıfın içinde olamaz ':

```cpp
class S {
    S();
public:
    int i;
};

class S2 {
    auto f() -> decltype(S().i);
};
```

Hatayı düzeltmek için arkadaş bildirimi ekleme `S2` içinde `S`:

```cpp
class S {
    S();
    friend class S2; // Make S2 a friend
public:
    int i;
};
```

- **Varsayılan ctor lambda örtük olarak silindi**  

Aşağıdaki kod, şimdi hata C3497 oluşturur: bir lambda örneği oluşturulamıyor:

```cpp
void func(){
    auto lambda = [](){};    
 
    decltype(lambda) other;
}
```

Hatayı düzeltmek için çağrılacak varsayılan oluşturucu gereksinimini kaldırın. Ardından lambda herhangi bir şey yakalamaz, işlev işaretçisi dönüştürülebilen.

- **Silinen atama işleci ile lambda ifadeleri**  

Aşağıdaki kod, şimdi hatası C2280 üretir:

```cpp
#include <memory>
#include <type_traits>

template <typename T, typename D>
std::unique_ptr<T, typename std::remove_reference<D &&>::type> wrap_unique(T *p, D &&d);

void f(int i)
{
    auto encodedMsg = wrap_unique<unsigned char>(nullptr, [i](unsigned char *p) {
    });
    encodedMsg = std::move(encodedMsg);
}
```

Hatayı düzeltmek için lambda functor sınıfıyla değiştirin veya atama işlecini kullanmanız ihtiyacını ortadan kaldırıyor.

- **Silinen bir kopya Oluşturucusu olan bir nesne taşıma girişimi**  

Aşağıdaki kod hatası C2280 artık oluşturur: 'taşınabilir:: moveable(const moveable &)': silinmiş bir işleve başvurmaya çalışıyor

```cpp
struct moveable {

    moveable() = default;
    moveable(moveable&&) = default;
    moveable(const moveable&) = delete;
};

struct S {
    S(moveable && m) :
        m_m(m)//copy constructor deleted
    {}
    moveable m_m;
};
```

Hatayı düzeltmek için kullanmak `std::move` bunun yerine:

```cpp
S(moveable && m) :
    m_m(std::move(m))
```

- **Daha sonra aynı işlevde tanımlanan başka bir yerel sınıf yerel sınıf başvuramaz**  

Aşağıdaki kod hatası C2079 artık oluşturur: 's' kullanır, struct 'main::S2' tanımsız

```cpp
int main()
{
    struct S2;
    struct S1 {
        void f() {
            S2 s;
        }
    };
    struct S2 {};
}
```

Hatayı düzeltmek için tanımını Taşı `S2`:

```cpp
int main()
{
    struct S2 { //moved up
    };
 
struct S1 {
    void f() {
        S2 s;
        }
    };
}
```

- **Korumalı bir temel ctor türetilmiş ctor gövdesinde çağrılamıyor.**  

Aşağıdaki kod hatası C2248 artık oluşturur: 'S1::S1': 'S1' sınıfta bildirilen korumalı üye erişemiyor

```cpp
struct S1 {
protected:
    S1();
};

struct S2 : public S1 {
    S2() {
        S1();
    }
};
```

İçinde hatayı gidermek için `S2` çağrısını kaldırın `S1()` oluşturucudan ve isteğe bağlı olarak gerekli başka bir işlevde yerleştirin.

- **{} İşaretçi dönüştürme engeller**  

Aşağıdaki kod artık C2439 üretir 'S::p': üye başlatılamadı   

```cpp
struct S {
    S() : p({ 0 }) {}
    void *p;
};
```

Hatayı düzeltmek için geçici olarak gelen bir küme ayraçları Kaldır `0` veya başka kullanım **nullptr** yerine, bu örnekte gösterildiği gibi:

```cpp
struct S {
    S() : p(nullptr) {}
    void *p;
};
```

- **Yanlış bir makro tanımı ve parantez ile kullanımı**  

Aşağıdaki örnek artık hatası C2008 oluşturur: ';': Makro tanımında beklenmiyor

```cpp
#define A; //cause of error

struct S {
    A(); // error
};
```

Sorunu gidermek için en üst satırına değiştirin `#define A();`

Aşağıdaki kod hatası C2059 oluşturur: söz dizimi hatası: ')'

```cpp
//notice the space after 'A'
#define A () ;

struct S {
    A();
};
```

Kod Kaldır arasındaki boşluk düzeltmek için bir ve ().

Aşağıdaki kod hatası C2091 oluşturur: işlev işlevi döndürür:

```cpp
#define DECLARE void f()

struct S {
    DECLARE();
};
```

Hatayı düzeltmek için s. DECLARE sonra parantez Kaldır `DECLARE;`.

Aşağıdaki kod hatası C2062 oluşturur: türü 'int' beklenmeyen

```cpp
#define A (int)

struct S {
    A a;
};
```

Sorunu düzeltmek için tanımladığınız `A` şöyle:

```cpp
#define A int
```

- **Ek bildirimlerinde parens**  

Aşağıdaki kod hatası C2062 oluşturur: türü 'int' beklenmeyen

```cpp
struct S {
    int i;
    (int)j;
};
```

Hatayı düzeltmek için kaldırma gelen parens `j`. Varsa parens daha anlaşılır olması için gerekli olan, ardından kullanmak bir **typedef**.

- **Derleyici tarafından oluşturulan oluşturucular ve __declspec(novtable)**  

Visual Studio 2015'te, satır içi derleyici tarafından oluşturulan Oluşturucular, soyut sınıf sanal temel sınıflarla yanlış kullanımı getirebilir karşılaşma olasılığı yüksektir yoktur `__declspec(novtable)` ile birlikte kullanıldığında `__declspec(dllimport)`.

- **tek bir doğrudan liste başlatma ifadesinde otomatik gerektirir** 

Aşağıdaki kod, şimdi hata C3518 oluşturur: 'testPositions': bir doğrudan liste başlatma bağlamında 'Auto' türü yalnızca bir tek bir başlatıcı ifadeden

```cpp
auto testPositions{
    std::tuple<int, int>{13, 33},
    std::tuple<int, int>{-23, -48},
    std::tuple<int, int>{38, -12},
    std::tuple<int, int>{-21, 17}
};
```

Hatayı düzeltmek için bir başlatmak için bir olasılıktır `testPositions` gibi:

```cpp
std::tuple<int, int> testPositions[]{
    std::tuple<int, int>{13, 33},
    std::tuple<int, int>{-23, -48},
    std::tuple<int, int>{38, -12},
    std::tuple<int, int>{-21, 17}
};
```

- **İs_convertible türlerinde işaretçileri ve türleri denetleniyor**  

Aşağıdaki kod, artık statik onaylama başarısız olmasına neden olur. 

```cpp
struct B1 {
private:
    B1(const B1 &);
};
struct B2 : public B1 {};
struct D : public B2 {};

static_assert(std::is_convertible<D, B2>::value, "fail");
```

Hatayı düzeltmek için değiştirme `static_assert` işaretçileri karşılaştırır böylece `D` ve `B2`:

```cpp
static_assert(std::is_convertible<D*, B2*>::value, "fail");
```

- **declspec(novtable) bildirimleri tutarlı olmalıdır.**  

**declspec** bildirimleri tutarlı olmalıdır tüm kitaplıkları. Aşağıdaki kod, artık bir tek Tanım Kuralı (ODR) ihlaline neden olur:

```cpp
//a.cpp
class __declspec(dllexport)
    A {
public:
    A();
    A(const A&);
    virtual ~A();
private:
    int i;
};

A::A() {}
A::~A() {}
A::A(const A&) {}

//b.cpp
// compile with cl.exe /nologo /LD /EHsc /Osx b.cpp
#pragma comment(lib, "A")
class __declspec(dllimport) A
{
public: A();
         A(const A&);
         virtual ~A();
private:
    int i;
};

struct __declspec(novtable) __declspec(dllexport) B
    : virtual public A {
    virtual void f() = 0;
};

//c.cpp
#pragma comment(lib, "A")
#pragma comment(lib, "B")
class __declspec(dllimport) A
{
public:
    A();
    A(const A&);
    virtual ~A();
private:
    int i;
};
struct  /* __declspec(novtable) */ __declspec(dllimport) B // Error. B needs to be novtable here also.
    : virtual public A
{
    virtual void f() = 0;
};

struct C : virtual B
{
    virtual void f();
};

void C::f() {}
C c;
```

###  <a name="VS_Update1"></a> Güncelleştirme 1'de uyumluluk geliştirmeleri  
  
- **Özel sanal temel sınıflar ve dolaylı devralma**  
  
     Önceki derleyici sürümleri izin türetilmiş bir sınıf üyesi işlevleri çağırmak kendi *dolaylı olarak türetilmiş* `private virtual` temel sınıflar. Bu eski davranışı yanlış ve C++ standartlarına uygun değil. Derleyici artık bu şekilde yazılmış kod kabul eder ve sonuç olarak derleyici hatası C2280 sorunlar.  
  
    ```Output  
    error C2280: 'void *S3::__delDtor(unsigned int)': attempting to reference a deleted function  
    ```  
  
     Örnek (önce)  
  
    ```cpp  
    class base  
    {  
    protected:  
        base();  
        ~base();  
    };  
  
    class middle : private virtual base {}; class top : public virtual middle {};   
  
    void destroy(top *p)  
    {  
        delete p;  //  
    }  
    ```  
  
     Örnek (sonra)  
  
    ```cpp  
    class base;  // as above  
  
    class middle : protected virtual base {};  
    class top : public virtual middle {};  
  
    void destroy(top *p)  
    {  
        delete p;  
    }  
    ```  
  
     - veya -  
  
    ```cpp  
    class base;  // as above  
  
    class middle : private virtual base {};  
    class top : public virtual middle, private virtual bottom {};  
  
    void destroy(top *p)  
    {  
        delete p;  
    }  
    ```  
  
- **Yeni aşırı yüklenmiş bir işleç ve delete işleci**  
  
     Önceki derleyici sürümleri, üye olmayan izin **new işleci** ve üye olmayan **delete işleci** statik bildirilmesi ve dışında genel ad alanlarında bildirilmesi için.  Bu eski davranışı oluşturulan program değil çağırırsınız bir risk **yeni** veya **Sil** sessiz hatalı çalışma zamanı davranışları kaynaklanan Programcı hedeflenen işleci uygulaması. Derleyici artık bu şekilde yazılmış kod kabul eder ve bunun yerine derleyici hatası C2323 sorunlar.  
  
    ```Output  
    error C2323: 'operator new': non-member operator new or delete functions may not be declared static or in a namespace other than the global namespace. 
    ```  
  
     Örnek (önce)  
  
    ```cpp  
    static inline void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // error C2323  
    ```  
  
     Örnek (sonra)  
  
    ```cpp  
    void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // removed 'static inline'  
    ```  
  
     Ayrıca, derleyici vermez ancak belirli Tanılama, satır içi işleç **yeni** yapılı olarak kabul edilir.  
  
- **Çağırma ' işleci *türü*() ' (kullanıcı tanımlı dönüştürme) sınıf olmayan türler hakkında**  
  
     İzin verilen Derleyici önceki sürümlerini ' işleci *türü*() ' sınıf olmayan türler üzerinde sessizce yoksayılıyor sırasında çağrılabilir. Bu eski davranışı sessiz hatalı kod oluşturma, beklenmeyen çalışma zamanı davranışları kaynaklanan riski oluşturuldu. Derleyici artık bu şekilde yazılmış kod kabul eder ve bunun yerine derleyici hatası C2228 sorunlar.  
  
    ```Output  
    error C2228: left of '.operator type' must have class/struct/union  
    ```  
  
     Örnek (önce)  
  
    ```cpp  
    typedef int index_t;  
    void bounds_check(index_t index);  
    void login(int column)  
    {  
        bounds_check(column.operator index_t());  // error C2228  
    }  
    ```  
  
     Örnek (sonra)  
  
    ```cpp  
    typedef int index_t;  
    void bounds_check(index_t index);  
    void login(int column)  
    {  
        bounds_check(column);  // removed cast to 'index_t', 'index_t' is an alias of 'int'  
    }  
    ```  
  
- **Ayrıntılandırılmış tür tanımlayıcıları, yedekli typename**  
  
     İzin verilen Derleyici önceki sürümlerini **typename** ayrıntılandırılmış tür tanımlayıcıları; bu şekilde yazılmış kod anlamsal olarak yanlıştır. Derleyici artık bu şekilde yazılmış kod kabul eder ve bunun yerine derleyici hatası C3406 sorunlar.  
  
    ```Output  
    error C3406: 'typename' cannot be used in an elaborated type specifier  
    ```  
  
     Örnek (önce)  
  
    ```cpp  
    template <typename class T>  
    class container;  
    ```  
  
     Örnek (sonra)  
  
    ```cpp  
    template <class T>  // alternatively, could be 'template <typename T>'; 'typename' is not elaborating a type specifier in this case  
    class container;  
    ```  
  
- **Başlatıcı listesi dizilerden çıkarım yazın**  
  
     Önceki derleyici sürümleri, bir başlatıcı listeden dizi türü kesintisi desteklememektedir. Derleyici artık bu tür kesintisi biçimi destekler ve sonuç olarak, başlatıcı listeleri kullanarak işlev şablonları çağrıları artık belirsiz olabilir veya farklı bir aşırı yüklemesini daha önceki bir derleyici sürümlerinde seçilmesi. Bu sorunları çözmek için program artık açıkça Programcı hedeflenen aşırı yük belirtmeniz gerekir.  
  
     Bu yeni davranış eşit geçmiş adayı olarak kadar iyi bir ek aday dikkate alınması gereken aşırı yükleme çözünürlüğü neden olduğunda çağrısı belirsiz hale gelir ve derleyici derleyici hatası C2668 sonucunda verir.  
  
    ```Output  
    error C2668: 'function' : ambiguous call to overloaded function.  
    ```  
  
     Örnek 1: (Önce) aşırı yüklenmiş işleve belirsiz çağrı  
  
    ```cpp  
    // In previous versions of the compiler, code written in this way would unambiguously call f(int, Args...)  
    template < typename... Args>  
    void f(int, Args...);  //  
  
    template < int N, typename... Args>  
    void f(const int(&)[N], Args...);  
  
    int main()  
    {  
        // The compiler now considers this call ambiguous, and issues a compiler error  
         f({ 3 });   error C2668 : 'f' ambiguous call to overloaded function  
    }  
    ```  
  
     Örnek 1: (sonra) aşırı yüklenmiş işleve belirsiz çağrı  
  
    ```cpp  
    template < typename... Args>  
    void f(int, Args...);  //  
  
    template < int N, typename... Args>  
    void f(const int(&)[N], Args...);  
  
    int main()  
    {  
        // To call f(int, Args...) when there is just one expression in the initializer list, remove the braces from it.  
        f(3);   
    }  
    ```  
  
     Bu yeni davranış geçmiş aday daha iyi bir eşleşme arama için yeni aday, kesin bir şekilde çözümler olan ek bir aday dikkate alınması gereken aşırı yükleme çözünürlüğü neden olduğunda, programın davranışını bir değişiklik neden büyük olasılıkla farklıdır Programcı yöneliktir.  
  
     Örnek 2: (önce) aşırı yükleme çözünürlüğü Değiştir  
  
    ```cpp  
    // In previous versions of the compiler, code written in this way would unambiguously call f(S, Args...)  
    struct S  
    {  
        int i;  
        int j;  
    };  
  
    template < typename... Args>  
    void f(S, Args...);  
  
    template < int N, typename... Args>  
    void f(const int *&)[N], Args...);  
  
    int main()  
    {  
        // The compiler now resolves this call to f(const int (&)[N], Args...) instead  
         f({ 1, 2 });   
    }  
    ```  
  
     Örnek 2: (sonra) aşırı yükleme çözünürlüğü Değiştir  
  
    ```cpp  
    struct S;  // as before  
  
    template < typename... Args>  
    void f(S, Args...);  
  
    template < int N, typename... Args>  
    void f(const int *&)[N], Args...);  
  
    int main()  
    {  
        // To call f(S, Args...), perform an explicit cast to S on the initializer list.  
        f(S{ 1, 2 });   
    }  
    ```  
  
- **Switch deyimi uyarıların geri yükleme**  
  
     Derleyicinin önceki bir sürümünü önceden varolan uyarıları ilgili kaldırıldı **geçiş** deyimleri; bunlar uyarı şimdi geri yüklendi. Derleyici artık geri yüklenen uyarı verir ve belirli durumlarda (varsayılan durumda dahil) için ilgili uyarıların artık sorunlu durum içeren satırı yerine switch ifadesinin Son satırda verilir. Sonuç olarak bu uyarılar farklı satırlara geçmişte artık verme, uyarıları önceden gizlenen kullanarak `#pragma warning(disable:####)` artık beklendiği gibi bastırılabilir. Beklendiği gibi bu uyarıları bastırmak için taşımak gerekli olabilir `#pragma warning(disable:####)` ilk harfi büyük olasılıkla sorunlu üzerine bir satır için yönerge. Geri yüklenen uyarılar verilmiştir.  
  
    ```Output  
    warning C4060: switch statement contains no 'case' or 'default' labels  
    ```  
  
    ```Output  
    warning C4061: enumerator 'bit1' in switch of enum 'flags' is not explicitly handled by a case label  
    ```  
  
    ```Output  
    warning C4062: enumerator 'bit1' in switch of enum 'flags' is not handled  
    ```  
  
    ```Output  
    warning C4063: case 'bit32' is not a valid value for switch of enum 'flags'  
    ```  

    ```Output  
    warning C4064: switch of incomplete enum 'flags'  
    ```  
  
    ```Output  
    warning C4065: switch statement contains 'default' but no 'case' labels  
    ```  
  
    ```Output  
    warning C4808: case 'value' is not a valid value for switch condition of type 'bool'  
    ```  
  
    ```Output  
    Warning C4809: switch statement has redundant 'default' label; all possible 'case' labels are given  
    ```  
  
     C4063 (önce) örneği  
  
    ```cpp  
    class settings  
    {  
    public:  
        enum flags  
        {  
            bit0 = 0x1,  
            bit1 = 0x2,  
            ...  
        };  
        ...  
    };  
  
    int main()  
    {  
        auto val = settings::bit1;  
  
        switch (val)  
        {  
        case settings::bit0:  
            break;  
  
        case settings::bit1:  
            break;  
  
             case settings::bit0 | settings::bit1:  // warning C4063  
                break;  
        }  
    };  
    ```  
  
     C4063 (sonra) örneği  
  
    ```cpp  
    class settings { ... };  // as above  
    int main()  
    {  
        // since C++11, use std::underlying_type to determine the underlying type of an enum  
        typedef std::underlying_type< settings::flags> ::type flags_t;   
  
            auto val = settings::bit1;  
  
        switch (static_cast< flags_t> (val))  
        {  
        case settings::bit0:  
            break;  
  
        case settings::bit1:  
            break;  
  
        case settings::bit0 | settings::bit1:  // ok  
            break;  
        }  
    };  
    ```  
  
     Geri yüklenen bir uyarı örnekleri kendi belgelerde verilmiştir.  
  
- **#include: ana dizin tanımlayıcısı kullanın '..' pathname içinde** (yalnızca etkiler `/Wall` `/WX`)  
  
     Önceki derleyici sürümleri üst dizini belirticisi kullanımını algılamadı '..' yol adını içinde `#include` yönergeleri. Bu şekilde yazılmış kod, genellikle projenin dışında yanlış proje göreli yollar kullanarak mevcut başlıkları da eklediğinizden yöneliktir. Bu eski davranışı program hedeflenen Programcı değerinden farklı bir kaynak dosyasındaki dahil ederek derlenebilir veya bu göreli yolları diğer yapı ortamları için taşınabilir olmayacaktır bir risk oluşturuldu. Derleyici artık algılar ve bu şekilde yazılmış kod Programcı size bildirir ve etkinleştirilirse C4464, uyarı bir isteğe bağlı derleyici verir.  
  
    ```Output  
    warning C4464: relative include path contains '..'  
    ```  
  
     Örnek (önce)  
  
    ```cpp  
    #include "..\headers\C4426.h"  // emits warning C4464  
    ```  
  
     Örnek (sonra)  
  
    ```cpp  
    #include "C4426.h"  // add absolute path to 'headers\' to your project's include directories  
    ```  
  
     Derleyici belirli tanılama sağlamazsa ancak Ayrıca, ayrıca, üst dizini belirticisi öneririz "..." Not proje ekleme dizinleri belirtmek için kullanılmalıdır.  
  
- **#pragma optimize() genişletir üstbilgi dosya sonunun** (yalnızca etkiler `/Wall` `/WX`)  
  
     Önceki derleyici sürümleri, bir çeviri birimi içinde bulunan bir üstbilgi dosyası kaçış iyileştirme bayrağı ayarlarında yapılan değişiklikler algılamadı. Derleyici artık algılar ve bu şekilde yazılmış kod Programcı bildirir ve sorunlu konumda C4426 uyarı isteğe bağlı bir derleyici sorunları `#include`, etkin. Değişiklikler çakışma iyileştirme bayrakları derleyici komut satırı bağımsız değişkenleri olarak ayarlarsanız bu uyarı yalnızca görüntülenir.  
  
    ```Output  
    warning C4426: optimization flags changed after including header, may be due to #pragma optimize()  
    ```  
  
     Örnek (önce)  
  
    ```cpp  
    // C4426.h  
    #pragma optimize("g", off)  
    ...  
    // C4426.h ends  
  
    // C4426.cpp  
    #include "C4426.h"  // warning C4426  
    ```  
  
     Örnek (sonra)  
  
    ```cpp  
    // C4426.h  
    #pragma optimize("g", off)  
                ...  
    #pragma optimize("", on)  // restores optimization flags set via command-line arguments  
    // C4426.h ends  
  
    // C4426.cpp  
    #include "C4426.h"  
    ```  
  
- **#Pragma warning(push) eşleşmeyen** ve **#pragma warning(pop)** (yalnızca etkiler `/Wall` `/WX`)  
  
     Önceki derleyici sürümleri algılamadı `#pragma warning(push)` durum değişikliklerini ile eşleştirilmiş `#pragma warning(pop)` durum nadiren yönelik farklı bir kaynak dosyasındaki değişiklikleri. Bu eski davranışı bir risk, oluşturulan program sessiz hatalı çalışma zamanı davranışını büyük olasılıkla kaynaklanan hazırlanan Programcı etkin uyarıları farklı bir dizi derlenecek. Derleyici artık algılar ve bu şekilde yazılmış kod Programcı bildirir ve eşleşen konumda C5031 uyarı isteğe bağlı bir derleyici sorunları `#pragma warning(pop)`, etkin. Bu uyarı, karşılık gelen #pragma warning(push) konumunu başvuran bir not içerir.  
  
    ```Output  
    warning C5031: #pragma warning(pop): likely mismatch, popping warning state pushed in different file  
    ```  
  
     Örnek (önce)  
  
    ```cpp  
    // C5031_part1.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    // C5031_part1.h ends without #pragma warning(pop)  
  
    // C5031_part2.h  
    ...  
    #pragma warning(pop)  // pops a warning state not pushed in this source file  
    ...  
    // C5031_part1.h ends  
  
    // C5031.cpp  
    #include "C5031_part1.h" // leaves #pragma warning(push) 'dangling'  
    ...  
    #include "C5031_part2.h" // matches 'dangling' #pragma warning(push), resulting in warning C5031  
    ...  
    ```  
  
     Örnek (sonra)  
  
    ```cpp  
    // C5031_part1.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop)  // pops the warning state pushed in this source file  
    // C5031_part1.h ends without #pragma warning(pop)  
  
    // C5031_part2.h  
    #pragma warning(push)  // pushes the warning state pushed in this source file  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop)  
    // C5031_part1.h ends  
  
    // C5031.cpp  
    #include "C5031_part1.h" // #pragma warning state changes are self-contained and independent of other source files or their #include order.  
    ...  
    #include "C5031_part2.h"  
    ...  
    ```  
  
     Bu şekilde yazılmış kod, bazen genel olmayan ancak kasıtlıdır. Bu şekilde yazılmış kod değişiklikleri için hassas `#include` sırası; mümkün olduğunda, kaynak kodu dosyaları uyarı durumuna bağımsız bir şekilde yönetmenizi öneririz.  
  
- **Eşleşmeyen #pragma warning(push)** (yalnızca etkiler `/Wall` `/WX`)  
  
     Önceki derleyici sürümleri algılamadı eşleşmeyen `#pragma warning(push)` durumu değiştiğinde bir çeviri birimi sonunda. Derleyici artık algılar ve bu şekilde yazılmış kod Programcı bildirir ve eşleşmeyen konumda C5032 uyarı isteğe bağlı bir derleyici sorunları `#pragma warning(push)`, etkin. Çeviri biriminde herhangi bir derleme hatası varsa, bu uyarı yalnızca görüntülenir.  
  
    ```Output  
    warning C5032: detected #pragma warning(push) with no corresponding #pragma warning(pop)  
    ```  
  
     Örnek (önce)  
  
    ```cpp  
    // C5032.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    // C5032.h ends without #pragma warning(pop)  
  
    // C5032.cpp  
    #include "C5032.h"  
    ...  
    // C5032.cpp ends -- the translation unit is completed without #pragma warning(pop), resulting in warning C5032 on line 1 of C5032.h  
    ```  
  
     Örnek (sonra)  
  
    ```cpp  
    // C5032.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop) // matches #pragma warning (push) on line 1  
    // C5032.h ends  
  
    // C5032.cpp  
    #include "C5032.h"  
    ...  
    // C5032.cpp ends -- the translation unit is completed without unmatched #pragma warning(push)  
    ```  
  
- **Geliştirilmiş #pragma uyarı durumu izleme sonucunda ek uyarılar verilebilir**  
  
     Önceki derleyici sürümleri de sorun için yeterince uyarı tüm uyarıları yönelik durum değişikliklerini #pragma izlenir. Bu davranış, uyarıları etkili bir şekilde kullanılmaya Programcı farklı durumlarda atlanması, belirli bir risk oluşturuldu. Derleyici artık izler `#pragma warning` durumu daha yerine--özellikle ilgili `#pragma warning` durumu şablonları içinde--değiştirir ve isteğe bağlı olarak istenmeyenkullanımlarıbulunProgramcıyardımcıolmaamacınıtaşımaktadıryeniuyarılarC5031veC5032sorunları`#pragma warning(push)` ve `#pragma warning(pop)`.  
  
     Sonucu olarak geliştirilmiş `#pragma warning` durumunda değişiklik izleme, eski adıyla yanlış gizlenen uyarılar veya önceden misdiagnosed sorunlarıyla ilgili uyarıları artık verilmiş.  
  
- **Erişilemeyen kod daha iyi tanımlama**  
  
     Derleyici belirli kodun ulaşılamaz olduğunu kanıtlamak, C++ Standart Kitaplığı değişiklikleri ve satır içi işlev çağrıları önceki derleyici sürümleri üzerinde geliştirilmiş olanağı sağlayabilir. Bu yeni davranış uyarısı C4720 örneklerini yeni ve daha sık verilen sonuçlanabilir.  
  
    ```Output  
    warning C4720: unreachable code  
    ```  
  
     Çoğu durumda, bu uyarı yalnızca iyileştirmeler derlenirken verilebilecek, bu yana iyileştirmeleri satır içi daha işlev çağrıları, gereksiz kod ortadan kaldırmak veya aksi halde belirli kodun ulaşılamaz olduğunu belirlemek mümkün kılar. Uyarı C4720 yeni örneklerini içinde sıkça gerçekleşen gözlenmiştir **try/catch** engeller, özellikle kullanımı ile ilgili [std::find](assetId:///std::find?qualifyHint=False&autoUpgrade=True).  
  
     Örnek (önce)  
  
    ```cpp  
    try  
    {  
        auto iter = std::find(v.begin(), v.end(), 5);  
    }  
    catch (...)  
    {  
        do_something();   // ok  
    }  
    ```  
  
     Örnek (sonra)  
  
    ```cpp  
    try  
    {  
        auto iter = std::find(v.begin(), v.end(), 5);  
    }  
    catch (...)  
    {  
        do_something();   // warning C4702: unreachable code  
    }  
    ```  
  
###  <a name="VS_Update2"></a> Güncelleştirme 2'de uyumluluk geliştirmeleri  
  
- **Kısmi ifade SFINAE desteği sonucunda ek uyarılar ve hatalar verilebilir**  
  
     Önceki derleyici sürümleri ifadelerinin içinde belirli bir türde değil ayrıştırma **decltype** tanımlayıcıları ifade SFINAE desteği eksikliği nedeniyle. Bu eski davranışı yanlış ve C++ standartlarına uygun değil. Derleyici artık bu deyimler ayrıştırır ve kısmi ifade SFINAE sürekli uyumluluk geliştirmeleri nedeniyle desteği vardır. Sonuç olarak, derleyici artık uyarı verir ve derleyicinin önceki sürümlerini değil ayrıştırma ifadelerinde hatalar bulundu.  
  
     Bu yeni davranış ayrıştırmak için ne zaman bir **decltype** sorunları derleyici hatası C2039 sonucunda henüz bildirilmedi, derleyici bir türü içeren bir ifade.  
  
    ```Output  
    error C2039: 'type': is not a member of '`global namespace''  
    ```  
  
     Örnek 1: bildirilmemiş bir türü (önce) kullanın  
  
    ```cpp  
    struct s1  
    {  
        template < typename T>  
        auto f() - > decltype(s2< T> ::type::f());  // error C2039  
  
        template< typename>  
        struct s2 {};  
    }  
    ```  
  
     Örnek 1 (sonra)  
  
    ```cpp  
    struct s1  
    {  
        template < typename>  // forward declare s2struct s2;   
  
            template < typename T>  
        auto f() - > decltype(s2< T> ::type::f());  
  
        template< typename>  
        struct s2 {};  
    }  
    ```  
  
     Bu yeni davranış ayrıştırmak için ne zaman bir **decltype** gerekli kullanımını eksik ifade **typename** anahtar sözcüğü bir tür, derleyici bağımlı bir ad olduğunu belirtmek için derleyici C4346 uyarı sorunları Derleyici Hatası C2923 birlikte.  
  
    ```Output  
    warning C4346: 'S2<T>::Type': dependent name is not a type  
    ```  
  
    ```Output  
    error C2923: 's1': 'S2<T>::Type' is not a valid template type argument for parameter 'T'  
    ```  
  
     Örnek 2: bağımlı adı (önce) bir tür değil.  
  
    ```cpp  
    template < typename T>  
    struct s1  
    {  
        typedef T type;  
    };  
  
    template < typename T>  
    struct s2  
    {  
        typedef T type;  
    };  
  
    template < typename T>  
    T declval();  
  
    struct s  
    {  
        template < typename T>  
        auto f(T t) - > decltype(t(declval< S1< S2< T> ::type> ::type> ()));  // warning C4346, error C2923  
    };  
    ```  
  
     Örnek 2 (sonra)  
  
    ```cpp  
    template < typename T> struct s1 { ... };  // as above  
    template < typename T> struct s2 { ... };  // as above  
  
    template < typename T>  
    T declval();  
  
    struct s  
    {  
        template < typename T>  
        auto f(T t) - > decltype(t(declval< S1< typename S2< T> ::type> ::type> ()));  
    };  
    ```  
  
- `volatile` **üye değişkenleri örtük olarak tanımlı oluşturucular ve atama işleçleri engelle**  
  
     Önceki derleyici sürümleri sahip bir sınıfı izin **geçici** varsayılan üye değişkenleri kopyalama/taşıma oluşturucuları ve kopyalama/taşıma atama işleçleri otomatik olarak oluşturulan varsayılan. Bu eski davranışı yanlış ve C++ standartlarına uygun değil. Derleyici artık sahip bir sınıf göz önünde bulundurur **geçici** Önemsiz yapım ve otomatik olarak oluşturulan varsayılan uygulamaları bu işleçlerin önleyen atama işleçleri için üye değişkenleri. Bu tür bir sınıfının bir birleşim (veya bir sınıf içinde anonim birleşim) üyesi olduğunda, kopyalama/taşıma oluşturucuları ve kopyalama/taşıma atama işleçleri union (veya unonymous union içeren sınıfın) örtük olarak silindi olarak tanımlanır. Oluşturmak veya bunları açıkça tanımlamadan UNION (veya anonim birleşim içeren sınıf) kopyalama girişimi hatayla ve derleyici sorunları derleyici hatası C2280 sonuç olarak.  
  
    ```Output  
    error C2280: 'B::B(const B &)': attempting to reference a deleted function  
    ```  
  
     Örnek (önce)  
  
    ```cpp  
    struct A  
    {  
        volatile int i;  
        volatile int j;  
    };  
  
    extern A* pa;  
  
    struct B  
    {  
        union  
        {  
            A a;  
            int i;  
        };  
    };  
  
    B b1{ *pa };  
    B b2(b1);  // error C2280  
    ```  
  
     Örnek (sonra)  
  
    ```cpp  
    struct A  
    {  
        int i; int j;   
    };  
  
    extern volatile A* pa;  
  
    A getA()  // returns an A instance copied from contents of pa  
    {  
        A a;  
        a.i = pa - > i;  
        a.j = pa - > j;  
        return a;  
    }  
  
    struct B;  // as above  
  
    B b1{ GetA() };  
    B b2(b1);  // error C2280  
    ```  
  
- **Statik üye işlevleri cv niteleyicileri desteklemez.**  
  
     Visual Studio 2015'ın önceki sürümlerini cv niteleyicileri sağlamak statik üye işlevlerinde izin. Bu Visual Studio 2015 ve Visual Studio 2015 güncelleştirme 1'teki bir gerileme nedeniyle, davranıştır; Visual Studio 2013 ve derleyicinin önceki sürümleri bu şekilde yazılmış kod reddeder. Visual Studio 2015 ve Visual Studio 2015 güncelleştirme 1 davranışını yanlış ve C++ standardı için uygun değil.  Visual Studio 2015 güncelleştirme 2, bu şekilde yazılmış kod reddeder ve bunun yerine derleyici hatası C2511 verir.  
  
    ```Output  
    error C2511: 'void A::func(void) const': overloaded member function not found in 'A'  
    ```  
  
     Örnek (önce)  
  
    ```cpp  
    struct A  
    {  
        static void func();  
    };  
  
    void A::func() const {}  // C2511  
    ```  
  
     Example(After)  
  
    ```cpp  
    struct A  
    {  
        static void func();  
    };  
  
    void A::func() {}  // removed const  
    ```  
  
- **Enum İleri dönük bildirimi WinRT kodunda izin verilmiyor** (etkiler `/ZW` yalnızca)  
  
     Windows çalışma zamanı (WinRT) izin vermeyen için derlenmiş kod **enum** türleri için .net yönetilen C++ kodu derlendiğinde İleri, benzer şekilde bildirilmesi için Framework kullanarak `/clr` derleyici anahtarı. Bu, davranıştır boyutu bir numaralandırmanın her zaman bilinen ve doğru şekilde WinRT türü sisteme öngörülen sağlar. Derleyici, bu şekilde yazılmış kod reddeder ve derleyici hatası c2599 arasındaki derleyici hatası C3197 birlikte verir.  
  
    ```Output  
    error C2599: 'CustomEnum': the forward declaration of a WinRT enum is not allowed  
    ```  
  
    ```Output  
    error C3197: 'public': can only be used in definitions  
    ```  
  
     Örnek (önce)  
  
    ```cpp  
    namespace A {  
        public enum class CustomEnum : int32;  // forward declaration; error C2599, error C3197  
    }  
  
    namespace A {  
        public enum class CustomEnum : int32  
        {  
            Value1  
        };  
    }  
  
    public ref class Component sealed  
    {  
    public:  
        CustomEnum f()  
        {  
            return CustomEnum::Value1;  
        }  
    };  
    ```  
  
     Örnek (sonra)  
  
    ```cpp  
              // forward declaration of CustomEnum removed  
    namespace A {  
        public enum class CustomEnum : int32  
        {  
            Value1  
        };  
    }  
  
    public ref class Component sealed  
    {  
    public:  
        CustomEnum f()  
        {  
            return CustomEnum::Value1;  
        }  
    };  
    ```  
  
- **Aşırı yüklenmiş üye olmayan işleç yeni ve delete işleci bildirilemez satır içi** (düzey 1 (`/W1`)-varsayılan)  
  
     Üye olmayan işleç yeni ve işleç delete işlevleri satır içi bildirildiğinde önceki derleyici sürümleri bir uyarı vermek değil. Bu şekilde yazılmış kodu hatalı oluşturulmuş (tanılama gerekli) ve bellek kaynaklanan sorunlar uyumsuz yeni ve delete tanı koymak güç olabilir (özellikle boyutlandırılmış ayırmayı kaldırma ile birlikte kullanıldığında) işleçleri neden olabilir. Derleyici artık derleyici bu şekilde yazılmış kodu belirlemenize yardımcı olması için C4595 uyarı verir.  
  
    ```Output  
    warning C4595: 'operator new': non-member operator new or delete functions may not be declared inline  
    ```  
  
     Örnek (önce)  
  
    ```cpp  
    inline void* operator new(size_t sz)  // warning C4595  
    {  
        ...  
    }  
    ```  
  
     Örnek (sonra)  
  
    ```cpp  
    void* operator new(size_t sz)  // removed inline  
    {  
        ...  
    }  
    ```  
  
     Bu şekilde yazılmış kod çözme operatör tanımlarının dışında bir üstbilgi dosyası ve karşılık gelen bir kaynak dosyasına taşınması gerekebilir.  
  
###  <a name="VS_Update3"></a> Güncelleştirme 3, uyumluluk geliştirmeleri  
  
- **Std::is_convertable otomatik atanmasını artık algılar** (standart kitaplığı)  
  
     Önceki sürümlerini `std::is_convertable` türü niteliğine, kopya Oluşturucu silindiğinde bir sınıf türünün otomatik atanmasını veya özel doğru algılamadı. Şimdi, `std::is_convertable<>::value` düzgün ayarlandığından **false** silindiğinde veya özel kopya Oluşturucu sınıf türünde uygulandığında.  
  
     Bu değişiklikle ilişkili hiçbir derleyici tanılama yoktur.  
  
     Örnek  
  
    ```cpp  
    #include <type_traits>  

    class X1  
    {  
                public:  
                X1(const X1&) = delete;  
                };  
  
    class X2  
    {  
                private:  
                X2(const X2&);  
                };  
  
    static_assert(std::is_convertible<X1&, X1>::value, "BOOM");static_assert(std::is_convertible<X2&, X2>::value, "BOOM");  
    ```  
  
     Derleyicinin önceki sürümlerinde, çünkü bu örnek altındaki statik onaylar geçirmek `std::is_convertable<>::value` yanlış ayarlandı **true**. Şimdi, `std::is_convertable<>::value` düzgün ayarlandığından **false**, statik bir onayları çökmesine neden olur.  
  
- **Varsayılan veya önemsiz copy silindi ve taşıma oluşturucuları saygı erişim tanımlayıcıları**  
  
     Derleyicinin önceki sürümlerini değil varsayılan yapılmış veya silinmiş bir önemsiz copy erişim belirleyici denetleyin ve bunları çağrılmasına izin vermeden önce taşıma oluşturucuları. Bu eski davranışı yanlış ve C++ standartlarına uygun değil. Bazı durumlarda, bu eski davranışı sessiz hatalı kod oluşturma, beklenmeyen çalışma zamanı davranışları kaynaklanan riski oluşturuldu. Derleyici artık varsayılan olarak ayarlanmış veya silinmiş bir önemsiz copy erişim belirleyici denetler ve taşıma oluşturucuları volat pouze jednou olup olmadığını ve değilse, sonuç olarak C2248 uyarı sorunları derleyici, belirlemek için.  
  
    ```Output  
    error C2248: 'S::S' cannot access private member declared in class 'S'  
    ```  
  
     Örnek (önce)  
  
    ```cpp  
    class S {  
    public:  
        S() = default;  
    private:  
        S(const S&) = default;  
    };  
  
    void f(S);  // pass S by value  
  
    int main()  
    {  
        S s;  
        f(s);  // error C2248, can't invoke private copy constructor  
    }  
    ```  
  
     Örnek (sonra)  
  
    ```cpp  
    class S {  
    public:  
        S() = default;  
    private:  
        S(const S&) = default;  
    };  
  
    void f(const S&);  // pass S by reference  
  
    int main()  
    {  
        S s;  
        f(s);   
    }  
    ```  
  
- **Öznitelik atanmış ATL kodu desteğini kullanımdan** (düzey 1 (`/W1`)-varsayılan)  
  
     ATL kodu kullanıldığında artık desteklenen derleyicinin önceki sürümlerini öznitelikli. Öznitelik atanmış ATL desteğini kaldırmanın sonraki aşamaya olarak kod [Visual Studio 2008'de başlangıcından](https://msdn.microsoft.com/library/bb384632\(v=vs.90\).aspx), öznitelik atanmış ATL kodu kullanıldığında artık kullanımdan kaldırıldı. Derleyici artık derleyici bu tür bir kullanım dışı kod belirlemenize yardımcı olması için C4467 uyarı verir.  
  
    ```Output  
    warning C4467: Usage of ATL attributes is deprecated  
    ```  
  
     Öznitelik atanmış ATL kodu desteği derleyicinin kaldırılana kadar kullanmaya devam etmek istiyorsanız, bu uyarıyı geçirerek devre dışı bırakabilirsiniz `/Wv:18` veya `/wd:4467` ekleyerek veya derleyici komut satırı bağımsız değişkenleri `#pragma warning(disable:4467)` , kaynak kodunuzdaki.  
  
     Örnek 1 (önce)  
  
    ```cpp  
              [uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]  
    class A {};  
    ```  
  
     Örnek 1 (sonra)  
  
    ```cpp  
    __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) A {};  
    ```  
  
     Bazen gerekir veya bir IDL oluşturmak istediğiniz kullanımı önlemek için aşağıdaki örnek kod gibi ATL öznitelikleri kullanım dışı  
  
     Örnek 2 (önce)  
  
    ```cpp  
    [emitidl];  
    [module(name = "Foo")];  
  
    [object, local, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]  
    __interface ICustom {  
        HRESULT Custom([in] long l, [out, retval] long *pLong);  
        [local] HRESULT CustomLocal([in] long l, [out, retval] long *pLong);  
    };  
  
    [coclass, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]  
    class CFoo : public ICustom  
    {  
        // ...  
    };  
    ```  
  
     İlk olarak, *.idl dosya oluşturun; oluşturulan vc140.idl dosyası almak için kullanılabilir bir \*arabirimleri ve ek açıklamaları içeren .idl dosyası.  
  
     Ardından, C++ arabirim tanımlarını oluşturulduğundan emin olmak için yapınıza MIDL adımı ekleyin.  
  
     Örnek 2 IDL (sonra)  
  
    ```cpp  
    import "docobj.idl";  
  
    [  
        object, local, uuid(9e66a290 - 4365 - 11d2 - a997 - 00c04fa37ddb)  
    ]  
  
    interface ICustom : IUnknown {  
        HRESULT  Custom([in] long l, [out, retval] long *pLong);  
        [local] HRESULT  CustomLocal([in] long l, [out, retval] long *pLong);  
    };  
  
    [version(1.0), uuid(29079a2c - 5f3f - 3325 - 99a1 - 3ec9c40988bb)]  
    library Foo  
    {  
        importlib("stdole2.tlb");  
    importlib("olepro32.dll");  
    [  
        version(1.0),  
        appobject,uuid(9e66a294 - 4365 - 11d2 - a997 - 00c04fa37ddb)  
    ]  
  
    coclass CFoo {  
        interface ICustom;  
    };  
    }  
    ```  
  
     Ardından, ATL doğrudan uygulama dosyasında, aşağıdaki örnek kod olduğu gibi kullanın.  
  
     Örnek 2 uygulaması (sonra)  
  
    ```cpp  
    #include <idl.header.h>  
    #include <atlbase.h>  
  
    class ATL_NO_VTABLE CFooImpl :  
        public ICustom,  
        public ATL::CComObjectRootEx< CComMultiThreadModel>  
    {  
    public:  
        BEGIN_COM_MAP(CFooImpl)  
            COM_INTERFACE_ENTRY(ICustom)  
        END_COM_MAP()  
    };  
    ```  
  
- **Önceden derlenmiş üst bilgi (PCH) dosyaları ve eşleşmeyen #include** (yalnızca etkiler `/Wall` `/WX`)  
  
     Önceki derleyici sürümleri kabul eşleşmeyen `#include` yönergeleri arasındaki kaynak dosyalarında `-Yc` ve `-Yu` kullanırken derlemeleri önceden derlenmiş üst bilgi (PCH) dosyaları. Bu şekilde yazılmış kod artık derleyici tarafından kabul edilir.   Derleyicinin CC4598 belirlemenize yardımcı olması için uyarı sorunları derleyici eşleşmeyen artık `#include` PCH dosyalarını kullanırken yönergeleri.  
  
    ```Output  
    warning C4598: 'b.h': included header file specified for Ycc.h at position 2 does not match Yuc.h at that position  
    ```  
  
     Örnek (önce):  
  
     X.cpp (-Ycc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h"  
    #include "c.h"  
    ```  
  
     Z.cpp (-Yuc.h)  
  
    ```cpp  
    #include "b.h"  
    #include "a.h"  // mismatched order relative to X.cpp  
    #include "c.h"  
    ```  
  
     Örnek (sonra)  
  
     X.cpp (-Ycc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h"   
    #include "c.h"  
    ```  
  
     Z.cpp (-Yuc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h" // matched order relative to X.cpp  
    #include "c.h"  
    ```  
  
- **Önceden derlenmiş üst bilgi (PCH) dosyaları ve eşleşmeyen ekleme kodu dizinleri** (yalnızca etkiler `/Wall` `/WX`)  
  
     Kabul edilen derleyicinin önceki sürümlerini eşleşmeyen içeren dizin (`-I`) arasındaki derleyici komut satırı bağımsız değişkenleri `-Yc` ve `-Yu` kullanırken derlemeleri önceden derlenmiş üst bilgi (PCH) dosyaları. Bu şekilde yazılmış kod artık derleyici tarafından kabul edilir.   Derleyicinin CC4599 belirlemenize yardımcı olması için uyarı sorunları derleyici eşleşmeyen artık içeren dizin (`-I`) PCH dosyalarını kullanırken komut satırı bağımsız değişkenleri.  
  
    ```Output  
    warning C4599: '-I..' : specified for Ycc.h at position 1 does not match Yuc.h at that position  
    ```  
  
     Örnek (önce)  
  
    ```ms-dos  
    cl /c /Wall /Ycc.h -I.. X.cpp  
    cl /c /Wall /Yuc.h Z.cpp  
    ```  
  
     Örnek (sonra)  
  
    ```ms-dos  
    cl /c /Wall /Ycc.h -I.. X.cpp  
    cl /c /Wall /Yuc.h -I.. Z.cpp  
    ```  
  
## <a name="visual-studio-2013-conformance-changes"></a>Visual Studio 2013 uyumluluğu değişiklikleri  
  
### <a name="compiler"></a>Derleyici  
  
- **Son** anahtar sözcüğü artık burada, Daha önceleri derlendiği çözülmemiş simge hatası üretmektedir:  
  
    ```cpp  
    struct S1 {  
        virtual void f() = 0;  
    };  
  
    struct S2 final : public S1 {  
        virtual void f();  
    };  
  
    int main(S2 *p)  
    {  
        p->f();  
    }  
    ```  
  
     Önceki sürümlerde, çağrı olduğundan hata verilmiyordu bir **sanal** çağırın; Bununla birlikte, program çalışma zamanında kilitlenme. Artık, sınıfın son olduğu bilindiğinden bir bağlayıcı hatası verilmektedir. Bu örnekte, hatayı düzeltmek için tanımını içeren nesneye karşı bağlamanız `S2::f`.  
  
- Ad alanlarında arkadaş işlevlerini kullandığınızda, arkadaş ona başvuran veya derleyici artık ISO C++ standardı ile uyumlu olduğundan bir hata alırsınız. önce işlevini yeniden bildirmeniz gerekir. Örneğin, bu artık derlenmemektedir:  
  
    ```cpp  
    namespace NS {  
        class C {  
            void func(int);  
            friend void func(C* const) {}  
        };  
  
        void C::func(int) {  
            NS::func(this);  // error  
        }  
    }  
    ```  
  
     Bu kodu düzeltmek için bildirin **arkadaş** işlevi:  
  
    ```cpp  
    namespace NS {  
        class C {  
            void func(int);  
            friend void func(C* const) {}  
        };  
  
        void func(C* const);  // conforming fix  
  
        void C::func(int) {  
            NS::func(this);  
        }  
    ```  
  
- C++ standardı bir sınıfta açık özelleştirme izin vermez. Microsoft Visual C++ derleyicisi, bazı durumlarda, aşağıdaki örnekte gibi durumlarda izin verir, ancak derleyici ikinci işlevi birincinin bir özelleştirmesi olarak kabul etmediği için bir hata oluşturulur.  
  
    ```cpp  
    template < int N>  
    class S {  
    public:  
        template  void f(T& val);  
        template < > void f(char val);  
    };  
  
    template class S< 1>;  
    ```  
  
     Bu kodu düzeltmek için ikinci işlevi değiştirin:  
  
    ```cpp  
    template <> void f(char& val);  
    ```  
  
-   Derleyici, aşağıdaki örnekte iki işlev ayırt etmek artık çalışır ve bir hata verir:  
  
    ```cpp  
    template< typename T> void Func(T* t = nullptr);  
    template< typename T> void Func(...);  
  
    int main() {  
        Func< int>(); // error  
    }  
    ```  
  
     Bu kodu düzeltmek için çağrıyı netleştirin:  
  
    ```cpp  
    template< typename T> void Func(T* t = nullptr);  
    template< typename T> void Func(...);  
  
    int main() {  
        Func< int>(nullptr); // ok  
    }  
    ```  
  
- Derleyici ISO C ++ 11 ile uyumlu hale getirilmeden önce aşağıdaki kod derlenmekteydi ve neden `x` türüne çözülmesine **int**:  
  
    ```cpp  
    auto x = {0};  
    int y = x;  
    ```  
  
     Bu kod artık çözümler `x` bir tür `std::initializer_list<int>` ve sonraki satırda atamaya çalışan bir hataya neden olur `x` türüne **int**. (Varsayılan olarak herhangi bir dönüştürme yoktur.) Bu kodu düzeltmek için **int** değiştirilecek **otomatik**:  
  
    ```cpp  
    int x = {0};  
    int y = x;  
    ```  
  
- Sağ taraftaki değer türü Başlatılmakta olan soldaki değerin türünü eşleşmediğinde toplu başlatmaya artık izin verilmez ve C ++ 11 ISO standart olmadan çalışmaya Tekdüzen başlatma gerektirdiğinden bir hata verilir daraltma dönüştürmeleri. Daha önce bir daraltma dönüşümü kullanılabilir, biri ise bir [Derleyici Uyarısı (düzey 4) C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) uyarı hata yerine verilen.  
  
    ```cpp  
    int i = 0;  
    char c = {i}; // error  
    ```  
  
     Bu kodu düzeltmek için açık bir daraltma dönüşümü ekleyin:  
  
    ```cpp  
    int i = 0;  
    char c = {static_cast<char>(i)};  
    ```  
  
-   Aşağıdaki başlatmaya artık izin verilmez:  
  
    ```cpp  
    void *p = {{0}};  
    ```  
  
     Bu kodu düzeltmek için şu formlardan birini kullanın:  
  
    ```cpp  
    void *p = 0;  
    // or  
    void *p = {0};  
    ```  
  
- Ad arama değişti. Aşağıdaki kod, Visual Studio 2012 ve Visual Studio 2013 C++ derleyicisinde farklı çözümlenir:  
  
    ```cpp  
    enum class E1 { a };  
    enum class E2 { b };  
  
    int main()  
    {  
        typedef E2 E1;  
        E1::b;  
    }  
    ```  
  
     Visual Studio 2012'deki `E1` ifadesinde `E1::b` çözümlendi `::E1` genel kapsamda. Visual Studio 2013'te `E1` ifadesinde `E1::b` çözümler `typedef E2` tanımında `main()` ve türüne sahip `::E2`.  
  
- {1&gt;Nesne düzeni değişti.&lt;1} x64 üzerinde, bir sınıfın nesne düzeni önceki sürümlere göre değişebilmektedir. Varsa bir **sanal** işlevi ancak sahip bir taban sınıfı yoksa bir **sanal** işlevi, derleyicinin nesne modeli için bir işaretçi ekler bir **sanal** işlev tablosu veri üyesi düzeninden sonra. Başka bir deyişle, ilgili düzen her durumda en uygun düzen olmayabilir. Önceki sürümlerde, x64 yönelik bir iyileştirme düzeni sizin yerinize iyileştirmeye dener, ancak karmaşık kod durumlarında düzgün çalışması başarısız olduğundan, Visual Studio 2013'te kaldırıldı. Örneğin, aşağıdaki kodu düşünün:  
  
    ```cpp  
    __declspec(align(16)) struct S1 {  
    };  
  
    struct S2 {  
        virtual ~S2();  
        void *p;  
        S1 s;  
    };  
    ```  
  
- Visual Studio 2013, sonucunu `sizeof(S2)` x64 üzerinde 48'dir, ancak isteğe bağlı olarak önceki sürümlerde 32 olarak değerlendirir. Bunu 32 x64 için Visual Studio 2013'teki C++ derleyicisinde değerlendirmek için sahip işlevsiz bir temel sınıf ekleyin. bir **sanal** işlevi:  
  
    ```cpp  
    __declspec(align(16)) struct S1 {  
    };  
  
    struct dummy {  
        virtual ~dummy() {}  
    };  
    struct S2 : public dummy {  
        virtual ~S2();  
        void *p;  
        S1 s;  
    };  
    ```  
  
     Kodunuzda önceki bir sürümünü iyileştirmek için çalıştınız yerleri bulmak için bir derleyici sürümü ile birlikte kullanın. `/W3` derleyici seçeneği ve 4370 uyarısı. Örneğin:  
  
    ```cpp  
    #pragma warning(default:4370)  
  
    __declspec(align(16)) struct S1 {  
    };  
  
    struct S2 {  
        virtual ~S2();  
        void *p;  
        S1 s;  
    };  
    ```  
  
     Visual Studio 2013'ten önce bu kod şu ileti çıktısını verir: "C4370 Uyarı: 'S2': sınıfın düzeni önceki bir sürümünden daha iyi paketleme nedeniyle derleyici değişti".  
  
     X86 derleyici tüm derleyici sürümlerinde aynı optimum altında Düzen sorunu vardır. Örneğin, bu kod x86 için derlenirse:  
  
    ```cpp  
    struct S {  
        virtual ~S();  
        int i;  
        double d;  
    };  
    ```  
  
     Sonucu `sizeof(S)` 24'tür. Bununla birlikte, az önce x64 için sözü edilen geçici çözümü kullanırsanız bu sonuç 16'ya indirilebilir:  
  
    ```cpp  
    struct dummy {  
        virtual ~dummy() {}  
    };  
  
    struct S : public dummy {  
        virtual ~S();  
        int i;  
        double d;  
    };  
    ```  
  
### <a name="standard-library"></a>Standart Kitaplık  
Visual Studio 2013 C++ derleyicisi, uyuşmazlıkları Visual Studio 2010'da uygulanmıştır, _ıterator_debug_level uyuşmazlıklarını ve RuntimeLibrary uyuşmazlıklarını algılar. Bu durum, derleyici seçenekleri `/MT` (statik sürüm) `/MTd` (statik hata ayıklama), `/MD` (dinamik sürüm) ve `/MDd` (dinamik hata ayıklama) karıştırılır.  
  
- Kodunuzu önceki yayındaki benzetilmiş diğer ad şablonlarını kabul ederse, bunu değiştirmeniz gerekir. Örneğin, yerine, `allocator_traits<A>::rebind_alloc<U>::other`başvurduysanız, artık `allocator_traits<A>::rebind_alloc<U>`. Ancak `ratio_add<R1, R2>::type` artık gerekli ve biz öneriyor olmamıza sunulmuştur `ratio_add<R1, R2>`, eski hala çünkü derleyeceği `ratio<N, D>` , zaten azaltılmışsa aynı türde olacak bir oran, bir "tür" typedef olması gereklidir.  
  
- Kullanmalısınız `#include <algorithm>` çağırdığınızda `std::min()` veya `std::max()`.  
  
- Önceki sürümün benzetilmiş, varolan kod kullanılan sabit listeleri kapsamlı, — geleneksel numaralandırmalarını ad alanlarına sarmalanmış numaralandırmalar — bunu değiştirmeniz gerekir. Örneğin, türü için başvurulan `std::future_status::future_status`başvurduysanız, artık `std::future_status`. Ancak, çoğu kod etkilenmez; Örneğin, `std::future_status::ready` derlenmeye devam eder.  
  
- `explicit operator bool()` işleç unspecified-bool-type() katı olur. `explicit operator bool()` Açık dönüştürmeler bool değerine izin verir — Örneğin, verilen `shared_ptr<X> sp`hem `static_cast<bool>(sp)` ve `bool b(sp)` geçerlidir — ve Boolean test edilebilir "bağlamsal dönüştürmeleri" bool — Örneğin, `if (sp)`, `!sp`, `sp &&` ne olursa olsun. Ancak, `explicit operator bool()` yüzden bool, örtük dönüşümlerini yasaklayabilir `bool b = sp;` ve bool dönüş türü düşünüldüğünde, diyemeyiz `return sp`.  
  
- Gerçek bağımsız değişken içeren şablonlar uygulanır, _varıadıc_max ve ilgili makroların bir etkisi yoktur. Halen _VARIADIC_MAX öğesini tanımlıyorsanız, sadece yok sayılır. Benzetilmiş değişen sayıda bağımsız değişken içeren şablonları farklı bir şekilde desteklemeye yönelik makro makinemizi kabul ettiyseniz, kodunuzu değiştirmeniz gerekir.  
  
- Sıradan anahtar sözcüklere ek olarak, C++ Standart Kitaplığı üst bilgileri artık makro oluşturulmasını engellemektedir bağlama duyarlı anahtar sözcükler yasaklayabilme **geçersiz kılma** ve **son**.  
  
- reference_wrapper/ref()/cref() şimdi geçici nesnelere bağlanmayı yasaklar.  
  
- \<rastgele > artık, derleme zamanı önkoşulları kesinlikle zorlar.  
  
- Çeşitli C++ Standart Kitaplığı türü nitelikler "T tam bir tür olacaktır" önkoşuluna sahiptir. Derleyici artık bunu daha katı şekilde zorladığı halde, her durumda zorla kabul ettiremeyebilir. (C++ Standart Kitaplığı önkoşulu ihlalleri tanımlanmamış davranışı tetiklediğinden, standart, zorlamayı garanti etmez.)  
  
- C++ Standart Kitaplığı desteklemediği `/clr:oldSyntax`.  
  
- C ++ 11 belirtimi common_type <> sahip beklenmedik ve istenmeyen sonuçlara; common_type özellikle kolaylaştırır\<int, int >:: dönüş int türüne & &. Bu nedenle, derleyici common_type getiren için önerilen çözümü kitaplık çalışma grubu sorunu 2141, uygulayan\<int, int = "" >:: dönüş tamsayı türü  
  
     Bir yan etkisi bu değişiklik, kimlik durumu artık çalışmaz (common_type\<T > türü T her zaman sonuç vermez). Bu Önerilen Çözünürlük ile uyumludur, ancak önceki çalışma biçimine dayalı kodları keser.  
  
     Bir kimlik türü niteliğine gereksinim duyarsanız standart dışı kullanmayın `std::identity` içinde tanımlanan \<type_traits > için çalışmaz çünkü \<void >. Bunun yerine, gereksinimlerinize uyan kendi kimlik türü ayırt edici niteliğini uygulayın. Örnek buradadır:  
  
    ```cpp  
    template < typename T> struct Identity {  
        typedef T type;  
    };  
    ```  
  
### <a name="mfc-and-atl"></a>MFC ve ATL  
  
- **Yalnızca Visual Studio 2013**: MFC MBCS kitaplığı dahil değildir Visual Studio'da Unicode çok popüler olduğundan ve MBCS kullanımı önemli ölçüde azaldığından. Yeni denetimlerin ve iletilerin çoğu salt Unicode olduğundan, bu değişiklik aynı zamanda MFC'yi Windows SDK ile daha paralel halde tutar. MFC MBCS kitaplığını kullanmaya devam etmeniz gerekiyorsa, Bununla birlikte, MSDN İndirme Merkezi'nden indirebilirsiniz [Visual Studio 2013 için çok baytlı MFC Kitaplığı](https://www.microsoft.com/en-us/download/details.aspx?id=40770). Visual C++ Yeniden Dağıtılabilir Paketi'nde bu kitaplık halen yer almaktadır.  (Not: MBCS DLL Visual Studio 2015 ve sonraki sürümlerde C++ Kurulum bileşenlerini dahil).
  
- MFC Şeridi için erişilebilirlik değişti.  Bir tek düzeyli mimari yerine artık hiyerarşik bir mimari yoktur. Çağırarak eski davranışı hala kullanabilirsiniz `CRibbonBar::EnableSingleLevelAccessibilityMode()`.  
  
- `CDatabase::GetConnect` yöntemi kaldırıldı. Güvenliği artırmak için bağlantı dizesi artık depolanan şifrelenir ve yalnızca gerektiğinde; şifresi düz metin olarak döndürülemez.  Dize kullanılarak elde edilebilir `CDatabase::Dump` yöntemi.  
  
- İmza `CWnd::OnPowerBroadcast` değiştirilir. Bu ileti işleyicisinin imzası ikinci parametre olarak bir LPARAM alacak şekilde değiştirilir.  
  
- İmzalar, ileti işleyicilerini barındıracak şekilde değiştirilir. Aşağıdaki işlevlerin parametre listeleri yeni eklenen ON_WM_* ileti işleyicilerini kullanacak şekilde değiştirilmiştir:  
  
    - `CWnd::OnDisplayChange` böylece yeni gt; on_wm_dısplaychange & makrosu ileti eşlemede kullanılabilir (WPARAM, LPARAM) yerine (UINT, int, int) değiştirdi.  
  
    - `CFrameWnd::OnDDEInitiate` böylece yeni ON_WM_DDE_INITIATE makrosu ileti eşlemede kullanılabilir (WPARAM, LPARAM) yerine (CWnd *, UINT, birim) değiştirdi.  
  
    - `CFrameWnd::OnDDEExecute` böylece yeni ON_WM_DDE_EXECUTE makrosu ileti eşlemede kullanılabilir (CWnd * için tanıtıcı) (WPARAM, LPARAM) yerine değiştirildi.  
  
    - `CFrameWnd::OnDDETerminate` böylece yeni gt; on_wm_dde_termınate & makrosu ileti eşlemede kullanılabilir (CWnd *) için (WPARAM, LPARAM) yerine parametre olarak değiştirildi.  
  
    - `CMFCMaskedEdit::OnCut` böylece yeni gt; ON_WM_CUT makrosu ileti eşlemede kullanılabilir parametre yok (WPARAM, LPARAM) yerine değiştirildi.  
  
    - `CMFCMaskedEdit::OnClear` böylece yeni ON_WM_CLEAR makrosu ileti eşlemede kullanılabilir parametre yok (WPARAM, LPARAM) yerine değiştirildi.  
  
    - `CMFCMaskedEdit::OnPaste` böylece yeni ON_WM_PASTE makrosu ileti eşlemede kullanılabilir parametre yok (WPARAM, LPARAM) yerine değiştirildi.  
  
- \#MFC üstbilgi dosyalarındaki ifdefs kaldırılır. Çok sayıda #ifdefs MFC başlık dosyaları ilgili desteklenmeyen Windows sürümleri (WINVER &lt; 0x0501) kaldırılır.  
  
- ATL DLL (atl120.dll) kaldırıldı. ATL artık, üst bilgiler ve statik kitaplık (atls.lib) olarak sağlanmaktadır.  
  
- Atlsd.lib, atlsn.lib ve atlsnd.lib kaldırıldı. Atls.lib artık, karakter kümesi bağımlılıkları veya hata ayıklamaya/yayınlamaya özgü kod içermez. Unicode/ANSI ve hata ayıklama/yayınlama için aynı çalıştığından, kitaplığın yalnızca tek bir sürümü gereklidir.  
  
- ATL DLL ile birlikte ATL/MFC izleme aracı kaldırılır ve izleme mekanizması basitleşti. `CTraceCategory` Oluşturucusu şimdi bir parametre (kategori adı) ve izleme makroları CRT hata ayıklama raporlama işlevlerini çağırın.  
  
## <a name="visual-c-2012-breaking-changes"></a>Visual C++ 2012 bozucu değişiklikler  
  
### <a name="compiler"></a>Derleyici  
  
- `/Yl` Derleyici seçeneği değiştirildi. Varsayılan olarak, derleyici, bu seçenek, belirli koşullar altında LNK2011 hatalara yol açabilir kullanır. Daha fazla bilgi için [/Yl (ekleme PCH başvurusu hata ayıklama kitaplığı için)](../build/reference/yl-inject-pch-reference-for-debug-library.md).  
  
- Derlenmiş kodda `/clr`, **enum** class anahtar sözcüğü, bir C ++ 11 sabit olmayan bir ortak dil çalışma zamanı (CLR) sabit listesi tanımlar. CLR enum tanımlamak için onun erişilebilirlik hakkında açık olması gerekir.  
  
- Şablon anahtar sözcüğü açıkça bir bağımlı adı (Standart C++ dil uyumluluğu) belirsizliğini ortadan kaldırmak için kullanın. Aşağıdaki örnekte, vurgulanan şablon anahtar sözcüğü belirsizliği çözmek için zorunludur. Daha fazla bilgi için [bağımlı türler için ad çözümleme](../cpp/name-resolution-for-dependent-types.md).  
  
    ```cpp  
    template < typename X = "", typename = "" AY = "">  
    struct Container { typedef typename AY::template Rebind< X> ::Other AX; };  
    ```  
  
- Tür float, sabit ifade artık aşağıdaki örnekte gösterildiği gibi bir şablon bağımsız değişkeni izin verilmez.  
  
    ```cpp  
    template<float n=3.14>  
    struct B {};  // error C2993: 'float': illegal type for non-type template parameter 'n'  
    ```  
  
- Derlenmiş kod `/GS` komut satırı seçeneği ve, olan bir kapalı tek güvenlik açığı neden olabilir, çalışma zamanında, sonlandırma işlemek için aşağıdaki sözde kod örneğinde gösterildiği gibi.  
  
    ```cpp  
    char buf[MAX]; int cch; ManipulateString(buf, &cch); // ... buf[cch] = '\0'; // if cch >= MAX, process will terminate  
    ```  
  
- Yapılar için SSE2 değiştirildiğinde x86 varsayılan mimarisi; Bu nedenle, derleyici SSE yönergeleri yayabilir ve XMM yazmaçlarında kayan nokta hesaplamalar gerçekleştirmek için kullanır. Önceki davranışa dönmek istiyorsanız, ardından kullanmak `/arch:IA32` mimarisi IA32 belirtmek için derleyici bayrağı.  
  
- Derleyici uyarılarını verebileceği [Derleyici Uyarısı (düzey 4) C4703](../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md) ve C4701 burada daha önce bu belirtmiyor. Derleyici, daha güçlü denetimler başlatılmamış yerel değişkenler işaretçi türü kullanımı için geçerlidir.  
  
- Ne zaman yeni bir bağlayıcı bayrağı `/HIGHENTROPYVA` belirtilirse, Windows 8 64-bit adresini döndürmek bellek ayırmaları genellikle neden olur. (Windows 8 önce böyle ayırmaları daha sık 2 GB'tan daha az olan adresler döndürdü.) Bu, varolan kodda işaretçi kesilmesi hatalar ortaya çıkarabilir. Varsayılan olarak, bu anahtar açıktır. Bu davranışı devre dışı bırakmak için bu seçeneği belirtin `/HIGHENTROPYVA:NO`.  
  
- Yönetilen derleme (Visual Basic / C#) da destekler `/HIGHENTROPYVA` Yönetilen derlemeler için.  Ancak, bu durumda, `/HIGHENTROPYVAswitch` varsayılan olarak kapalıdır.  
  
### <a name="ide"></a>IDE  
  
- Windows Forms uygulamaları C +'da oluşturduğunuz değil öneririz ancak +/ CLI, bakım mevcut C + +/ CLI UI uygulamaları desteklenir. Bir Windows Forms uygulaması veya başka bir .NET kullanıcı Arabirimi uygulama oluşturmak varsa, C# veya Visual Basic kullanın. Kullanmak C + +/ CLI birlikte çalışabilirliği için yalnızca amacıyla.  
  
### <a name="parallel-patterns-library-and-concurrency-runtime-library"></a>Paralel Desen kitaplığı ve Eşzamanlılık Çalışma Zamanı Kitaplığı  
`SchedulerType` Numaralandırması `UmsThreadDefault` kullanım dışı bırakılmıştır. Belirtimi `UmsThreadDefault` kullanım dışı bir uyarı verir ve geri dahili olarak eşler `ThreadScheduler`.  
  
### <a name="standard-library"></a>Standart Kitaplık  
  
- C ++ 98/03 ve C ++ 11 standartları arasında bozucu değişiklik çağırmak için açık şablon bağımsız değişkenleri kullanarak `make_pair()` — olarak `make_pair<int, int>(x, y)` — genellikle Visual Studio 2012'de Visual c++ derleme yapmaz. Çözümü her zaman çağırmaktır `make_pair() `açık şablon bağımsız değişkenler olmadan — olarak `make_pair(x, y)`. Açık şablon bağımsız değişkenleri defeats işlevin amacı sağlama. Sonuçta elde edilen tür üzerinde kesin denetim gerektiren kullanırsanız `pair` yerine `make_pair` — olarak `pair<short, short>(int1, int2)`.  
  
- C ++ 98/03 ve C ++ 11 standartları arasında başka bir değişiklik: A örtük olarak dönüştürülebilir olduğunda B de C için örtük olarak dönüştürülebilir, ancak A, C, C ++ 98/03 ve Visual C++ 2010 izin örtük olarak dönüştürülebilir değil `pair<A, X>` (örtük olarak dönüştürülmesine veya açıkça) için `pair<C, X>`. (Bir tür, X, burada faiz ve bu çift ilk türüne özgü değildir değil.) C ++ 11 ve Visual Studio 2012 C++ derleyicisindeki bir C için örtük olarak dönüştürülebilir değil algılamak için bunlar aşırı yükleme çözünürlüğü çifti dönüştürme kaldırın. Bu, birçok senaryo için pozitif bir değişikliktir. Örneğin, aşırı yükleme `func(const pair<int, int>&)` ve `func(const pair<string, string>&)`ve çağırma `func()` ile `pair<const char *, const char *>` bu değişiklik ile derlenir. Ancak, bu değişiklik agresif çifti dönüştürmeleri yararlandı kod keser. Bu tür kod genellikle açıkça bir parçasını dönüştürme gerçekleştirerek düzeltilebilir — geçirerek gibi `make_pair(static_cast<B>(a), x)` bekleyen bir işleve `pair<C, X>`.  
  
- Visual C++ 2010 benzetimli variadic şablonları — Örneğin, `make_shared<T>(arg1, arg2, argN)`— bağımsız değişkenleri, aşırı yüklemeler ve uzmanlıkları out ile önişlemci makineler damgası tarafından 10, bir sınıra kadar. Visual Studio 2012'de, derleme sürelerini ve kullanıcıların çoğu için derleyicinin bellek tüketimini geliştirmek için 5 bağımsız değişkenler için bu sınır azaltılır. Ancak, _varıadıc_max açıkça proje genelinde 10 tanımlayarak önceki sınırı ayarlayabilirsiniz.  
  
- C ++ 11 17.6.4.3.1 [macro.names]/2 yasaklıyor makrosu engellemektedir anahtar sözcükler, C++ Standart Kitaplığı üst bilgiler dahil edilir. Bunlar makrosu ized anahtar sözcükleri algılayın, üst bilgileri artık derleyici hataları gösterin. (Bu kodu derlemek _ALLOW_KEYWORD_MACROS tanımlama verir, ancak biz kesinlikle bu kullanımı önerilmemektedir.) Üstbilgileri aygıtlarınızı kendilerini #pragma push_macro("new") / #undef yeni / #pragma pop_macro("new") kullanarak korumak için bir özel durum, varsayılan olarak, ized yeni makrosu izin verilir. Tam olarak bu ne adından da anlaşılacağı _ENFORCE_BAN_OF_MACRO_NEW tanımlama yapar.  
  
- Çeşitli iyileştirmeler ve hata ayıklama denetimlerini uygulamak için C++ Standart Kitaplığı uygulaması kasıtlı olarak Visual Studio sürümleri arasında ikili uyumluluğu keser (2005, 2008, 2010, 2012). C++ Standart Kitaplığı kullanıldığında, bu nesne dosyaları ve statik kitaplıklar bir ikili olarak (EXE veya DLL) farklı sürümler kullanılarak derlenmiş ve C++ Standart Kitaplığı nesneleri geçirme tarafından derlenmiş ikili dosyaları arasında engelliyor karıştırma engelliyor farklı sürümleri kullanılarak. Nesne dosyaları ve statik kitaplıklar karıştırma (C++ kullanılarak derlenmiş değerlerle Visual C++ 2010 kullanılarak derlenmiş C++ Standart Kitaplığı'nı kullanarak Visual Studio 2012'de derleyici _MSC_VER uyuşmazlığı, _MSC_VER olduğu ilgili bağlayıcı hataları yayar Derleyicinin ana sürümünü (Visual Studio 2012'deki Visual c++ 1700) içeren makrosu. Bu denetim DLL karmasını algılayamaz ve Visual C++ 2008 veya önceki bir sürümü içeren karmasını algılayamaz.  
  
- Visual Studio 2012'de C++ derleyicisi, _ıterator_debug_level uyuşmazlıkları Visual C++ 2010 içinde olan algılama ek olarak, çalışma zamanı kitaplığı uyuşmazlıkları algılar. Bu durum, derleyici seçeneklerinin `/MT` (statik sürüm) `/MTd` (statik hata ayıklama), `/MD` (dinamik sürüm) ve `/MDd` (dinamik hata ayıklama) karıştırılır.  
  
- `operator<()`, `operator>()`, `operator<=()`, ve `operator>=()` için daha önce sağlanan `std::unordered_map` ve `stdext::hash_map` aileleri kapsayıcıların, ancak kendi uygulamalarında gerçekten kullanışlı değildir. Bu standart işleçler, Visual Studio 2012'de Visual C++'da kaldırılmıştır. Ayrıca, uygulanması `operator==()` ve `operator!=()` için `std::unordered_map` ailesi karşılamak için genişletilmişse `stdext::hash_map` ailesi. (Kullanımını kaçınmanızı öneririz `stdext::hash_map` yeni kod ailesi.)  
  
- C ++ 11 22.4.1.4 [locale.codecvt] belirtir `codecvt::length()` ve `codecvt::do_length()` değiştirilebilir zamanınızı `stateT&` parametreleri, ancak Visual C++ 2010 sürdü `const stateT&`. Visual Studio 2012'de C++ derleyici alan `stateT&` standart tarafından zorunlu olarak. Bu sanal işlevi geçersiz kılma girişiminde herkes için önemli bir fark `do_length()`.  
  
### <a name="crt"></a>CRT  
  
- C çalışma zamanı (CRT) yığın, yeni kullanılır ve malloc(), özel artık. CRT, şimdi ise işlem yığınını kullanır. Bunun anlamı bir DLL kaldırıldığında yığın yok edilmez, CRT için kitaplıklarla statik bağlantılar oluşturabilir DLL tarafından ayrılan bellek emin olmak için onu kaldırıldı önce DLL kod temizlenir.  
  
- `iscsymf()` İşlevi negatif değerleri ile onaylar.  
  
- `threadlocaleinfostruct` Yapı değişiklikleri yerel işlevler uyum sağlayacak şekilde değişti.  
  
- İlgili yapı içleri sahip CRT işlevleri `memxxx()`, `strxxx()` ıntrin.h ' kaldırılır. Yalnızca bu işlevler için intrin.h içeriyorsa, karşılık gelen CRT üst bilgileri artık içermelidir.  
  
### <a name="mfc-and-atl"></a>MFC ve ATL  
  
- Fusion desteği (afxcomctl32.h); kaldırıldı Bu nedenle, afxcomctl32.h içinde tanımlanan tüm yöntemleri kaldırıldı. Üst bilgi dosyaları afxcomctl32.h ve afxcomctl32.inl silindi.  
  
- Adının değişip `CDockablePane::RemoveFromDefaultPaneDividier` için `CDockablePane::RemoveFromDefaultPaneDivider`.  
  
- İmzası değiştirildi `CFileDialog::SetDefExt` LPCTSTR; kullanmak için bu nedenle Unicode yapıları etkilenir.  
  
- Eski ATL İzleme kategorilerinin kaldırıldı.  
  
- İmzası değiştirildi `CBasePane::MoveWindow` gerçekleştirilecek bir `const CRect`.  
  
- İmzası değiştirildi `CMFCEditBrowseCtrl::EnableBrowseButton`.  
  
- Kaldırılan `m_fntTabs` ve `m_fntTabsBold` gelen `CMFCBaseTabCtrl`.  
  
- Bir parametre eklendi `CMFCRibbonStatusBarPane` oluşturucular. (Varsayılan parametredir ve bu nedenle kaynakta önemli değildir.)  
  
- Bir parametre eklendi `CMFCRibbonCommandsListBox` Oluşturucusu. (Varsayılan parametredir ve bu nedenle kaynakta önemli değildir.)  
  
- Kaldırılan `AFXTrackMouse` API (ve ilişkili Zamanlayıcı proc). Win32 kullanın `TrackMouseEvent` API yerine.  
  
- Bir parametre eklendi `CFolderPickerDialog` Oluşturucusu. (Varsayılan parametredir ve bu nedenle kaynakta önemli değildir.)  
  
- `CFileStatus` Yapı boyutu değişti: `m_attribute` üyesi için DWORD BAYTTAN değiştirildi (öğesinden döndürülen değerle eşleşecek şekilde `GetFileAttributes`).  
  
- `CRichEditCtrl` ve `CRichEditView` Unicode yapılarında RICHEDIT_CLASS (3.0 RichEdit Denetimi) yerine MSFTEDIT_CLASS (4.1 RichEdit Denetimi) kullanın.  
  
- Kaldırılan `AFX_GLOBAL_DATA::IsWindowsThemingDrawParentBackground` her zaman Windows Vista, Windows 7 ve Windows 8 üzerinde TRUE olduğundan.  
  
- Kaldırılan `AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable` her zaman Windows Vista, Windows 7 ve Windows 8 üzerinde TRUE olduğundan.  
  
- Kaldırılan `AFX_GLOBAL_DATA::DwmExtendFrameIntoClientArea`. Windows API doğrudan Windows Vista, Windows 7 ve Windows 8'i çağırın.  
  
- Kaldırılan `AFX_GLOBAL_DATA::DwmDefWindowProc`. Windows API doğrudan Windows Vista, Windows 7 ve Windows 8'i çağırın.  
  
- Yeniden adlandırılan `AFX_GLOBAL_DATA::DwmIsCompositionEnabled` için `IsDwmCompositionEnabled` ad çakışması ortadan kaldırmak için.  
  
- MFC iç zamanlayıcılar sayısı için tanımlayıcılar değiştirildi ve tanımları için afxres.h (AFX_TIMER_ID_ *) taşınır.  
  
- İmzası değiştirildi `OnExitSizeMove` ON_WM_EXITSIZEMOVE makrosu ile uyuşacak şekilde yöntemi:  
  
    - `CFrameWndEx`  
  
    - `CMDIFrameWndEx`  
  
    - `CPaneFrameWnd`  
  
- Adı ve imzası değiştirildi `OnDWMCompositionChanged` ON_WM_DWMCOMPOSITIONCHANGED makro kabul etmek için:  
  
    - `CFrameWndEx`  
  
    - `CMDIFrameWndEx`  
  
    - `CPaneFrameWnd`  
  
- İmzası değiştirildi `OnMouseLeave` ON_WM_MOUSELEAVE makrosu ile uyuşacak şekilde yöntemi:  
  
    - `CMFCCaptionBar`  
  
    - `CMFCColorBar`  
  
    - `CMFCHeaderCtrl`  
  
    - `CMFCProperySheetListBox`  
  
    - `CMFCRibbonBar`  
  
    - `CMFCRibbonPanelMenuBar`  
  
    - `CMFCRibbonRichEditCtrl`  
  
    - `CMFCSpinButtonCtrl`  
  
    - `CMFCToolBar` ReplaceThisText  
  
    - `CMFCToolBarComboBoxEdit`  
  
    - `CMFCToolBarEditCtrl`  
  
    - `CMFCAutoHideBar`  
  
- İmzası değiştirildi `OnPowerBroadcast` ON_WM_POWERBROADCAST makro kabul etmek için:  
  
    - `CFrameWndEx`  
  
    - `CMDIFrameWndEx`  
  
- İmzası değiştirildi `OnStyleChanged` ON_WM_STYLECHANGED makro kabul etmek için:  
  
    - `CMFCListCtrl`  
  
    - `CMFCStatusBar`  
  
- İç yöntemi olarak yeniden adlandırıldı `FontFamalyProcFonts` için `FontFamilyProcFonts`.  
  
- Çok sayıda genel statik kaldırıldı `CString` bellek ortadan kaldırmak için bazı durumlarda sızıntılarını nesneleri (yerine #defines), ve aşağıdaki sınıf üye değişkenleri:  
  
    - `CKeyBoardManager::m_strDelimiter`  
  
    - `CMFCPropertyGridProperty::m_strFormatChar`  
  
    - `CMFCPropertyGridProperty::m_strFormatShort`  
  
    - `CMFCPropertyGridProperty::m_strFormatLong`  
  
    - `CMFCPropertyGridProperty::m_strFormatUShort`  
  
    - `CMFCPropertyGridProperty::m_strFormatULong`  
  
    - `CMFCPropertyGridProperty::m_strFormatFloat`  
  
    - `CMFCPropertyGridProperty::m_strFormatDouble`  
  
    - `CMFCToolBarImages::m_strPngResType`  
  
    - `CMFCPropertyGridProperty::m_strFormat`  
  
- İmzası değiştirildi `CKeyboardManager::ShowAllAccelerators` ve Hızlandırıcı sınırlayıcı parametresi kaldırıldı.  
  
- Eklenen `CPropertyPage::GetParentSheet`hem de `CPropertyPage` sınıfı, bunun yerine çağrı `GetParent` üst olabilir ve doğru üst sayfası penceresini veya bir doya pencereye almak için `CPropertyPage`. Çağırmak için kodunuzu değiştirmeniz gerekebilir `GetParentSheet` yerine `GetParent`.  
  
- Olmayan dengesiz #pragma ATLBASE düzeltildi. H uyarıları hatalı devre dışı bırakılması neden oldu. Bu uyarılar artık doğru şekilde ATLBASE sonra etkinleştirilir. H ayrıştırılır.  
  
- D2D ilgili metotlar için _AFX_D2D_STATE AFX_GLOBAL_DATA taşındı:  
  
    - `GetDirectD2dFactory`  
  
    - `GetWriteFactory`  
  
    - `GetWICFactory`  
  
    - `InitD2D`  
  
    - `ReleaseD2DRefs`  
  
    - `IsD2DInitialized`  
  
    - `D2D1MakeRotateMatrix`  
  
    - Örneğin, çağırmak yerine `afxGlobalData.IsD2DInitialized`, çağrı `AfxGetD2DState->IsD2DInitialized`.  
  
- Eski ATL * kaldırıldı. \Atlmfc\include\ klasördeki dosyaların CPP.  
  
- Taşınan `afxGlobalData` CRT başlatma zaman karşılamak için isteğe bağlı yerine için başlatma `DLLMain` gereksinimleri.  
  
- Eklenen `RemoveButtonByIndex` yönteme `CMFCOutlookBarPane` sınıfı.  
  
- Düzeltilen `CMFCCmdUsageCount::IsFreqeuntlyUsedCmd` için `IsFrequentlyUsedCmd`.  
  
- Çeşitli örneklerini düzeltildi `RestoreOriginalstate` için `RestoreOriginalState (CMFCToolBar, CMFCMenuBar, CMFCOutlookBarPane)`.  
  
- Kullanılmayan yöntemlerinden kaldırıldı `CDockablePane`: `SetCaptionStyle`, `IsDrawCaption`, `IsHideDisabledButtons`, `GetRecentSiblingPaneInfo`, ve `CanAdjustLayout`.  
  
- Kaldırılan `CDockablePane` statik üye değişkenleri `m_bCaptionText` ve `m_bHideDisabledButtons`.  
  
- Bir geçersiz kılma eklenen `DeleteString` yönteme `CMFCFontComboBox`.  
  
- Kullanılmayan yöntemlerinden kaldırıldı `CPane`: `GetMinLength` ve `IsLastPaneOnLastRow`.  
  
- Yeniden adlandırılan `CPane::GetDockSiteRow(CDockingPanesRow *)` için `CPane::SetDockSiteRow`.  
  
## <a name="visual-c-2010-breaking-changes"></a>Visual C++ 2010 bozucu değişiklikler  
  
### <a name="compiler"></a>Derleyici  
  
- **Otomatik** anahtar sözcüğü, yeni bir varsayılan anlamı vardır. Çoğu uygulama, eski anlamı kullanımını seyrek olduğundan, bu değişiklikten etkilenmez.  
  
- Yeni **static_assert** anahtar sözcüğü sunulmuştur, zaten varsa bir tanımlayıcı bu adla kodunuzda bir ad çakışması neden olacak.  
  
- Yeni lambda gösterim bir IDL uuid özniteliği tırnak işareti olmayan bir GUID kodlaması için destek dışlar desteği.  
  
-   .NET Framework 4 işlem kurtarılamaz bir bozuk durumda bırakın özel durumlar bozuk durum özel durumları kavramını sunar. Varsayılan olarak, hatta diğer özel durumların tamamını yakalar / eha derleyici seçeneği ile bir bozuk durumda özel durumu yakalayamaz.                 Açıkça bir bozuk durum özel durumu yakalamak için __try - kullanın\__except deyimleri. Ya da bozuk durum özel durumları yakalamak bir işlev etkinleştirmek için [HandledProcessCorruptedStateExceptions] özniteliğini uygulayın.  Bu değişiklik, öncelikli olarak bozuk durumda özel durumu yakalamak gerekebilir sistem programcılar etkiler. Sekiz istisnaları STATUS_ACCESS_VIOLATION, STATUS_STACK_OVERFLOW, EXCEPTION_ILLEGAL_INSTRUCTION, EXCEPTION_IN_PAGE_ERROR, EXCEPTION_INVALID_DISPOSITION, EXCEPTION_NONCONTINUABLE_EXCEPTION, EXCEPTION_PRIV_INSTRUCTION, STATUS_ UNWIND_CONSOLIDATE.                 Bu özel durumları hakkında daha fazla bilgi için bkz. [GetExceptionCode](/windows/desktop/Debug/getexceptioncode) makrosu.  
  
- Düzenlenen `/GS` derleyici seçeneği korur arabellek taşmalarına karşı kıyasla daha kapsamlı önceki sürümleri. Bu sürüm, ek güvenlik denetimlerini performansı düşebilir yığınında ekleyebilirsiniz. Yeni **__declspec(safebuffers)** anahtar sözcüğünü kullanarak derleyicinin güvenlik Ekle değil, belirli bir işlev için denetler.  
  
- Her ikisi de derlerseniz `/GL` (bütün Program iyileştirmesi) ve `/clr` (ortak dil çalışma zamanı derlemesi) derleyici seçenekleri, `/GL` seçeneği yoksayılır. Derleyici Seçenekleri birleşimini az avantaj sağlamadığı bu değişiklik yapılmıştır. Bu değişikliğe bağlı olarak, derleme performansı geliştirildi.  
  
- Varsayılan olarak, trigrafları devre dışı için Visual C++ 2010'da destekler. Kullanım `/Zc:trigraphs` trigrafları desteğini etkinleştirmek için derleyici seçeneği. Bir trigraf oluşur birbirini izleyen iki soru işareti ("??") üçüncü bir benzersiz karakter. Derleyici bir trigraf karşılık gelen bir noktalama karakteri ile değiştirir. Örneğin, derleyici değiştirir "?? = "trigraf '#' karakteri ile. Trigrafları, C kaynak dosyalarında bazı noktalama karakterleri için uygun grafik sunumlar içermeyen bir karakter kümesini kullandırır kullanın.  
  
- Bağlayıcı artık Windows 98 için en iyi duruma getirme destekler. `/OPT` (İyileştirmeler) seçeneğini belirtirseniz bir derleme zamanı hatası oluşturur `/OPT:WIN98` veya `/OPT:NOWIN98`.  
  
- DebugInformationFormat ve RuntimeLibrary belirtilen varsayılan derleyici seçenekleri özellikleri değiştirildi sistem oluşturun. Varsayılan olarak, bu derleme özellikleri Visual C++ tarafından oluşturulan projeleri belirtilen 7.0 10.0 ile serbest bırakır. Visual C++ 6.0 tarafından oluşturulan bir projeyi geçirirseniz, yoksa bu özellikler için bir değer belirtmek göz önünde bulundurun.  
  
- Visual C++ 2010 RuntimeLibrary = çok iş parçacıklı (`/MD`) ve DebugInformationFormat ProgramDatabase = (`/Zi`). Visual c++ 9.0, RuntimeLibrary = çok iş parçacıklı (`/MT`) ve DebugInformationFormat = devre dışı.  
  
### <a name="clr"></a>CLR  
  
- Microsoft C# ve Visual Basic derleyicileri artık hiç birincil birlikte çalışma derlemesi (PIA Hayır) oluşturabilir. Hayır-PIA derleme COM türleri ilgili birincil birlikte çalışma derlemesi (PIA) dağıtımını olmadan kullanabilirsiniz. Kitaplığı kullanan herhangi bir no-PIA derleme başvurusu önce Visual C# veya Visual Basic tarafından üretilen Hayır PIA derlemeleri kullanılırken, derleme komut PIA derlemesine başvuru vermelisiniz.  
  
### <a name="visual-c-projects-and-msbuild"></a>Visual C++ projeleri ve MSBuild  
  
- Visual C++ projeleri artık MSBuild araç temel alır. Sonuç olarak, proje dosyaları yeni bir XML dosya biçimi ve .vcxproj dosyası sonekini kullanın. Visual C++ 2010 otomatik olarak proje dosyaları, Visual Studio'nun önceki sürümlerinden yeni bir dosya biçimine dönüştürür. Mevcut bir projeyi önceki derleme aracını, VCBUILD.exe veya proje dosya soneki .vcproj üzerinde bağlıysa etkilenir.  
  
- Önceki sürümlerde, Visual C++ özellik sayfaları geç değerlendirme desteklenmiyor. Örneğin, bir alt özellik sayfası bir üst özellik sayfası içeri aktarmak ve üst alt öğe içinde tanımlanan bir değişkeni diğer değişkenleri tanımlamak için kullanabilirsiniz. Geç değerlendirme üst, alt özellik sayfası bile alınmadan önce alt değişkenini kullanmak etkin. MSBuild yalnızca erken değerlendirme desteklediğinden tanımlanmadan önce Visual C++ 2010'da bir proje sayfası değişken kullanılamaz.  
  
### <a name="ide"></a>IDE  
  
- Uygulama sonlandırma iletişim kutusu artık bir uygulama sona erer. Önceki sürümlerde, zaman `abort()` veya `terminate()` işlevi, bir uygulamanın perakende derleme kapalı, C çalışma zamanı kitaplığı, bir konsol penceresi ya da iletişim kutusunda bir uygulama sonlandırma iletisi görüntülenir. İleti parçası olarak, "Bu uygulama çalışma zamanı bir biçimde sonlandırmasını istedi. Bununla birlikte "Lütfen uygulamanın Destek ekibine daha fazla bilgi için başvurun." Windows, Windows hata bildirimi (Dr. genellikle geçerli sonlandırma işleyicisi ardından görüntülenen uygulama sonlandırma iletisi olarak yedekli Watson) iletişim kutusunu veya Visual Studio hata ayıklayıcısını. Visual Studio 2010'da başlıyor, C çalışma zamanı kitaplığı ileti görüntülemez. Ayrıca, çalışma zamanı hata ayıklayıcı başlamadan önce uygulamanın bitiş engeller. Yalnızca uygulama sonlandırma iletisi üzerinde önceki davranışına dayanıyorsa bir değişiklik budur.  
  
- Özellikle Visual Studio 2010 için IntelliSense için C + çalışmaz +/ CLI kodu veya öznitelikleri **tüm başvuruları Bul** çalışmıyor yerel değişkenleri ve kod modeli için alınan derlemeleri tür adları alma veya çözün mu tam adlarıyla türleri.  
  
### <a name="libraries"></a>Kitaplıklar  
  
- SafeInt sınıfı Visual C++'de bulunan ve artık ayrı bir indirme değil. Ayrıca "SafeInt" adlı bir sınıf yalnızca geliştirdiyseniz, bir değişiklik budur.  
  
- Kitaplıkları dağıtım modeli, bildirimler artık belirli bir dinamik bağlantı kitaplığı sürümü bulmak için kullanır. Bunun yerine, sürüm numarasının her dinamik bağlantı kitaplığının adı içerir ve kitaplığını bulmak için bu adı kullanın.  
  
- Visual Studio'nun önceki sürümlerinde, çalışma zamanı kitaplıkları yeniden oluşturulamadı. Visual C++ 2010 artık kendi kopyalarını çalıştırma zamanı kitaplık dosyaları C oluşturmayı da destekler.  
  
### <a name="standard-library"></a>Standart Kitaplık  
  
- \<Yineleyici > Üstbilgi artık dahil otomatik olarak tarafından diğer pek çok üst bilgi dosyaları. Önceki derleme aracını, VCBUILD.exe veya proje dosya soneki bağlıysa An varolan projede tanımlanan tek başına yineleyiciler için destek etkilenen gerekiyorsa bunun yerine, bu açıkça üstbilgisini. vcproj.interator > Üstbilgi.  
  
- İçinde \<algoritma > üst bilgi, checked_ * ve unchecked_\* işlevleri kaldırılır. Ve \<yineleyici >> başlık `checked_iterator` sınıfı kaldırılır ve `unchecked_array_iterator` sınıfı eklendi.  
  
- `CComPtr::CComPtr(int)` Oluşturucusu kaldırılır. Bu oluşturucu, izin verilen bir `CComPtr` nesnesinin NULL makrodan oluşturulmuş olabilir ancak gereksiz ve nonsensical izin yapılarını gelen sıfır olmayan bir tamsayı.  
  
     A `CComPtr` hala 0 olarak tanımlandığında, ancak tamsayı sabit değeri 0 dışında oluşturulan bırakılırsa, NULL oluşturulabilir. Kullanım **nullptr** yerine.  
  
- Aşağıdaki `ctype` üye işlevleri kaldırıldı: `ctype::_Do_narrow_s`, `ctype::_Do_widen_s`, `ctype::_narrow_s`, `ctype::_widen_s`. Bir uygulama bu üye işlevleri kullanıyorsa, karşılık gelen güvenli olmayan sürümü ile değiştirmeniz gerekir: `ctype::do_narrow`, `ctype::do_widen`, `ctype::narrow`, `ctype::widen`.  
  
### <a name="crt-mfc-and-atl-libraries"></a>CRT, MFC ve ATL kitaplığı  
  
- CRT, MFC ve ATL kitaplıkları oluşturmak, kullanıcılar için destek kaldırılmıştır. Örneğin, bir uygun nmake dosyası sağlanmadı. Ancak, kullanıcılar yine de kaynak kodu bu kitaplıklara ilişkin erişebilir. Ve Microsoft bu kitaplıkları oluşturmak için kullandığı MSBuild seçeneklerini açıklayan bir belge içinde Visual C++ Team Blog büyük olasılıkla yayımlanacak.  
  
- IA64 için MFC Desteği kaldırılmıştır. Ancak, CRT ve IA64 üzerinde ATL desteği yine de sağlanır.  
  
- Sıra sayıları artık MFC modül-tanımlama (.def) dosyaları yeniden kullanılır. Bu değişiklik, sıra sayıları ikincil sürümleri arasında farklı olmayacaktır ve ikili uyumluluk hizmet paketleri ve hızlı yayınlar mühendislik düzeltme için geliştirilmiş anlamına gelir.  
  
- Yeni bir sanal işlev eklendi `CDocTemplate` sınıfı. Bu yeni bir sanal işlev [CDocTemplate sınıfı](../mfc/reference/cdoctemplate-class.md). Önceki sürümünü `OpenDocumentFile` iki parametre vardı. Yeni sürümü, üç parametre yok. Yeniden başlatma Yöneticisi desteği için herhangi bir sınıftan türetilen `CDocTemplate` üç parametre sürümü uygulamalıdır. Yeni parametre `bAddToMRU`.  
  
### <a name="macros-and-environment-variables"></a>Makrolar ve ortam değişkenleri  
  
- Ortam değişkeni __MSVCRT_HEAP_SELECT artık desteklenmiyor. Bu ortam değişkeni kaldırılır ve bir şey eklenmemiştir.  
  
### <a name="microsoft-macro-assembler-reference"></a>Microsoft Macro Assembler Başvurusu  
  
- Birkaç yönergeleri Microsoft Macro Assembler başvurusu derleyicisinden kaldırıldı. .186, kaldırılan yönergeleridir.286, .286P.287,.8086,.8087, ve. NO87.  
  
## <a name="visual-c-2008-breaking-changes"></a>Visual C++ 2008 bozucu değişiklikler  
  
### <a name="compiler"></a>Derleyici  
  
- Windows 95, Windows 98, Windows ME ve Windows NT platformları artık desteklenmiyor. Bu işletim sistemleri, hedeflenen platformun listesinden kaldırıldı.  
  
- Derleyici artık doğrudan olan birden çok öznitelik destekler ATL sunucusuyla ilişkilendirilmiş. Aşağıdaki öznitelikler artık desteklenir:  
  
    - perf_counter  
  
    - perf_object  
  
    - Perfmon  
  
    - request_handler  
  
    - soap_handler  
  
    - soap_header  
  
    - soap_method  
  
    - tag_name  
  
### <a name="visual-c-projects"></a>Visual C++ projeleri  
  
- Projeleri Visual Studio'nun önceki sürümlerinden yükseltme yaparken, büyüktür veya eşittir 0x0500 olmalı ve böylelikle WINVER ve _WIN32_WINNT'de makroları değiştirmek gerekebilir.  
  
- Visual Studio 2008'den itibaren Yeni Proje Sihirbazı'nı bir SQL Server C++ projesi oluşturmak için bir seçenek yok. Visual Studio'nun önceki bir sürümü kullanılarak oluşturulmuş SQL Server projeleri hala derleyin ve düzgün çalışır.  
  
- Windows API üst bilgi dosyası Winable.h kaldırıldı. Bunun yerine Winuser.h içerir.  
  
- Windows API kitaplığı Rpcndr.lib kaldırıldı. Bunun yerine Rpcrt4.lib ile bağlayın.  
  
### <a name="crt"></a>CRT  
  
- Windows 95, Windows 98, Windows Millennium Edition ve Windows NT 4.0 için destek kaldırılmıştır.  
  
- Aşağıdaki genel değişkenleri kaldırıldı:  
  
    - _osplatform  
  
    - _osver  
  
    - _winmajor  
  
    - _winminor  
  
    - _winver  
  
- Aşağıdaki işlevleri kaldırıldı. Windows API işlevlerini `GetVersion` veya `GetVersionEx` bunun yerine:  
  
    - _get_osplatform  
  
    - _get_osver  
  
    - _get_winmajor  
  
    - _get_winminor  
  
    - _get_winver  
  
- SAL ek açıklamaları sözdizimini değişti. Daha fazla bilgi için [SAL ek açıklamalarını](../c-runtime-library/sal-annotations.md).  
  
- IEEE filtre şimdi SSE 4.1 yönerge kümesini destekler. Daha fazla bilgi için [_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)_fpieee_flt.  
  
- C çalışma zamanı kitaplıkları Visual Studio ile birlikte sevk artık üzerinde sistem DLL msvcrt.dll bağımlıdır.  
  
### <a name="standard-library"></a>Standart Kitaplık  
  
- Windows 95, Windows 98, Windows Millennium Edition ve Windows NT 4.0 için destek kaldırılmıştır.  
  
- Hata ayıklama modunda tanımlanmış _HAS_ITERATOR_DEBUGGING ile derleme yaparken (yerini [_ıterator_debug_level](../standard-library/iterator-debug-level.md) sonra Visual Studio 2010), bir yineleyici artırın veya geçmiş azaltma girişiminde bulunduğunda bir uygulama artık onaylama temel alınan kapsayıcının sınırları.  
  
- Üye değişkeni c sınıfı yığınının artık korumalı bildirilir. Daha önce bu üye değişkeni, genel bildirildi.  
  
- Davranışını `money_get::do_get` değişti. Daha önce ile bir parasal miktarını ayrıştırılırken değerinden daha fazla kesir basamağı için adlandırılır `frac_digits`, `do_get` tüm bunları kullanmak için kullanılır. Şimdi, `do_get` en fazla tükettikten sonra ayrıştırma durdurur `frac_digits` karakter.  
  
### <a name="atl"></a>ATL  
  
- ATL CRT üzerinde bir bağımlılık oluşturulamıyor. Visual Studio'nun önceki sürümlerinde kullanabileceğinizi #define atl_mın_crt ATL projesinde CRT üzerinde en düşük düzeyde bağımlı hale getirmek için. Visual C++ 2008'de tüm ATL projeleri atl_mın_crt tanımlanan bağımsız olarak CRT üzerinde en düşük düzeyde bağımlıdır.  
  
- ATL Sunucu codebase Codeplex'te bir paylaşılan kaynak proje olarak yayımlanmıştır ve Visual Studio'nun bir parçası yüklü değil. Kodlama ve sınıflardan atlenc.h ve yardımcı işlevleri ve sınıfları atlutil.h ve atlpath.h kod çözme veri tutulmuştur ve artık ATL Kitaplığı'nın bir parçasıdır. ATL Sunucu ile ilişkilendirilen çeşitli dosyalar artık, Visual Studio'nun bir parçası değildir.  
  
- Bazı işlevler, artık DLL'de bulunur. Bunlar yine de içeri aktarma kitaplığı'nda bulunur. Bu işlevleri statik olarak kullanan kodu etkilemez. Bu, bu işlevler dinamik olarak kullanan kod etkiler.  
  
- Makroları PROP_ENTRY ve PROP_ENTRY_EX kullanım ve güvenlik nedenleriyle PROP_ENTRY_TYPE ve PROP_ENTRY_TYPE_EX makroları ile değiştirilmiştir.  
  
### <a name="atlmfc-shared-classes"></a>ATL/MFC Paylaşılan Sınıfları  
  
- ATL CRT üzerinde bir bağımlılık oluşturulamıyor. Visual Studio'nun önceki sürümlerinde kullanabileceğinizi `#define ATL_MIN_CRT` ATL projesinde CRT üzerinde en düşük düzeyde bağımlı hale getirmek için. Visual C++ 2008'de tüm ATL projeleri atl_mın_crt tanımlanan bağımsız olarak CRT üzerinde en düşük düzeyde bağımlıdır.  
  
- ATL Sunucu codebase Codeplex'te bir paylaşılan kaynak proje olarak yayımlanmıştır ve Visual Studio'nun bir parçası yüklü değil. Kodlama ve sınıflardan atlenc.h ve yardımcı işlevleri ve sınıfları atlutil.h ve atlpath.h kod çözme veri tutulmuştur ve artık ATL Kitaplığı'nın bir parçasıdır. ATL Sunucu ile ilişkilendirilen çeşitli dosyalar artık, Visual Studio'nun bir parçası değildir.  
  
- Bazı işlevler, artık DLL'de bulunur. Bunlar yine de içeri aktarma kitaplığı'nda bulunur. Bu işlevleri statik olarak kullanan kodu etkilemez. Bu, bu işlevler dinamik olarak kullanan kod etkiler.  
  
### <a name="mfc"></a>MFC  
  
- `CTime` Sınıf: `CTime` sınıfı artık C.E. 1/1/1900 ' itibaren tarihleri kabul eder 1/1/1970 C.E. yerine              

- MFC iletişim kutularındaki denetimlerin sırasını sekmesi: bir MFC iletişim kutusunda birden çok denetim doğru sekme sırası sekme sırasının MFC ActiveX denetimi eklediyseniz rahatsız edilmiş. Bu değişiklik, bu sorunu düzeltir.  
  
     Örneğin, bir ActiveX denetimini ve birkaç düzenleme denetimleri olan bir MFC iletişim uygulama oluşturun. Konumu Düzenle denetimlerin sekme sırasını ortasında ActiveX denetimi. Uygulamayı başlatmak, sekme sırasını ActiveX denetimi ve sekme sonra olan bir düzenleme denetimi tıklayın. Bu değişiklik öncesinde, odak sonraki sekme sırasını düzenleme denetiminde yerine ActiveX denetimi aşağıdaki düzenleme denetimine bir sorun oluştu.  
  
- `CFileDialog` Sınıf: Özel şablonları için `CFileDialog` sınıfı olamaz otomatik olarak unity'nin Windows Vista için. Bunlar hala kullanılabilir, ancak ek işlevsellik olmaz veya Windows Vista stili iletişimleri arar.  
  
- `CWnd` Sınıf ve `CFrameWnd` sınıfı: `CWnd::GetMenuBarInfo` yöntemi kaldırıldı.  
  
     `CFrameWnd::GetMenuBarInfo` Yöntemi sanal olmayan bir yöntem sunuldu. Daha fazla bilgi için **GetMenuBarInfo işlevi** Windows SDK.  
  
- MFC ISAPI desteği: MFC artık uygulamalar oluşturma ile Internet sunucusu uygulama programı arabirimi (ISAPI) destekler. ISAPI uzantıları, ISAPI uygulama oluşturmak istiyorsanız, doğrudan çağırabilir.  
  
- Kullanım dışı ANSI API'leri: Çeşitli MFC yöntemler ANSI sürümleri kullanım dışı bırakılmıştır. Gelecekteki uygulamalarınızın bu yöntemleri Unicode sürümlerini kullanın. Daha fazla bilgi için **yapı gereksinimleri için Windows Vista ortak denetimleri**.  
  
## <a name="visual-c-2005-breaking-changes"></a>Visual C++ 2005 bozucu değişiklikler  
  
### <a name="crt"></a>CRT  
  
- Birçok işlev kullanım dışı bırakıldı. Bkz: **CRT işlevleri kullanım dışı**.  
  
- Birçok İşlevler, artık geçersiz parametreler verildiyse yürütmeyi durdurma, kendi parametrelerini doğrular. Geçersiz parametreler geçirir ve bunları yoksayılıyor veya yalnızca bir hata kodunu döndürerek işlevi kullanır kodu kesilmesine neden olabilir. Bkz: **parametre doğrulaması**.  
  
- Dosya tanımlayıcısı değeri -2, artık stdout ve stderr hiçbir konsol penceresine sahip bir Windows uygulaması örnekte olduğu gibi bir çıktı kullanılamaz olduğunu belirtmek için kullanılır. Kullanılan önceki değer -1 belirtildi. Daha fazla bilgi için [_fileno](../c-runtime-library/reference/fileno.md).  
  
- Tek iş parçacıklı CRT kitaplığı /ML ve libcd.lib, kaldırıldı. Çok iş parçacıklı CRT kitaplıkları kullanın. `/ML` Derleyici bayrağı artık desteklenmiyor. Çok iş parçacıklı kod ve tek iş parçacıklı kod arasındaki performans farkının potansiyel olarak önemli olduğu durumlarda bazı işlevlerin olmayan kilitleme sürümleri eklendi.  
  
- Pow, çift pow (int, int), aşırı yüklemesini standarda daha iyi uyacak şekilde kaldırıldı.  
  
- Kendiliğinden olmaması nedeniyle varsayılan olarak tüm işlevleri printf ailesinin %n Biçim belirticisi artık desteklenmiyor. %N karşılaşılırsa varsayılan davranışı geçersiz parametre işleyicisini çağırır sağlamaktır. %N desteğini etkinleştirmek için _set_printf_count_output (Ayrıca see_get_printf_count_output) kullanın.  
  
- `sprintf` Şimdi imzalanmış bir sıfır eksi işareti yazdırır.  
  
- `swprintf` standarda uygun şekilde değiştirildi; Artık, bir boyut parametresi gerektirir. Biçiminde `swprintf` olmadan boyutu parametresi kullanımdan çıkarıldı.  
  
- `_set_security_error_handler` kaldırıldı. Bu işlev çağrıları kaldırın; Varsayılan güvenlik hataları uğraşmanızı çok daha güvenli şekilde işleyicisidir.  
  
- `time_t` (_use_32bıt_tıme_t tanımlı olmadığı sürece) 64 bitlik bir değer sunulmuştur.  
  
- `_spawn`, `_wspawn` İşlevleri artık bırakın errno dokunulmadan C Standart tarafından belirtilen başarılı olma durumunda.  
  
- RTC, geniş karakterler artık varsayılan olarak kullanır.  
  
- Kayan nokta denetim sözcüğünü desteği işlevleri, / CLR veya/CLR ile derlenmiş uygulamalar için kaldırılmıştır: PURE. Etkilenen işlevleri `_clear87`, `_clearfp`, `_control87`, `_controlfp`, `_fpreset`, `_status87`, `_statusfp`. _CRT_MANAGED_FP_NO_DEPRECATE tanımlayarak kullanımdan kaldırılma uyarısı devre dışı bırakabilirsiniz, ancak bu işlevler yönetilen kodda beklenmedik ve desteklenmeyen kullanılır.  
  
- Bazı işlevler, artık const işaretçiler döndürür. Eski, sabit olmayan davranış _CONST_RETURN tanımlayarak sağlanmaya başlanır. Etkilenen işlevleri  
  
    - memchr, wmemchr  
  
    - strchr, wcschr, _mbschr, _mbschr_l  
  
    - strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l  
  
    - strrchr, wcsrchr, _mbsrchr, _mbsrchr_l  
  
    - strstr, wcsstr, _mbsstr, _mbsstr_l  
  
- Setargv.obj veya Wsetargv.obj bağlarken artık çift tırnak içine alarak komut satırında bir joker karakter genişletmesi bastırmak mümkün değildir. Daha fazla bilgi için [joker karakter bağımsız değişkenlerini genişletme](../c-language/expanding-wildcard-arguments.md).  
  
### <a name="standard-library-2005"></a>Standart Kitaplığı (2005)  
  
- Özel durum sınıfı (bulunan \<özel durum > üst bilgi) taşındı `std` ad alanı. Önceki sürümlerde, bu sınıfın genel ad alanında oluştu. Özel durum sınıfı bulunamadığını belirten hataları gidermek için aşağıdakileri ekleyin, kodunuzun deyimi kullanarak:                 `using namespace std;`  
  
- Çağrılırken `valarray::resize()`, içeriğini `valarray` kaybolacak ve varsayılan değerlerle değiştirilir. `resize()` Yöntemi yeniden tasarlanmıştır `valarray` yerine dinamik olarak gibi bir vektör büyütün.  
  
- Hata ayıklama yineleyiciler: Uygulamaların hata ayıklama sürümü C çalışma zamanı kitaplığı ile oluşturulan ve çalışma zamanında hangi kullanım yineleyiciler görmek yanlış başlayabilir onaylar. Bunlar devre dışı bırakmak için onaylar, _HAS_ITERATOR_DEBUGGING tanımlaması gerekir (yerini [_ıterator_debug_level](../standard-library/iterator-debug-level.md) sonra Visual Studio 2010) 0. Daha fazla bilgi için [hata ayıklama yineleyici desteği](../standard-library/debug-iterator-support.md)  
  
## <a name="visual-c-net-2003-breaking-changes"></a>Visual C++ .NET 2003 bozucu değişiklikler  
  
### <a name="compiler"></a>Derleyici  
  
- Kapanış ayraçlarını tanımlanmış önişlemci yönergesi (C2004) için artık gerekli.  
  
- Açık uzmanlık artık birincil şablondan şablon parametreleri bulun ([derleyici hatası C2146](../error-messages/compiler-errors-1/compiler-error-c2146.md)).  
  
- Korumalı bir üye (n) yalnızca bir üye işlevi onu (n) üyesi olduğu sınıfından (A) devralan bir sınıfın (B) üzerinden erişilebilir ([derleyici hatası C2247](../error-messages/compiler-errors-1/compiler-error-c2247.md)).  
  
- Geliştirilmiş erişilebilirlik denetimlerinde derleyici artık erişilemeyen temel sınıflar algılamak ([derleyici hatası C2248](../error-messages/compiler-errors-1/compiler-error-c2248.md)).  
  
- Bir özel durum, yakalanamaz yok edici ve/veya kopya oluşturucudur erişilemez (C2316).  
  
- Varsayılan bağımsız değişkenler üzerinde artık izin işlev işaretçileri ([derleyici hatası C2383](../error-messages/compiler-errors-1/compiler-error-c2383.md)).  
  
- Statik veri üyesi türetilmiş sınıf aracılığıyla başlatılamaz ([derleyici hatası C2477](../error-messages/compiler-errors-1/compiler-error-c2477.md)).  
  
- Başlatma bir **typedef** standart tarafından izin verilmiyor ve artık bir derleyici hatasına neden olur ([derleyici hatası C2513](../error-messages/compiler-errors-2/compiler-error-c2513.md)).  
  
- **bool** artık doğru bir türüdür ([derleyici hatası C2632](../error-messages/compiler-errors-2/compiler-error-c2632.md)).  
  
- Aşırı yüklenmiş işleçlerle bir UDC artık belirsizliği oluşturabilirsiniz ([C2666](../error-messages/compiler-errors-2/compiler-error-c2666.md)).  
  
- Daha fazla ifade artık geçerli bir null işaretçi sabit olarak kabul edilir ([derleyici hatası C2668](../error-messages/compiler-errors-2/compiler-error-c2668.md)).  
  
- Şablon <> yerde nerede derleyici daha önce yaptığından, artık gerekli ([derleyici hatası C2768](../error-messages/compiler-errors-2/compiler-error-c2768.md)).  
  
- Bir üye işlev ourside expilicit uzmanlaşması sınıf işlev zaten açıkça Şablon sınıfı bir özelleştirmeye özelleştirilmiş geçerli değil ([derleyici hatası C2910](../error-messages/compiler-errors-2/compiler-error-c2910.md)).  
  
- Kayan nokta tür olmayan şablon parametreleri artık izin verilir ([derleyici hatası C2993](../error-messages/compiler-errors-2/compiler-error-c2993.md)).  
  
- Sınıf şablonlarının şablon türü bağımsız (C3206) izin verilmez.  
  
- Arkadaş işlev adlarını, kapsayan ad alanını artık sunulmuştur ([derleyici hatası C3767](../error-messages/compiler-errors-2/compiler-error-c3767.md)).  
  
- Derleyici artık ek virgül (C4002) bir makroda kabul eder.  
  
- Bir form () Başlatıcı ile oluşturulmuş POD türünde bir nesne, varsayılan olarak başlatılır (C4345) olacaktır.  
  
- TypeName, artık bir bağımlı öğe adı bir tür olarak kabul edilmesi için gereklidir ([Derleyici Uyarısı (düzey 1) C4346](../error-messages/compiler-warnings/compiler-warning-level-1-c4346.md)).  
  
- Şablon uzmanlıkları yanlış dikkate işlevleri artık bunu (C4347) olarak kabul edilir.  
  
- Statik veri üyeleri (C4356) türetilmiş sınıf aracılığıyla başlatılamaz.  
  
- Bir sınıf şablonu uzmanlığı, dönüş türü içinde kullanılan önce tanımlanması gerekir ([Derleyici Uyarısı (Düzey 3) C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md)).  
  
- Derleyici artık erişilemeyen kod (C4702) bildirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.

[Visual Studio'da Visual C++ yenilikleri](../what-s-new-for-visual-cpp-in-visual-studio.md)
---
title: "Visual C++ değişiklik geçmişini 2003 2015 | Microsoft Docs"
ms.custom: 
ms.date: 08/30/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- breaking changes [C++]
ms.assetid: b38385a9-a483-4de9-99a6-797488bc5110
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 271831fb4dd946739414fb40b00fadf83b5e0ed1
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="visual-c-change-history-2003---2015"></a>Visual C++ değişiklik geçmişini 2003 2015

Bu makalede, Visual Studio 2015 için Visual Studio 2003 ve bu makalede "yeni davranış" koşulları geri dönerseniz gelen tüm önemli değişiklikler açıklanmaktadır veya Visual Studio 2015 ve daha sonra "Şimdi" başvurun. Koşulları "eski davranışı" ve "önce" Visual Studio 2013 ve önceki sürümleri için bkz.

Visual Studio 2017 hakkında daha fazla bilgi için bkz: [Visual Studio 2017'de Visual C++ yenilikleri](../what-s-new-for-visual-cpp-in-visual-studio.md) ve [uygunluk Visual Studio 2017'de Visual C++ yenilikleri](../cpp-conformance-improvements-2017.md). 

> [!NOTE]
> Visual Studio 2015 ve Visual Studio 2017 arasında önemli değişiklikler hiçbir ikili vardır.

Visual Studio'nun yeni bir sürüme yükselttiğinizde, derleme ve/veya önceden derlenmiş ve doğru şekilde çalışan kodda çalışma zamanı hataları karşılaşabilirsiniz. Olarak bilinen yeni sürümü gibi sorunlara neden değişiklikleri *önemli değişiklikler*, ve genellikle bunlar C++ dili standart, işlevi imzaları veya bellekte nesneleri düzen değişikliklerini gerektirdiği.

 Algılanması ve tanılanması zor çalışma zamanı hatalarından kaçınmak için, derleyicinin farklı sürümleri kullanılarak derlenmiş ikili dosyalara hiçbir zaman statik bağlantı vermemenizi öneriyoruz. Ayrıca, bir EXE veya DLL projesini yükseltirken, bağlantı verdiği kitaplıkları da yükselttiğinizden emin olun. CRT (C çalışma zamanı) ya da C++ Standart Kitaplığı (Standart C++ Kitaplığı) türleri kullanıyorsanız, bunları derleyici farklı sürümleri kullanılarak derlendi (DLL'leri dahil) ikili dosyalar arasında geçiş yok. Daha fazla bilgi için bkz: [olası hataları geçirme CRT nesnelerini DLL sınırlar boyunca](../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md).  
  
 Ayrıca, COM arabirimi ya da POD projesi olmayan bir nesne için belirli bir düzeni temel alan kodları da asla yazmamanızı öneriyoruz. Bu tür bir kod yazarsanız, yükseltme sonrasında çalışmasını sağlamalısınız. Daha fazla bilgi için bkz: [taşınabilirlik adresindeki ABI sınırları](../cpp/portability-at-abi-boundaries-modern-cpp.md).  
  
 Ayrıca, devam eden iyileştirmeler derleyici uyumluluğu bazen derleyici mevcut kaynak kodunuzu nasıl anlar değiştirebilirsiniz. Bu gerçekleştiğinde, yapı veya önceden oluşturulmuş ve düzgün çalışmasına görünüyor kodu dahi davranış farklılıkları sırasında yeni ya da farklı hatalarla karşılaşabilirsiniz. Bunlar bu belgede ele alınan olanlar gibi önemli değişiklikler değil olmakla birlikte, bu sorunları gidermek için kaynak kod değişiklikleri gerekli.  
  
  
1.  [C çalışma zamanı (CRT) kitaplığı yeni değişiklikler](#BK_CRT)  
  
2.  [Standart C++ ve yeni değişiklikler C++ Standart Kitaplığı](#BK_STL)  
  
3.  [MFC ve ATL yeni değişiklikler](#BK_MFC)  
  
4.  [Eşzamanlılık Çalışma zamanı önemli değişiklikler](#BK_ConcRT)  
  
## <a name="VC_2015"></a>Visual C++ 2015 uyumluluğu değişiklikleri  
  
###  <a name="BK_CRT"></a>C çalışma zamanı kitaplığı (CRT)  
  
#### <a name="general-changes"></a>Genel değişiklikler  
  
-   **İkili dosyaları yeniden düzenlenmiş sürümlere** CRT kitaplık, bir iki farklı ikili dosyalar, bir evrensel standart işlevselliğinin büyük kısmını içeren CRT (ucrtbase) ve bir VC Çalışma zamanı derleyici ile ilgili içeren kitaplığı (vcruntime) bulunanad özel durum işleme ve ön tanımlı gibi işlevselliği. Varsayılan proje ayarlarını kullanıyorsanız, bağlayıcı yeni varsayılan kitaplıkları otomatik olarak kullanır bu yana sonra bu değişiklik, etkilemez. Projenin ayarlarsanız **bağlayıcı** özelliği **tüm varsayılan kitaplıkları Yoksay** için **Evet** veya komut satırında /NODEFAULTLIB bağlayıcı seçeneğini kullanıyorsanız, sonra gerekir kitaplıkları listesini güncelleştirin (içinde **ek bağımlılıklar** özelliği) yeni, işlenmiş kitaplıkları eklenecek. Eski CRT kitaplık (libcmt.lib, libcmtd.lib, msvcrt.lib, msvcrtd.lib) eşdeğer işlenmiş kitaplıkları ile değiştirin. Her iki işlenmiş kitaplıkların vardır (.lib) statik ve dinamik (.dll) sürümlerin sürümüyle (herhangi bir sonek) ve hata ayıklama sürümleriyle ("d" soneki). Dinamik sürümleri ile bağlantı bir içeri aktarma kitaplığını sahip. İki işlenmiş kitaplıkları, Evrensel CRT, özellikle ucrtbase.dll veya .lib, ekler veya .lib ve VC Çalışma Zamanı Kitaplığı ve libvcruntime.lib, vcruntime*sürüm*.dll, libvcruntimed.lib ve vcruntimed*sürüm*.dll. *Sürüm* Visual Studio 2015 ve Visual Studio 2017 140 değil. Bkz: [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md).  
  
#### <a name="localeh"></a>\<Locale.h >  
  
-   **localeconv** [localeconv](../c-runtime-library/reference/localeconv.md) işlevi bildirilen locale.h şimdi çalışır doğru olduğunda [iş parçacığı başına yerel ayar](../parallel/multithreading-and-locales.md) etkinleştirilir. Kitaplık önceki sürümlerinde, bu işlevi değil iş parçacığı yerel ayarı genel yerel ayarlar lconv veri döndürür.  
  
     İş parçacığı yerel ayarlarına göre kullanırsanız, kodunuzu lconv verileri genel yerel döndürülen varsayar olmadığını görmek için localeconv kullanımınız denetleyin ve uygun şekilde değiştirin.  
  
#### <a name="mathh"></a>\<Math.h >  
  
-   **Matematik kitaplık işlevleri C++ aşırı** önceki sürümlerde, \<math.h > matematik kitaplık işlevleri için C++ aşırı, bazı ancak değil tüm tanımlı. \<cmath > şekilde aşırı bir dahil etmek için gerekli tüm almak için kalan aşırı tanımlanan \<cmath > Üstbilgi. Bu işlev aşırı yükleme çözünürlüğü yalnızca dahil kodda ile ilgili sorunların neden \<math.h >. Şimdi, tüm C++ aşırı kaldırılmış olan \<math.h > ve şimdi yalnızca mevcut olduğundan \<cmath >.  
  
     Hataları gidermek için dahil <cmath> sıradan kaldırıldığını işlevleri bildirimlerini almak için \<math.h >. Aşağıdaki tabloda taşındı işlevleri listeler.  
  
     Taşınan İşlevler:  
  
    1.  çift abs(double) ve float abs(float)  
  
    2.  double pow (double, int), float pow (float, float) float pow (float, int) pow (uzun çift, uzun çift)'uzun çift, pow (uzun çift int)'uzun çift  
  
    3.  float ve noktası işlevleri acos acosh, asin, asinh, atan, atanh, atan2, cbrt, cos, copysign, ceil kayan uzun çift sürümlerini cosh, erf, erfc, exp, exp2, expm1, fabs, fdim, floor, fma, fmax, fmin, fmod, frexp, hypot, ilogb, ldexp, lgamma, llrint, llround, günlük , log10, log1p, log2, lrint, lround, modf, nearbyint, nextafter, nexttoward, kalan, remquo, azdır, hepsini, scalbln, scalbn, Sinüs, sinh, sqrt, Bronz, tanh, tgamma, trunc  
  
     Bir kayan ile kullanır abs noktası yalnızca math.h üstbilgi içeren türü, kayan nokta sürümleri Hayır sahip code, kayan olsa da, çağrısı işaret biçimde bağımsız değişkeni artık kullanılabilir, şimdi abs(int) için çözümler. Bu hata üretir:  
  
    ```Output  
    warning C4244: 'argument' : conversion from 'float' to 'int', possible loss of data  
    ```  
  
     Bu uyarı için düzeltmeyi abs çağrısı bir kayan ile değiştirmektir noktası fabs çift bağımsız değişkeni için veya bir float bağımsız değişkeni için fabsf gibi abs sürümünü veya cmath üstbilgisi içerir ve abs kullanmaya devam edebilirsiniz.  
  
-   **Kayan nokta uygunluk** birçok matematik kitaplığına NaN ve sonsuz gibi özel servis talebi girişleri göre IEEE 754 ve C11 eki F belirtimlerine uyumluluğu artırmak için yapılan değişiklikler. Örneğin, genellikle önceki sürümlerinde kitaplığı, hata olarak kabul, sessiz NaN girişleri artık hata olarak kabul edilir. Bkz: [IEEE 754 standart](http://grouper.ieee.org/groups/754) ve Annex F, [C11 standart](http://www.iso-9899.info/wiki/The_Standard).  
  
     Bu değişiklikler derleme zamanında hata oluşmasına neden olmaz ancak standart göre farklı ve daha doğru bir şekilde davranmasına programlar neden olabilir.  
  
-   **FLT_ROUNDS** , Visual Studio 2013, yuvarlama modu arama fesetround tarafından çalışma zamanında, örneğin, yapılandırılabilir olduğundan, yanlış bir sabit ifadesine genişletilmiş FLT_ROUNDS makrosu. FLT_ROUNDS makrosu şimdi dinamiktir ve doğru geçerli yuvarlama modu yansıtır.  
  
#### <a name="new-and-newh"></a>\<Yeni > ve \<new.h >  
  
-   **Yeni ve silme** kitaplığı önceki sürümlerinde, uygulama tanımlı new işleci ve silme işlevleri Çalışma Zamanı Kitaplığı'ndan DLL (örneğin, msvcr120.dll) verildi. Bu işleç işlevler şimdi her zaman statik olarak ikili dosyalar içinde çalışma zamanı kitaplığı DLL'leri kullanırken bile bağlanır.  
  
     Bu yerel ya da karma kodu için önemli bir değişiklik değil (/ clr), ancak olarak derlenmiş kod [/CLR: pure](../build/reference/clr-common-language-runtime-compilation.md), bu kodunuzu derlemek başarısız olmasına neden olabilir. / CLR olarak kod derleme yaparsanız: Saf, size eklemeniz gerekebilir #include \<yeni > veya #include \<new.h > derleme hataları bu değişikliği nedeniyle geçici olarak çözmek için. Unutmayın, / CLR: pure olan Visual Studio 2015'te kullanım dışıdır ve gelecek sürümlerde kaldırılabilir.  
  
#### <a name="processh"></a>\<Process.h >  
  
-   **_beginthread ve _beginthreadex** [_beginthread](../c-runtime-library/reference/beginthread-beginthreadex.md) ve [_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md) şimdi işlevleri bir iş parçacığı yordamı süresince tanımlanır modülü başvurusu iş parçacığı. Bu bir iş parçacığı tamamlanıncaya kadar çalıştırılana dek modülleri kaldırılmış olduğundan emin olmak için yardımcı olur.  
  
#### <a name="stdargh"></a>\<stdarg.h >  
  
-   **va_start ve başvuru türleri** C++ kodu derlerken [va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) şimdi derleme kendisine geçirilen bağımsız değişken başvuru türünde olmayan zamanında doğrular. Başvuru türü bağımsız değişkenleri C++ standardına göre yasaktır.  
  
#### <a name="stdioh-and-conioh"></a>\<stdio.h > ve \<conio.h >  
  
-   **Printf ve scanf ailesi işlevlerini şimdi tanımlanan satır içi.** Tüm printf ve scanf işlevleri tanımlarını içine taşınan satır içi silinmiş \<stdio.h >, \<conio.h > ve diğer CRT üstbilgileri. Bu bir bağlayıcı hatası (LNK2019, çözümlenmemiş dış sembol) müşteri adayları önemli bir değişiklik uygun CRT üstbilgileri dahil olmak üzere bu işlevler yerel olarak bildirilen tüm programları içindir. Mümkünse, CRT üstbilgileri dahil etmek için kod güncelleştirmeniz gerekir (diğer bir deyişle, ekleme #include \<stdio.h >) ve satır içi işlevler, ancak bu üst bilgi dosyaları dahil etmek için kodunuzu değiştirmek istemiyorsanız, başka bir çözüm ek eklemek için Kitaplığı, bağlayıcı giriş, legacy_stdio_definitions.lib için.  
  
     IDE içinde bağlayıcı giriş bu kitaplığa eklemek için proje düğümüne bağlam menüsünü açın, seçin **özellikleri**, ardından **proje özelliklerini** iletişim kutusunda, seçin **bağlayıcı**ve düzenleme **bağlayıcı girişi** legacy_stdio_definitions.lib semi-colon ayrılmış listesine eklemek için.
     Projeniz Visual Studio 2015'ten önceki bir sürümü ile derlendi statik kitaplıkları ile bağlanıyorsa, bağlayıcı çözülmemiş bir dış sembolü bildirebilir. Bu hatalar _iob, _iob_func veya biçiminde belirli stdio işlevleri için ilgili içeri aktarmalar için iç stdio tanımları başvurabilir\_*. Microsoft, bir projeyi yükselttiğiniz sırada C++ derleyicisi en son sürümü ile tüm statik kitaplıklar ve kitaplıkları derlenir önerir. Bir üçüncü taraf kitaplık kitaplığı ise, hangi kaynağı kullanılamıyor için güncelleştirilmiş bir ikili üçüncü taraftan isteği ya da eski sürümü derleyici ve kitaplıkları ile derleme ayrı bir DLL içine bu kitaplık kullanımınızı yalıtma .
  
    > [!WARNING]
    >  Windows 8.1 SDK veya önceki bağlanıyorsanız, bu çözümlenmemiş dış simgesi hatalarla karşılaşabilirsiniz. Bu durumda, daha önce açıklandığı gibi giriş bağlayıcı legacy_stdio_definitions.lib ekleyerek hata çözümlenmelidir.  
  
     Çözümlenmemiş simgesi hataları gidermek için kullanmayı deneyebilirsiniz [dumpbin.exe](../build/reference/dumpbin-reference.md) binary tanımlanmış semboller incelemek için. Bir Kitaplığı'nda tanımlanan simgeleri görüntülemek üzere aşağıdaki komut satırını deneyin.  
  
    ```cpp  
    dumpbin.exe /LINKERMEMBER somelibrary.lib  
    ```  
  
-   **alır ve _getws** [alır](../c-runtime-library/gets-getws.md) ve [_getws](../c-runtime-library/gets-getws.md) işlevleri kaldırıldı. Güvenli bir şekilde kullanılamadığından alır işlevi C11 C Standart kitaplığında kaldırılmıştır. _Getws işlevi eşdeğer bir Microsoft uzantısı olan alır ancak geniş dizeleri. Bu işlevler için alternatif, kullanımını göz önünde bulundurun [fgets](../c-runtime-library/reference/fgets-fgetws.md), [fgetws](../c-runtime-library/reference/fgets-fgetws.md), [gets_s](../c-runtime-library/reference/gets-s-getws-s.md), ve [_getws_s](../c-runtime-library/reference/gets-s-getws-s.md).  
  
-   **_cgets ve _cgetws** [_cgets](../c-runtime-library/cgets-cgetws.md) ve [_cgetws](../c-runtime-library/cgets-cgetws.md) işlevleri kaldırıldı. Bu işlevler için alternatif, kullanımını göz önünde bulundurun [_cgets_s](../c-runtime-library/reference/cgets-s-cgetws-s.md) ve [_cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).  
  
-   **Sonsuzluk ve NaN biçimlendirme** önceki sürümlerde, sonsuz ve NaN MSVC özgü sentinel dizeler kümesi kullanılarak biçimlendirilmiş.  
  
    -   Sonsuz: 1. #INF  
  
    -   Sessiz NaN: 1. #QNAN  
  
    -   Sinyal NaN: 1. #SNAN  
  
    -   Belirsiz NaN: 1. #IND  
  
     Bunlardan herhangi bir oturum tarafından öneki ve biraz daha farklı alan genişliği ve duyarlık bağlı olarak biçimlendirilmiş olabilir (bazen olağan dışı efektleri ile örneğin printf ("%.2f\n", SONSUZLUK) 1 yazdıracak. #J #INF "bir duyarlık yuvarlanmasını çünkü" 2 rakamı). Yeni gereksinimleri nasıl Biçimlendirilecek sonsuz ve NaN olduğunuza C99 sunmuştur. MSVC uygulama artık bu gereksinimleri için uygundur. Yeni dizeler aşağıdaki gibidir:  
  
    -   Sonsuz: INF  
  
    -   Quiet NaN: nan  
  
    -   NaN sinyal: nan(snan)  
  
    -   Belirsiz NaN:nan(ind)  
  
     Bunları herhangi biri, bir oturum tarafından önek. Büyük harf biçim belirticisi ise dizeleri büyük harf (INF) INF yerine yazdırılır sonra (%F %f yerine) kullanılan olarak gereklidir.  
  
     [Scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) işlevleri gidiş printf ve scanf aracılığıyla bu dizeler olacak şekilde bu yeni dizeler ayrıştırmak için değiştirilmiş olabilir.  
  
-   **Kayan nokta biçimlendirme ve ayrıştırma** yeni kayan nokta biçimlendirme ve algoritmaları ayrıştırma sunulan doğruluğunu artırmak için. Bu değişiklik [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) ve [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) işlevleri gibi işlevler aileleri ister [strtod](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md).  
  
     Eski biçimlendirme algoritmaları yalnızca sınırlı sayıda basamak oluşturur, ardından kalan ondalık sıfır ile doldurmanız. Bu özgün kayan noktalı değeri gidiş dönüş geri olacak dizeleri oluşturmak genellikle yeterli uygundur ancak, tam değer (veya bunların en yakın ondalık gösterimi) isterseniz harika değil. Yeni biçimlendirme algoritmaları, bir değeri temsil (veya belirtilen duyarlık doldurmak için) gibi çok sayıda basamak gerektiği şekilde oluşturur. Geliştirme örnek olarak; sonuçları iki büyük gücünü yazdırırken göz önünde bulundurun:  
  
    ```cpp  
    printf("%.0f\n", pow(2.0, 80))  
  
    ```  
  
    ```Output  
        Old:  1208925819614629200000000    New:  1208925819614629174706176  
    ```  
  
     Eski ayrıştırma algoritmaları giriş dizesinden yalnızca en fazla 17 önemli basamak düşünebileceğiniz ve basamakların rest atar. Bu çok dizenin temsil ettiği değerinin yaklaşık oluşturmak yeterli olduğundan ve sonucu genellikle çok doğru yuvarlatılmış yakın sonucudur. Yeni uygulama tüm mevcut basamak göz önünde bulundurur ve tüm girişleri (uzunluğu en fazla 768 basamak) için doğru yuvarlatılmış sonuç üretir. Ayrıca, bu işlevler şimdi (fesetround denetlenebilir) yuvarlama modu saygılı olun.  Potansiyel olarak bölme budur bu işlevler farklı sonuçlar çıktı çünkü davranışını değiştirin. Yeni sonuçları her zaman daha olduğunda eski sonuçları daha doğru.  
  
-   **Onaltılık ve sonsuz/NaN kayan noktası ayrıştırma** algoritmaları ayrıştırma kayan nokta şimdi onaltılık kayan nokta dizeleri (örneğin %a ve %A printf biçim belirticileri tarafından oluşturulan) ayrıştırır ve tüm sonsuz ve NaN dizelerde printf işlevleri tarafından yukarıda açıklandığı gibi oluşturulur.  
  
-   **%A ve %a sıfır doldurma** kayan %a ve %A biçim belirticileri biçimlendirmek onaltılık Mantis ve üs. ikili nokta sayısı. Önceki sürümlerde printf işlevleri yanlış sıfır paneli dizeleri olacaktır. Örneğin, printf ("%07.0a\n", 1.0) 00x1p + 0, burada yazdırmanız 0x01p + 0 yazdırabilirsiniz. Bu düzeltilmiştir.  
  
-   **%A ve %a duyarlık** kitaplığı önceki sürümlerinde 6 %A ve %a biçim belirticileri varsayılan kesinliğini oluştu. Varsayılan duyarlık 13 standart C ile uyumluluk için sunulmuştur.  
  
     Bu çalışma zamanı davranışı çıktısı bir biçim dizesi %A veya % kullanan herhangi bir işlev olarak farklıdır bir. Eski davranış %A tanımlayıcısı kullanılarak çıkışı "1.1A2B3Cp + 111" olabilir. Şimdi aynı değeri için çıktı, "1.1A2B3C4D5E6F7p + 111" şeklindedir. Eski davranışı elde etmek üzere, örneğin, %.6A duyarlık belirtebilirsiniz. Bkz: [duyarlık belirtimleri](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md#precision).  
  
-   **%F belirleyici** %F biçim/dönüştürme belirleyici artık desteklenmektedir. Büyük harf kullanılarak sonsuz ve NaN biçimlendirilmiş dışında %f biçim belirticisi için işlevsel olarak eşdeğerdir.  
  
     Önceki sürümlerde, F ve N uzunluğu değiştiricileri ayrıştırmak için kullanılan uygulama. Bu davranış tarihli geri bölümlenmiş adres alanları yaşını: Bu uzunluğu değiştiricileri Fp % veya %Ns olduğu kadar ve işaretçileri, yakın sırasıyla belirtmek için kullanılan. Bu davranış kaldırılmıştır. %F karşılaşılırsa, şimdi %F biçim belirteci işlem görür; %N karşılaşılırsa, artık geçersiz bir parametre kabul edilir.  
  
-   **Biçimlendirme üs** %e ve ondalık Mantis ve üs nokta sayısı kayan %E biçim belirticileri biçimi. Ayrıca %g ve %G biçim belirticileri bazı durumlarda bu formda sayıları biçimlendirme. Önceki sürümlerde CRT her zaman üç basamaklı üs dizelerle oluşturur. Örneğin, printf ("%e\n", 1.0) 1.000000e + 000 yazdıracak. Bu yanlış: C gerektiren üs yalnızca bir veya iki basamak kullanarak gösterilebilir ise, ardından yalnızca iki basamak yazdırılmak üzere olduğunu.  
  
     Visual Studio 2005'te bir genel uyumluluk anahtar eklendi: [_set_output_format](../c-runtime-library/set-output-format.md). Bir program uyumlu üs yazdırmayı etkinleştirmek için bu işlevi bağımsız değişken _two_dıgıt_exponent ile çağırabilirsiniz. Varsayılan davranış standartları uyumsuz üs yazdırma moduna değiştirildi.  
  
-   **Biçimlendirme dizesi doğrulama** önceki sürümlerde printf ve scanf işlevleri sessizce bazen olağan dışı efektleri ile birçok geçersiz biçim dizeleri kabul eder. Örneğin, % hlhlhld %d değerlendirilmesi. Tüm geçersiz biçim dizeleri artık geçersiz parametre olarak kabul edilir.  
  
-   **fopen modu dize doğrulama**  
  
     Önceki sürümlerde fopen ailesi işlevlerini sessizce bazı geçersiz mod dizeleri (örn. r + b +) kabul edildi. Geçersiz mod dizeleri şimdi algıladı ve geçersiz parametre olarak kabul edilir.  
  
-   **_O_U8TEXT modu**  
  
     [_Setmode](../c-runtime-library/reference/setmode.md) işlevi artık doğru şekilde rapor modu akışları in_O_U8TEXT modunda açılmış için. Kitaplık önceki sürümlerde, _O_WTEXT içinde açılmakta olarak böyle akışları raporlar.  
  
     UTF-8 kodlamasını Burada, Akışlar için _O_WTEXT modu kodunuzu yorumlar bu önemli bir değişiklik ise. Uygulamanızı UTF_8 desteklemiyorsa, bu giderek ortak kodlaması için destek eklemeyi düşünün.  
  
-   **snprintf ve vsnprintf** [snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) ve [vsnprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) işlevleri şimdi uygulanır. Eski kod genellikle tanımları makrosu sürümleri bu işlevler çünkü bunlar CRT kitaplık tarafından uygulanan değil, ancak bunlar artık daha yeni sürümlerinde gerekli sağlamıştır. Varsa [snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) veya [vsnprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) eklemeden önce makro olarak tanımlanan \<stdio.h >, şimdi derleme makro tanımlandığı belirten bir hata ile başarısız olur.  
  
     Normalde, bu sorun için düzeltme snprintf ya da kullanıcı kodu vsnprintf tüm bildirimler silmektir.  
  
-   **tmpnam oluşturur kullanılabilir dosya adları** önceki sürümlerde tmpnam ve tmpnam_s işlevleri (örneğin, \sd3c.) sürücüsünün kök dosya adlarında oluşturulur. Bu işlevler kullanılabilir dosya adı yolları geçici dizinde şimdi oluşturun.  
  
-   **Dosya kapsülleme** önceki sürümlerde, dosya türü tamamen tanımlanan \<stdio.h >, bir dosyaya erişmek ve kendi iç yapıları değiştirmek, kullanıcı kodu mümkün. Stdio kitaplığı, uygulama ayrıntılarını gizlemek için değiştirildi. Bunun bir parçası olarak tanımlandığı gibi dosya \<stdio.h > şimdi bir donuk türüdür ve üyeleri CRT dışında erişilemez.  
  
-   **_outp ve _inp** işlevleri [_outp](../c-runtime-library/outp-outpw-outpd.md), [_outpw](../c-runtime-library/outp-outpw-outpd.md), [_outpd](../c-runtime-library/outp-outpw-outpd.md), [_inp](../c-runtime-library/inp-inpw-inpd.md), [_inpw](../c-runtime-library/inp-inpw-inpd.md), ve [_inpd](../c-runtime-library/inp-inpw-inpd.md) kaldırıldı.  
  
#### <a name="stdlibh-malloch-and-sysstath"></a>\<stdlib.h >, \<malloc.h >, ve \<sys/stat.h >  
  
-   **strtof ve wcstof** strtof ve wcstof işlevleri değeri float gösterilebilir değilken errno ERANGE için ayarlanamadı. Bu düzeltilmiştir. (Bu hatayı bu iki işlevleri; strtod, wcstod, strtold belirli ve wcstold işlevlerinin etkilenmemesini unutmayın.) Bu değişiklik yeni bir çalışma zamanı olur.  
  
-   **Ayırma işlevleri hizalı** önceki sürümlerde hizalanmış ayırma işlevleri (_aligned_malloc, _aligned_offset_malloc, vb.) sessiz bir hizalama 0 olan bir bloğun isteklerini kabul eder. İstenen hizalama güç iki hangi sıfır olmalıdır. Bu sabit ve 0 istenen hizalamasını artık geçersiz bir parametre kabul edilir. Bu değişiklik yeni bir çalışma zamanı olur.  
  
-   **Yığın işlevleri** _heapadd, _heapset ve _heapused işlevleri kaldırıldı. Windows yığın kullanmak için CRT güncellendiğinden bu yana bu işlevler işlevsel olmuştur.  
  
-   **smallheap** smalheap bağlantı seçeneği kaldırılmıştır. Bkz: [bağlantı seçenekleri](../c-runtime-library/link-options.md).  
  
#### <a name="stringh"></a>\<String.h >  
  
-   **wcstok** wcstok işlevi imza ne C Standart tarafından gerekli eşleşecek şekilde değiştirildi. Kitaplık önceki sürümlerinde, bu işlev imzası oluştu:  
  
    ```cpp  
    wchar_t* wcstok(wchar_t*, wchar_t const*)  
    ```  
  
     İç, bir iş parçacığı başına bağlamı için strtok gerçekleştirilir gibi çağrıları arasında durumunu izlemek için kullanılır. İmza wchar_t * wcstok işlevi artık sahiptir (wchar_t\*, wchar_t const\*, wchar_t\*\*) ve bağlam işlevin üçüncü bağımsız değişken olarak geçirmek çağrıyı gerektirir.  
  
     Yeni bir _wcstok işlev taşıma kolaylaştırmak için eski imzayla eklendi. C++ kodu derleme sırasında da aynı zamanda eski imzası wcstok satır içi yüklemesini yoktur. Bu aşırı kullanım dışı bırakıldı olarak bildirildi. C kodu define_CRT_NON_CONFORMING_WCSTOK wcstok yerine kullanılacak _wcstok neden olabilir.  
  
#### <a name="timeh"></a>\<time.h >  
  
-   **Saat** önceki sürümlerde, [saati](../c-runtime-library/reference/clock.md) işlevi Windows API'si kullanılarak gerçekleştirilen [GetSystemTimeAsFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724397.aspx). Bu uygulama ile clock işlevi sistem saatini hassas ve bu nedenle mutlaka monoton değildi. Clock işlevi cinsinden reimplemented [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904.aspx) ve monoton sunulmuştur.  
  
-   **fstat ve _utime** önceki sürümlerde, [_stat](../c-runtime-library/reference/stat-functions.md), [fstat](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md), ve [_utime](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) işlevleri işlemek günışığından yanlış. Yaz Saati değilmiş gibi Visual Studio 2013'ten önce tüm bu işlevlerin yanlış Standart Saati kez ayarlanır.  
  
     Visual Studio 2013'te sorun _stat ailesi işlevlerini sabit ancak işlevlerin fstat ve _utime ailelerindeki benzer sorunlar değil düzeltilen. Bu sorunların tutarsızlığı nedeniyle işlevleri arasında gerektiriyordu. Tüm bu işlevlerin şimdi günışığından doğru ve tutarlı bir şekilde işlemek için işlevleri fstat ve _utime aileleri şimdi düzeltildi.  
  
-   **asctime** önceki sürümlerde, [asctime](../c-runtime-library/reference/asctime-wasctime.md) işlevi paneli tek basamaklı günleri sıfır, örneğin: Cum Haz 06 08:00:00 2014. Bu tür gün başında boşluk ile örneğin Cum Haz 6 dolgu uygulanması emin belirtilmesini gerektiriyor 08:00:00 2014. Bu düzeltilmiştir.  
  
-   **strftime ve wcsftime** strftime ve wcsftime işlevleri şimdi %c desteği, %D, %e, %F, %g, %G, %s, %n, %r, %R, %t, %T, %u ve %V biçim belirticileri. Ayrıca, E ve O değiştiricileri Ayrıştırılan göz ardı ancak.  
  
     %C biçim belirteci geçerli yerel ayar için bir "uygun tarih ve Saat Gösterimi" oluşturan olarak belirtilir. C yerel %a %b %e %T %Y ile aynı olması için bu gösterim gereklidir. Bu aynı form asctime tarafından üretilen aynıdır. Önceki sürümlerde, GG/AA/YY ss: dd: gösterimi kullanılarak kez %c biçim belirteci hatalı biçimlendirilmiş. Bu düzeltilmiştir.  
  
-   **timespec ve TIME_UTC** \<time.h > Üstbilgi şimdi timespec türü ve C11 standart timespec_get işlevi tanımlar. Ayrıca, timespec_get işlevi ile kullanılmak üzere TIME_UTC makrosu şimdi tanımlanır. Çakışan tanım bunlardan birine sahip code için önemli bir değişiklik budur.  
  
-   **CLOCKS_PER_SEC** CLOCKS_PER_SEC makrosu C dil gerektirdiği türü clock_t tamsayıya şimdi genişletir.  
  
####  <a name="BK_STL"></a>C++ Standart Kitaplığı  
 Yeni iyileştirmeleri ve hata ayıklama denetimlerini etkinleştirmek için, C++ Standart Kitaplığı'nın Visual Studio uygulaması bir sürümden sonraki bir sürüme ikili uyumluluğu kasıtlı olarak bozar. Bu nedenle, C++ Standart Kitaplığı kullanıldığında, farklı sürümlerin kullanımıyla derlenmiş nesne dosyaları ve statik kitaplıklar tek bir ikili dosya (EXE veya DLL) halinde karma yapılabilir ve C++ Standart Kitaplığı nesneleri, farklı sürümler kullanılarak derlenmiş ikili dosyalar arasında geçirilemez. Bu tür karmalar, _MSC_VER uyuşmazlıklarıyla ilgili bağlayıcı hataları verir. (_MSC_VER olduğu derleyicinin ana sürüm içeren makrosu — Örneğin, Visual Studio 2013 için 1800.) Bu onay DLL karıştırma algılayamaz ve Visual Studio 2008 veya önceki bir sürümü içeren karıştırma algılayamıyor.  
  
-   **C++ Standart Kitaplığı dosyaları** C++ Standart Kitaplığı üstbilgilerini INCLUDE yapısında bazı değişiklikler yapılmıştır. C++ Standart Kitaplığı üstbilgilerini birbirine belirtilmeyen şekillerde dahil izin verilmez. Genel olarak, kodunuzu yazma, böylece tüm C++ Standart göre gerektiğini ve hangi C++ Standart Kitaplığı üstbilgilerini hangi bir C++ Standart Kitaplığı üstbilgileri dahil kullanmaz üstbilgileri dikkatle içerir. Bu kod taşınabilir sürümleri ve platformda hale getirir. En az iki üstbilgi değişiklikler Visual Studio 2015'te kullanıcı kodu etkiler. İlk olarak, \<dize > artık içeren \<yineleyici >. İkinci, \<tanımlama grubu > şimdi tüm eklemeden std::array bildirir \<dizi >, hangi kod yapıları aşağıdaki bileşimi kodda kesme: kodunuzu "dizi" adlı bir değişken varsa ve kullanma yönergesi "kullanma ad alanı std; ", ve C++ Standart Kitaplığı üstbilgisini (gibi \<işlevsel >) içeren \<tanımlama grubu >, şimdi std::array bildirir.  
  
-   **steady_clock** \<chrono > uygulaması [steady_clock](../standard-library/steady-clock-struct.md) steadiness ve monotonicity C++ Standart gereksinimlerini karşılamak üzere değişti. steady_clock temel şimdi [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904.aspx) ve high_resolution_clock şimdi typedef steady_clock için. Sonuç olarak, Visual Studio'da steady_clock::time_point chrono::time_point < steady_clock >; için bir typedef sunulmuştur Ancak, bu mutlaka diğer uygulamalardan söz konusu değildir.  
  
-   **allocators ve const** biz şimdi her iki tarafında const bağımsız değişkenleri kabul etmek için ayırıcısı eşitlik/eşitsizlik karşılaştırmaları gerektirir.  Bu işleç, allocators aşağıdaki gibi tanımlayın ise:  
  
    ```cpp  
    bool operator==(const MyAlloc& other)  
    ```  
  
     Const üye olarak bildirme güncelleştirmeniz gerekir.  
  
    ```cpp  
    bool operator==(const MyAlloc& other) const  
    ```  
  
-   **const öğeleri** C++ Standart const öğelerin kapsayıcıları her zaman Yasak (vektör gibi\<const T > veya\<const T >). Visual Studio 2013 ve önceki gibi kapsayıcıları kabul edildi. Geçerli sürümde, bu tür kapsayıcıları derlemek başarısız.  
  
-   **Std::Allocator:: ayırması** Visual Studio 2013 ve önceki n geçirilen bağımsız değişken std::allocator::deallocate(p, n) yoksayıldı.  C++ Standart n çağrılmasını ilk bağımsız değişken tahsis gibi p döndürülen geçirilen değerine eşit her zaman gereklidir. Ancak, geçerli sürümde değerindeki bir n sahip olduğunu denetlenir. Hangi standart gerektirir farklı bağımsız değişkenleri n geçirir kodu çalışma zamanında kilitlenmesine neden olabilir.  
  
-   **hash_map ve hash_set** hash_set ve standart üstbilgi dosyaları hash_map Visual Studio 2015'te kullanım dışı bırakılmış ve bir sonraki sürümde kaldırılacak. Unordered_map ve unordered_set kullanın.  
  
-   **karşılaştırıcıları ve operator()** ilişkilendirilebilir kapsayıcıları ( \<harita > Aile) şimdi işleçleri çağrı const aranabilir işlevi sağlamak için bunların karşılaştırıcıları gerektirir. Aşağıdaki kod bir karşılaştırıcı sınıf bildirimindeki şimdi derlemek başarısız olur:  
  
    ```cpp  
    bool operator()(const X& a, const X& b)  
    ```  
  
     Bu hatayı gidermek için işlev bildirimi değiştirin:  
  
    ```cpp  
    bool operator()(const X& a, const X& b) const  
    ```  
  
-   **tür özellikleri** C++ taslak standart önceki bir sürümünden tür özellikleri için eski adlarını kaldırıldı. Bunlar, C ++ 11 değiştirildi ve C ++ 11 değerlere Visual Studio 2015'te güncelleştirildi. Aşağıdaki tabloda eski ve yeni adlarını gösterir.  
  
    |Eski adı|Yeni bir ad|  
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
  
-   **Launch::ANY ve launch::sync ilkeleri** standart olmayan launch::any ve launch::sync ilkeleri kaldırıldı. Bunun yerine, launch::any için başlatma: zaman uyumsuz &#124; kullanın başlatma: ertelenmiş. Launch::Sync için launch::deferred kullanın. Bkz: [launch numaralandırması](../standard-library/future-enums.md#launch).  
  
####  <a name="BK_MFC"></a>MFC ve ATL  
  
-   **Microsoft Foundation sınıfları (MFC)** Visual Studio içinde bir "Tipik" yükleme büyük boyutuna nedeniyle artık eklenmiştir. MFC yüklemek için Visual Studio 2015 kurulumunda özel yükleme seçeneğini seçin. Visual Studio 2015 yüklü zaten varsa, Visual Studio Kurulumu yeniden çalıştırmayı özel yükleme seçeneği seçerek ve Microsoft temel sınıfları seçme MFC yükleyebilirsiniz. Visual Studio Kurulumu Denetim Masası, programlar ve özellikler veya yükleme medyasından yeniden çalıştırabilirsiniz.  
  
     Visual C++ Yeniden Dağıtılabilir Paketi'nde bu kitaplık halen yer almaktadır.  
  
####  <a name="BK_ConcRT"></a>Eşzamanlılık Çalışma zamanı  
  
-   **Windows.h concurrency::Context::Yield ile çakışan gelen makrosu verim** eşzamanlılık çalışma zamanı önceden #undef Windows.h h ve concurrency::Context tanımlanan verim makrosu arasındaki çakışmaları önleme verim makrosu tanımsız için kullanılır: : Ödeme işlevi. Bu #undef kaldırıldı ve yeni bir çakışmayan eşdeğer API çağrısı [concurrency::Context::YieldExecution](../parallel/concrt/reference/context-class.md#yieldexecution) eklendi. Verim çakışıyor geçici olarak çözmek için bunun yerine YieldExecution işlevi çağırmak için kodunuzu güncelleştirin veya verim işlev adı aşağıdaki örnekteki gibi çağrısı sitelerdeki parantez ile çevrelendiğinden:  
  
    ```cpp  
    (concurrency::Context::Yield)();  
    ```  
  
## <a name="compiler-conformance-improvements-in-visual-studio-2015"></a>Visual Studio 2015'te derleyici uyumluluğu geliştirmeleri  
 Kod önceki sürümlerinden yükseltme yaparken, Visual Studio 2015'te yapılan uygunluk geliştirmeleri nedeniyle derleyici hatalarını hatalarla karşılaşabilirsiniz. Bu geliştirmeler, Visual Studio'nun önceki sürümlerinden ikili uyumluluğu bozmadığını ancak burada Hiçbiri önce gösterilen derleyici hataları üretebilir. Daha fazla bilgi için bkz: [Visual C++ ne ait yeni 2003 2015 aracılığıyla](../porting/visual-cpp-what-s-new-2003-through-2015.md).  
  
 Visual Studio 2015'te derleyici uyumluluğu devam eden iyileştirmeler derleyici mevcut kaynak kodunuzu nasıl anlar bazen değiştirebilirsiniz. Bu gerçekleştiğinde, yapı veya önceden oluşturulmuş ve düzgün çalışmasına görünüyor kodu dahi davranış farklılıkları sırasında yeni ya da farklı hatalarla karşılaşabilirsiniz.  
  
 Neyse ki, bu farklılıklar çok az kayıpla veya hiç kaynak kodunuzu çoğunu üzerinde etkisi ve kaynak kodu veya başka değişiklikler bu farklılıklar gidermenin gerekli olduğunda, düzeltmeleri genellikle küçük ve düz ilet. Birçok değiştirilmesi gerekebilir önceden kabul edilebilir kaynak kod örnekleri dahil ettiğiniz *(önce)* ve bunları düzeltmek için düzeltmeler *(sonra)*.  
  
 Bu farklılıklar, kaynak kodu veya diğer yapı yapıları etkileyebilir karşın, bunların Visual Studio sürümleri için güncelleştirmeler arasında ikili uyumluluğu etkilemez. Değişiklik, daha ciddi bir tür *değişiklik çiğnemekten* ikili uyumluluğu etkileyebilir, ancak bu tür bir ikili uyumluluğu sonlarını yalnızca ana Visual Studio sürümleri arasında oluşur. Örneğin, Visual Studio 2013 ve Visual Studio 2015 arasında. Visual Studio 2013 ve Visual Studio 2015 arasında oluştu önemli değişiklikler hakkında daha fazla bilgi için bkz: [Visual Studio 2015 uyumluluğu değişiklikleri](#VC_2015).  
  
-   [Visual Studio 2015'te uygunluk geliştirmeleri](#VS_RTM)  
  
-   [Güncelleştirme 1 uygunluk yenilikleri](#VS_Update1)  
  
-   [Güncelleştirme 2 uygunluk yenilikleri](#VS_Update2)  
  
-   [Güncelleştirme 3 uygunluk yenilikleri](#VS_Update3)  
  
###  <a name="VS_RTM"></a>Visual Studio 2015'te uygunluk geliştirmeleri  
  
-   /ZC:forScope-seçeneği  
  
     Derleyici seçeneği **/Zc:forScope-** kullanım dışıdır ve gelecek sürümde kaldırılacak.  
  
    ```cpp  
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release  
    ```  
  
     Seçeneği genellikle kullanır, burada, standart göre kullanıcılar fazlası kapsam dışında noktadan sonra değişkenleri döngü standart olmayan kod izin vermek üzere kullanıldı. /Za bu yana /Za seçeneğiyle derlediğiniz zaman yalnızca gerekli kullanarak bir döngü sonundan her zaman izin sonra döngü değişkeni için. (Örneğin, kodunuzu diğer derleyiciler için taşınabilir tasarlanmamıştır) standartları uyumluluğu hakkında önemli değil, /Za seçeneğini devre dışı bırakın (veya dil uzantılarını devre dışı bırakma özelliğini Hayır olarak ayarlayın). Taşınabilir, standartlara uygun kod yazma hakkında dikkat edin, böylece bu değişkenleri bildirimi döngü dışında bir nokta taşıyarak standardına uygun kodunuzu yeniden yazma.  
  
    ```cpp  
    // C2065 expected  
    int main() {  
        // Uncomment the following line to resolve.  
        // int i;  
        for (int i = 0; i < 1; i++);  
        i = 20;   // i has already gone out of scope under /Za  
    }  
  
    ```  
  
-   **/ZG derleyici seçeneği**  
  
     /Zg derleyici seçeneği (işlev prototipleri oluşturma), artık mevcut değil. Bu derleyici seçeneği önceden kullanımdan kaldırılmıştır.  
  
-   Artık birim testleri C + ile çalıştırabilirsiniz +/ CLI mstest.exe ile komut satırından. Bunun yerine, vstest.console.exe kullanın. Bkz: [VSTest.Console.exe komut satırı seçenekleri](/devops-test-docs/test/vstest-console-exe-command-line-options).  
  
-   **mutable anahtar sözcüğü**  
  
     `mutable` Depolama sınıfı tanımlayıcısı burada önceden derlenmiş hatasız yerlerde artık verilir. Derleyici Hatası C2071 şimdi verir (geçersiz depolama sınıfı). Standart göre değişebilir tanımlayıcı yalnızca sınıfı veri üyesi adlarına uygulanabilir ve const veya statik bildirilen adlarına uygulanamaz ve üyeleri başvurmak için uygulanamaz.  
  
     Örneğin, aşağıdaki kodu göz önünde bulundurun:  
  
    ```cpp  
    struct S   
    {  
        mutable int &r;  
    };  
  
    ```  
  
     Derleyici önceki sürümlerinde bu kabul ancak şimdi derleyici aşağıdaki hata verir:  
  
    ```Output  
    error C2071: 'S::r': illegal storage class  
    ```  
  
     Hatayı düzeltmek için basitçe yedekli mutable anahtar sözcüğü kaldırın.  
  
-   **char_16_t ve char32_t**  
  
     Artık kullanabilirsiniz `char16_t` veya `char32_t` bir typedef adlarda olarak çünkü bu türleri artık yerleşik kabul edilir. Kullanıcılar ve char16_t ve char32_t uint16_t ve uint32_t, diğer adlar sırasıyla tanımlamak için kitaplık yazarları için ortak.  
  
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
  
     Kodunuzu güncelleştirmek için typedef bildirimleri kaldırın ve bu adları birbiriyle çakışır diğer tanımlayıcıları yeniden adlandırın.  
  
-   **Tür olmayan şablon parametreleri**  
  
     Açık şablon değişkenlerini sağladığınızda tür olmayan şablon parametreleri içeren belirli kod artık doğru türü uyumluluk için kontrol edilir. Visual Studio'nun önceki sürümlerinde hatasız derlenmiş Örneğin, aşağıdaki kodu.  
  
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
  
     Şablon parametresi türü şablon bağımsız değişken eşleşmediği için geçerli derleyici doğru bir hata verir (const üyesi için bir işaretçi parametredir, ancak const olmayan işlev f):  
  
    ```Output  
    error C2893: Failed to specialize function template 'void S2::f(void)'note: With the following template arguments:note: 'C=S1'note: 'Function=S1::f'  
    ```  
  
     Kodunuzda bu hatayı gidermek için kullandığınız şablon bağımsız değişken türü şablon parametresi türü eşleştiğinden emin olun.  
  
-   **__declspec(align)**  
  
     Derleyici artık kabul `__declspec(align)` işlevlerde. Bu her zaman gözardı edildi ancak şimdi bir derleyici hatası oluşturur.  
  
    ```cpp  
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations  
    ```  
  
     Bu sorunu gidermek için kaldırın `__declspec(align)` işlev bildirimi gelen. Herhangi bir etkisi sahip olduğundan, kaldırarak herhangi bir şeyi değiştirmez.  
  
-   **Özel durum işleme**  
  
     Birkaç özel durum işleme için değişiklik vardır. İlk olarak, özel durum nesneleri copyable veya taşınabilir olması gerekir. Aşağıdaki kod derlenmiş [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], ancak içinde derlenmiyor [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]:  
  
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
  
     Nesne bir özel durum işleme normal seyrinde olduğu sürece kopyalanamaz şekilde kopya oluşturucu özel sorunudur. Kopya Oluşturucu bildirilmişse aynı durum geçerlidir `explicit`.  
  
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
  
     Kodunuzu güncelleştirmek için özel durum nesnesi kopya Oluşturucu ortak ve işaretlenmemiş olduğundan emin olun `explicit`.  
  
     Değere göre bir özel durum yakalama özel durum nesnesi copyable olmasını gerektirir. Aşağıdaki kod derlenmiş [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], ancak içinde derlenmiyor [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]:  
  
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
  
     İçin parametre türü değiştirerek bu sorunu gidermek `catch` bir başvuru.  
  
    ```cpp  
    catch (D& d)  
    {  
    }  
  
    ```  
  
-   **Makroları tarafından izlenen dize değişmez değerleri**  
  
     Derleyici artık kullanıcı tanımlı değişmez değerler destekler. Dize değişmez değerleri müdahalede bulunan tüm boşluk olmadan makroları ve ardından hataları veya beklenmeyen sonuçlara neden, kullanıcı tanımlı değişmez değerler, sonuç olarak yorumlanır. Örneğin, aşağıdaki kod önceki derleyicileri başarıyla derlenmiş:  
  
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
  
     Derleyici bu bir dize olarak değişmez değer olarak "hello"yok"genişletilir bir makro tarafından izlenen" yorumlanır ve iki dize değişmez değerleri birine ardından birleştirilmiş. İçinde [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]derleyici bu kullanıcı tanımlı bir sabit değer olarak yorumlar, ancak tanımlı hiçbir eşleşen kullanıcı tanımlı değişmez değer _x olduğundan, bir hata verir.  
  
    ```Output  
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found  
    note: Did you forget a space between the string literal and the prefix of the following string literal?  
    ```  
  
     Bu sorunu gidermek için dize sabit değeri ile makrosu arasında bir boşluk ekleyin.  
  
-   **Bitişik dize değişmez değerleri**  
  
     Benzer şekilde önceki, dizesini ayrıştırma, ilgili değişiklikler nedeniyle hiçbir boşluk olmadan bitişik dize değişmez değerleri (ya da geniş veya dar karakteri dize değişmez değerleri) tek bir birleştirilmiş dizeyi Visaul C++ önceki sürümlerinde yorumlanan. İçinde [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], artık iki dizeyi arasında boşluk eklemeniz gerekir. Örneğin, aşağıdaki kodu değiştirilmelidir:  
  
    ```cpp  
    char * str = "abc""def";  
    ```  
  
     Bir alanı arasında iki dize eklemeniz yeterlidir.  
  
    ```cpp  
    char * str = "abc" "def";  
    ```  
  
-   **Yeni yerleştirme ve silme**  
  
     Bir değişiklik delete işleci ilkelerinizle uyumlu C ++ 14 standart getirmek için yapılmıştır. Standartlar değişiklik ayrıntılarını bulunabilir [C++ boyutta ayırmayı kaldırma](http://isocpp.org/files/papers/n3778.html). Değişiklikleri boyutu parametresi alan genel delete işleci biçiminde ekleyin. (Yerleştirme yeni işleciyle karşılık gelecek şekilde) aynı imzayla daha önce bir delete işleci kullanıyorsanız, derleyici hatası alırsınız sonu değişikliktir (burada yeni yerleştirme kullanılır, beri noktada oluşur C2956 o kod derleyici burada uygun eşleşen tanımlamayı dener konumda delete işleci).  
  
     İşlev `void operator delete(void *, size_t)` edildi yerleştirme yeni işlev için karşılık gelen bir yerleştirme delete işleci "void \* new işleci (size_t, size_t)" C ++ 11. C ++ 14 boyutlu ayırmayı kaldırma ile bu silme işlevi sunulmuştur bir *normal ayırmayı kaldırma işlevi* (genel delete işleci). Standart bir yerleştirme yeni kullanımını karşılık gelen bir silme işlevini arar ve her zamanki ayırmayı kaldırma işlevi bulur, program hatalı oluşturulmuş olmasını gerektirir.  
  
     Örneğin, kodunuzu yeni bir yerleştirme ve yerleştirme delete tanımlar varsayın:  
  
    ```cpp  
    void * operator new(std::size_t, std::size_t);  
    void operator delete(void*, std::size_t) noexcept;  
  
    ```  
  
     Sorun, tanımladığınız yerleştirme delete işleci yeni küresel ölçekli delete işleci arasındaki işlevi imzaları eşlemesinde nedeniyle oluşur. Farklı bir tür size_t dışındaki tüm yerleştirme için yeni kullanmak ve delete işleçleri olup olmadığını göz önünde bulundurun.  Size_t typedef türünü derleyici bağımlı olduğunu unutmayın; İmzasız Int MSVC'için bir typedef olur. Bu gibi bir enum türü kullanmak iyi bir çözümdür:  
  
    ```cpp  
    enum class my_type : size_t {};  
  
    ```  
  
     Ardından, yerleştirme yeni tanımınız değiştirebilir ve bu tür size_t yerine ikinci bağımsız değişken olarak kullanmak için silebilirsiniz. Ayrıca yeni türü geçirmek için yeni yerleştirme çağrıları güncelleştirmeniz gerekir (kullanarak örneğin, `static_cast<my_type>` tamsayı değerini dönüştürmek için) ve tanımını yeni güncelleştirme ve tamsayı türüne yayınlanamıyor silin. Bunun için bir numaralandırma kullanmanız gerekmez; sınıf türü size_t üyesi ile de çalışır.  
  
     Bir alternatif yeni yerleştirme tamamen ortadan kaldırmak mümkün olabilir çözümüdür. Kodunuzu yerleştirme yeni burada yerleştirme bağımsız değişkeni olan nesne boyutunu tahsis edilen veya silinen, sonra boyutlu ayırmayı kaldırma özelliği, kendi özel bellek havuzu kodunuzu değiştirmek uygun olabilir ve, elden çıkarabilirsiniz bellek havuzundaki uygulamak için kullanıyorsa, yerleştirme işlevler ve yalnızca kendi iki bağımsız değişken delete işleci yerine yerleştirme işlevlerini kullanın.  
  
     Kodunuzu hemen güncelleştirmek istemiyorsanız, derleyici seçeneği /Zc:sizedDealloc-kullanarak eski davranışa geri dönebilirsiniz. Bu seçeneği kullanırsanız, iki bağımsız değişken silme işlevleri mevcut değil ve yerleştirme delete operatörünüze ile bir çakışma neden olmaz.  
  
-   **Birleşim veri üyeleri**  
  
     Veri üyeleri birleşimler artık başvuru türleri olabilir. Başarıyla derlenen aşağıdaki kod [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], ancak bir hata üretir [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)].  
  
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
  
     Yukarıdaki kod aşağıdaki hatalar üretir:  
  
    ```Output  
  
    test.cpp(67): error C2625: 'U2::i': illegal union member; type 'int &' is reference type  
    test.cpp(70): error C2625: 'U3::i': illegal union member; type 'int &' is reference type  
  
    ```  
  
     Bu sorunu gidermek için başvuru türleri bir işaretçi veya bir değeri değiştirin. Bir işaretçi türü değiştirilmesi birleşim alan kullanan kodu değişiklikleri gerektirir. Kod bir değer ile değiştirmek birleşim türlerini alanları aynı bellek paylaşmak olduğundan, diğer alanlar etkileyen birleşim içinde depolanan verileri değiştirirsiniz. Değer boyutuna bağlı olarak, bu da UNION boyutu değişebilir.  
  
-   Anonim birleşimler için standart daha fazla uyumluluğunu sunulmuştur. Derleyici önceki sürümlerini bir açık oluşturucu ve yıkıcı anonim birleşimler için oluşturulur. Bunlar de silinir [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)].  
  
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
  
     Yukarıdaki kod aşağıdaki hatası oluşturur [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]:  
  
    ```cpp  
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function  
    note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here  
  
    ```  
  
     Bu sorunu çözmek için kendi tanımları oluşturucusu ve/veya yıkıcı sağlayın.  
  
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
  
-   **Anonim yapılar ile birleşimler**  
  
     Standart uygun için anonim yapılar Birleşimlerdeki üyeleri için çalışma zamanı davranışı değişmiştir. Bu tür bir birleşim oluşturulduğunda UNION anonim yapısı üyeleri Oluşturucusu artık dolaylı olarak adlandırılır. Ayrıca, UNION kapsam dışına çıktığında yıkıcı bir birleşim anonim yapısı üyeler için artık dolaylı olarak adlandırılır. UNION U yıkıcı sahip adlandırılmış bir yapı S olan bir üyeyi içeren bir anonim yapısı içeren aşağıdaki kod, göz önünde bulundurun.  
  
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
  
     İçinde [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], S Oluşturucusu UNION oluşturulduğunda ve işlev f yığınının Temizlenen S yıkıcı denir denir. Ancak [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], oluşturucusu ve yıkıcı değil olarak adlandırılır. Derleyici bu davranış değişikliği hakkında bir uyarı verir.  
  
    ```Output  
    warning C4587: 'U::s': behavior change: constructor is no longer implicitly calledwarning C4588: 'U::s': behavior change: destructor is no longer implicitly called  
    ```  
  
     Özgün davranışını geri yüklemek için anonim yapısı bir ad verin. Anonim olmayan yapılar çalışma zamanı davranışını derleyici sürümü bağımsız olarak aynıdır.  
  
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
  
     Alternatif olarak, yeni işlevler oluşturucusu ve yıkıcı kodu taşımayı deneyin ve bu işlevler oluşturucusu ve UNION yıkıcı çağrıları ekleyin.  
  
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
  
-   **Şablon çözümleme**  
  
     Şablonlar için ad çözümlemesi için değişiklikler yapıldı. Bir ad çözümlemesi için aday değerlendirirken C++'da, göz önünde bulundurarak olası eşleşmeler olarak bir veya daha fazla adlarla geçersiz şablonu örneklemesi üreten durumda olabilir. Bu geçersiz örneklemesi normalde derleyici hataları, SFINAE (değiştirme hatası olmayan bir hata) bilinen bir ilkeye neden olmaz.  
  
     Şimdi, bir sınıf şablonu uzmanlaşması örneği oluşturmak için derleyici SFINAE gerektirir, bu işlem sırasında oluşan hataları derleyici hataları demektir. Önceki sürümlerde derleyici böyle hataları yoksayma. Örneğin, aşağıdaki kodu göz önünde bulundurun:  
  
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
  
     Geçerli derleyicisi ile derleme yaparsanız, aşağıdaki hatayı alıyorsunuz:  
  
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
  
     İs_base_of ilk çağırma noktasında sınıfı kullandığınız olmasıdır ' henüz tanımlanmamış.  
  
     Bu durumda, düzeltme sınıf tanımlanan kadar böyle tür özellikleri kullanmamaktır. Kod dosyasının başlangıcına B ve D tanımlarını taşırsanız, hata çözümlenir. Tanımları üstbilgi dosyalarında değilse, sorunlu şablonları kullanılmadan önce herhangi bir sınıf tanımları derlenmiş emin olmak üst bilgi dosyaları Include deyimleri sırasını denetleyin.  
  
-   **Kopya oluşturucuları**  
  
     Hem de [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] ve Visual Studio 2015 derleyici oluşturan bir sınıf için bir kopya Oluşturucu bu sınıfın bir kullanıcı tarafından tanımlanan taşıma oluşturucusuna ancak hiçbir kullanıcı tarafından tanımlanan kopya Oluşturucu varsa. Dev14 içinde bu örtük olarak oluşturulmuş kopya Oluşturucu de işaretlenmiş "delete =".  

<!--From here to VS_Update1 added 04/21/2017-->

-   **ana "C" şimdi bir dönüş türü gerektirir extern bildirildi.**  

Aşağıdaki kod artık C4430 üretir. 
```cpp
extern "C" __cdecl main(){} // C4430
```
Hatayı düzeltmek için dönüş türü ekleyin:
```cpp
extern "C" int __cdecl main(){} // OK
```

 -   **TypeName bir üye başlatıcıdan izin verilmiyor**  

Aşağıdaki kod artık C2059 üretir:
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
Hatayı düzeltmek için kaldırma `typename` Başlatıcı gelen:
```cpp
S1() : T::type() // OK
...
```

-   **Depolama sınıfı açık özelleştirmeleri üzerinde göz ardı edilir.** 

Aşağıdaki kodda statik depolama sınıfı tanımlayıcısı göz ardı edilir 
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

-   **Sınıf şablonu içinde static_assert kullanılan bir sabiti her zaman başarısız olur.**  

Aşağıdaki kod static_assert her zaman başarısız olmasına neden olur:
```cpp
template <size_t some_value>
struct S1
{
    static_assert(false, "default not valid"); // always invoked

};

//other partial specializations here
```

Bu sorunu çözmek için bir yapı değeri kaydır:
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

-   **İletme bildirimleri için zorlanan kuralları. (Yalnızca C'ye geçerlidir)**  

Aşağıdaki kod artık C2065 üretir:
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

-   **İşlev işaretçi türlerinin daha tutarlı zorlama**  

Aşağıdaki kod artık C2197 üretir:

```cpp
typedef int(*F1)(int);
typedef int(*F2)(int, int);

void func(F1 f, int v1, int v2)
{
    f(v1, v2); // C2197
}
```

-   **Aşırı yüklenen işlevler belirsiz çağrıları**  

Aşağıdaki kod artık C266 üretir: 'N::bind': aşırı yüklenmiş işlevi belirsiz çağrısı
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

Hatayı düzeltmek için tam olarak bağlamak için çağrı nitelemek: N::bind(...). Bu değişiklik bildirimi bildirilmemiş tanımlayıcıdır (C2065) aracılığıyla ise, ancak, daha sonra bunu bunun yerine 'kullanılarak' bildirimiyle düzeltmek uygun olabilir.

ComPtr ve diğer türlerle Microsoft::WRL ad alanında bu deseni sıkça gerçekleşir.

-   **Yanlış adresini düzeltin**  

Aşağıdaki kod artık C2440 üretir: '=': dönüştürülemiyor ' türü *' için 'type'. Hata, değişiklik & (tür) (yazmak için) düzeltmek için ve (& (f()) f()).
 
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

-   **Değişmez dize değeri sabit bir dizidir**  

Aşağıdaki kod artık C2664 üretir: ' void f (void *)': 1 bağımsız değişkenden dönüştürülemiyor ' const char (*) [2]' için ' void *'
```cpp
void f(void *);
 
void h(void)
{
    f(&__FUNCTION__); 
    void *p = &"";
}
```

Hatayı düzeltmek için işlevi parametresi türü 'const void * için' değiştirin, aksi takdirde şuna h gövdesini değiştirin:

```cpp
void h(void)
{
    char name[] = __FUNCTION__;
    f( name); 
    void *p = &"";
}

```

-   **C ++ 11 UDL dizeleri**  

Aşağıdaki kod hatası C3688 şimdi oluşturur: Geçersiz değişmez değer soneki 'L'; değişmez değer işleci veya değişmez değer işleci şablon ' işleci "" M ' bulunamadı


```cpp
#define MACRO

#define STRCAT(x, y) x\#\#y

int main(){

    auto *val1 = L"string"MACRO;
    auto *val2 = L"hello "L"world";

    std::cout << STRCAT(L"hi ", L"there");
}
```
Hatayı düzeltmek için bu kodu değiştirin:

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
Yukarıdaki örnekte `MACRO` artık iki belirteçleri (makro tarafından izlenen bir dize) olarak ayrıştırılır.  Şimdi tek bir belirteç UDL ayrıştırılır.  Aynı L daha önce ayrıştırıldığında L "" M"" geçerlidir"" ve L "" ve şimdi L ayrıştırılır "" M ve "".

Dize birleştirme kuralları da L "a" "b" M "ab" eşdeğer olduğu anlamına gelir standart hale getirilmiştir. Visual Studio'nun önceki sürümleri farklı karakter genişliği dizelerle birleştirilmesi kabul etmedi.


-   **C ++ 11 kaldırılan karakter boş**  

Aşağıdaki kod hatası C2137 şimdi oluşturur: boş karakter sabiti

```cpp
bool check(wchar_t c){
    return c == L''; //implicit null character
}
```

Hatayı düzeltmek için bu kodu değiştirin:

```cpp
bool check(wchar_t c){
    return c == L'\0';
}
```

-   **Copyable olmadıklarından değeriyle MFC özel durum yakalandı olamaz**  

MFC uygulaması artık aşağıdaki kodda hata C2316 neden olur: 'D ': yıkıcı ve/veya kopya Oluşturucu erişilemez veya silinmiş olduğundan yakalanan olamaz

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
Kod düzeltmek için catch bloğu değiştirebilirsiniz ' catch (const D &)', ancak daha iyi çözüm genellikle MFC TRY/CATCH makroları kullanmaktır.

-   **alignof artık bir anahtar sözcüktür**  

Aşağıdaki kod hatası C2332 şimdi oluşturur: 'sınıfı': Etiket adı eksik. Kod düzeltmek için sınıfı yeniden adlandırın veya gerekir, yalnızca sınıf alignof, olarak aynı iş çalışıyorsa sınıfı new anahtar sözcüğü ile değiştirin.
```cpp
class alignof{}
```

-   **constexpr artık bir anahtar sözcüktür**  

Aşağıdaki kod hatası C2059 şimdi oluşturur: sözdizimi hatası: ')'. Kod düzeltmek için herhangi bir işlev veya "constexpr" adlı değişken adları yeniden adlandırmanız gerekir. 
```cpp
int constexpr() {return 1;}
```

-   **Taşınabilir türleri const olamaz**  

Bir işlev taşınacak hedeflenen bir türü geri döndüğünde, kendi dönüş türü const olmamalıdır.

-   **Silinen kopya oluşturucuları**  

Aşağıdaki kod artık C2280'ın üreten:: S(S &&)': silinen işlevi başvuru girişimi:

```cpp
struct S{
    S(int, int);
    S(const S&) = delete;
    S(S&&) = delete;
};

S s2 = S(2, 3); //C2280
```
Hatayı düzeltmek için doğrudan başlatma S2 için kullanın:
```cpp
struct S{
    S(int, int);
    S(const S&) = delete;
    S(S&&) = delete;
};

S s2 = {2,3}; //OK
```

-   **Yalnızca hiçbir lambda yakalama zaman oluşturulan işlev işaretçisi dönüştürme**  

Aşağıdaki kod, Visual Studio 2015'te C2664 üretir. 

```cpp
void func(int(*)(int)) {}

int main() {

    func([=](int val) { return val; });
}
```
Hatayı düzeltmek için kaldırma `=` yakalama listeden.

-   **Dönüştürme işleçleri içeren belirsiz çağrıları**  

Aşağıdaki kod hatası C2440 şimdi oluşturur: 'tür belirtimi': 'S2' 'S1' dönüştürülemiyor:

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
Hatayı düzeltmek için açıkça dönüştürme işleci arayın:

```cpp
void f(S2 s2)
{
    //Explicitly call the conversion operator
    s2.operator S1();
    // Or
    S1((int)s2);
}

```

Aşağıdaki kod hatası C2593 şimdi oluşturur: ' işleci =' belirsiz:

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
Hatayı düzeltmek için açıkça dönüştürme işleci arayın:
```cpp
void f(S1 *p, S2 s)
{
       *p = s.operator S1&();
}
```

-   **Statik olmayan veri üye başlatma (NSDMI) geçersiz kopya başlatma Düzelt**  

Aşağıdaki kod hatası C2664 şimdi oluşturur: 'S1::S1(S1 &&)': 'bool' dönüştürülemiyor bağımsız değişkeni 1 ' const S1 &':
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

-   **Oluşturucular decltype deyimleri içinde erişme**  

Aşağıdaki kod artık C2248 üretir: 'S::S': olamaz erişim özel üye bildirilen sınıfının içinde ':
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
Hatayı düzeltmek için S: S2 için arkadaş bildirimi ekleyin
```cpp
class S {
    S();
    friend class S2; // Make S2 a friend
public:
    int i;
};
```

-   **Lambda, varsayılan ctor örtük olarak silinir**  

Aşağıdaki kod hatası C3497 şimdi oluşturur: bir lambda örneği oluşturulamaz:
```cpp
void func(){
    auto lambda = [](){};    
 
    decltype(lambda) other;
}
```
Hatayı düzeltmek için çağrılacak varsayılan oluşturucu gereksinimini kaldırın. Lambda herhangi bir şey yakalamaz varsa sonra bir işlev işaretçisi dönüştürme olabilir.

-   **Lambda'lar ile silinen atama işleci**  

Aşağıdaki kod artık hata C2280 üretir:

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
Hatayı düzeltmek için lambda functor sınıfıyla değiştirin veya atama işleci kullanmaya gerek kaldırın.

-   **Silinen kopya Oluşturucu sahip bir nesne taşınmaya çalışılırken**  

Aşağıdaki kod hatası C2280 şimdi oluşturur: 'taşınabilir:: moveable(const moveable &)': silinen işlevi başvurulmaya çalışılıyor
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
Hatayı düzeltmek için std::move kullanın:
```cpp
S(moveable && m) :
    m_m(std::move(m))
```
-   **Yerel sınıfı daha sonra aynı işlevinde tanımlı başka bir yerel sınıf başvuramaz.**  

Aşağıdaki kod hatası C2079 şimdi oluşturur: 's' kullanır yapısı 'main::S2' tanımlanmamış
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
Hatayı düzeltmek için S2 tanımı Taşı:
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

-   **Korumalı bir temel ctor türetilmiş ctor gövdesinde çağrılamaz.**  

Aşağıdaki kod hatası C2248 şimdi oluşturur: 'S1::S1': 'S1' sınıfında tanımlanan korumalı üye erişemiyor
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
Hatayı düzeltmek için S2 S1() çağrısı oluşturucusundan kaldırın ve gerekirse, başka bir işlevde yerleştirin.

-   **{} İşaretçi dönüştürme engeller**  

Aşağıdaki kod artık C2439 üreten 'S::p': üye başlatılamadı   
```cpp
struct S {
    S() : p({ 0 }) {}
    void *p;
};
```
Hatayı düzeltmek için gelen kaşlı 0 geçici kaldırın veya başka kullanmak `nullptr` bunun yerine, bu örnekte gösterildiği gibi:
```cpp
struct S {
    S() : p(nullptr) {}
    void *p;
};
```

-   **Yanlış makro tanımı ve parantez kullanımı**  

Aşağıdaki örnek şimdi hata C2008 üretir: ';': makrosu tanımında beklenmeyen
```cpp
#define A; //cause of error

struct S {
    A(); // error
};
```
Sorunu gidermek için üst çizgi değiştirin`#define A();`

Aşağıdaki kod hatası C2059 oluşturur: sözdizimi hatası: ')'
```cpp

//notice the space after 'A'
#define A () ;

struct S {
    A();
};
```
Kod Kaldır arasındaki boşluğu düzeltmek için A ve ().

Aşağıdaki kod hatası C2091 oluşturur: işlevi işlevi döndürür:

```cpp

#define DECLARE void f()

struct S {
    DECLARE();
};
```
Hatayı düzeltmek için S: DECLARE sonra parantez kaldırmak `DECLARE;`.

Aşağıdaki kod hatası C2062 oluşturur: türü 'int' beklenmeyen

```cpp
#define A (int)

struct S {
    A a;
};
```
Sorunu düzeltmek için A aşağıdaki gibi tanımlayın:
```cpp
#define A int
```

-   **Fazladan bildirimlerinde parens**  

Aşağıdaki kod hatası C2062 oluşturur: türü 'int' beklenmeyen
```cpp

struct S {
    int i;
    (int)j;
};
```
Hatayı düzeltmek için kaldırma gelen parens `j`. Varsa parens daha anlaşılır olması için gerekli olan, daha sonra bir typedef kullanır.

-   **Derleyicinin ürettiği oluşturucular ve __declspec(novtable)**  

Visual Studio 2015'te satır içi derleyici tarafından üretilen oluşturucular sanal taban sınıflar ile soyut sınıfların __declspec(dllimport) ile birlikte kullanıldığında __declspec(novtable) hatalı kullanımını getirebilir bir olasılığının yoktur.

-   **Otomatik gerektirir doğrudan listesi başlatma tek ifadesinde** aşağıdaki kod hatası C3518 şimdi oluşturur: 'testPositions': doğrudan listesi başlatma bağlamda türü için 'auto' yalnızca bir tek Başlatıcı ifadesinden anlaşılan

```cpp
auto testPositions{
    std::tuple<int, int>{13, 33},
    std::tuple<int, int>{-23, -48},
    std::tuple<int, int>{38, -12},
    std::tuple<int, int>{-21, 17}
};
```
Hatayı düzeltmek için testPositions şu şekilde başlatmak için bir olasılık olabilir:

```cpp
std::tuple<int, int> testPositions[]{
    std::tuple<int, int>{13, 33},
    std::tuple<int, int>{-23, -48},
    std::tuple<int, int>{38, -12},
    std::tuple<int, int>{-21, 17}
};
```

-   **İs_convertible türlerinde işaretçiler ve türleri denetleniyor**  

Aşağıdaki kod artık statik onaylama başarısız olmasına neden olur. 

```cpp
struct B1 {
private:
    B1(const B1 &);
};
struct B2 : public B1 {};
struct D : public B2 {};

static_assert(std::is_convertible<D, B2>::value, "fail");
```
Hatayı düzeltmek için static_assert D ve B2 işaretçileri karşılaştırır şekilde değiştirin:

```cpp
static_assert(std::is_convertible<D*, B2*>::value, "fail");
```

-   **declspec(novtable) bildirimleri tutarlı olmalıdır**  

declspec bildirimleri tüm kitaplıkları arasında tutarlı olması gerekir. Aşağıdaki kod, artık bir tanım kuralını (ODR) ihlaline neden olur:

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


  
###  <a name="VS_Update1"></a>Güncelleştirme 1 uygunluk yenilikleri  
  
-   **Özel sanal taban sınıflar ve dolaylı devralma**  
  
     Derleyici önceki sürümlerini izin üye işlevlerini çağırın türetilmiş bir sınıf kendi *dolaylı olarak türetilmiş* `private virtual` temel sınıflar. Bu eski davranış yanlış ve C++ Standart uygun değil. Derleyici artık bu şekilde yazılan kod kabul eder ve derleyici hatası C2280 sonuç olarak verir.  
  
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
  
-   **New işleci aşırı yüklenmiş ve delete işleci**  
  
     Derleyici önceki sürümlerini izin üyesi olmayan `operator new` ve üye olmayan `operator delete` statik bildirilmesi ve ad alanları genel ad alanı dışında bildirilmesi için.  Bu eski davranış oluşturulan program çağrılmayan risk `new` veya `delete` sessiz hatalı çalışma zamanı davranışını elde edilen Programcı hedeflenen işleci uygulama. Derleyici artık bu şekilde yazılan kod kabul eder ve bunun yerine derleyici hatası C2323 sorunları.  
  
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
  
     Derleyici belirli bir tanılama vermediğinin rağmen ek olarak, yeni satır içi işleci bozuk biçimli olarak kabul edilir.  
  
-   **Çağırma ' işleci *türü*() ' (kullanıcı tanımlı dönüştürme) sınıfı olmayan türler**  
  
     İzin verilen Derleyici önceki sürümlerini ' işleci *türü*() ' sınıfı olmayan türlerinde sessizce yoksayılıyor sırasında çağrılabilir. Bu eski davranış sessiz hatalı kod oluşturmasına, öngörülemeyen çalışma zamanı davranışını kaynaklanan riski oluşturulmuş. Derleyici artık bu şekilde yazılan kod kabul eder ve bunun yerine derleyici hatası C2228 sorunları.  
  
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
  
-   **Yedek typename içinde ayrıntılandırılmış tür tanımlayıcıları**  
  
     İzin verilen Derleyici önceki sürümlerini `typename` ayrıntılandırılmış tür tanımlayıcıları; bu şekilde yazılan kod anlamsal olarak geçersiz. Derleyici artık bu şekilde yazılan kod kabul eder ve bunun yerine derleyici hatası C3406 sorunları.  
  
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
  
-   **Bir başlatıcı listesinden dizi türü kesintisi**  
  
     Derleyici önceki sürümlerini bir başlatıcı listesinden dizi türü kesintisi desteklememektedir. Derleyici şimdi türü kesintisi bu biçimini destekler ve sonuç olarak, başlatıcı listeleri kullanarak işlev şablonları çağrıları şimdi belirsiz olabilir veya farklı bir aşırı daha Derleyici önceki sürümlerde seçilmesi. Bu sorunları gidermek için program şimdi açıkça Programcı hedeflenen aşırı belirtmeniz gerekir.  
  
     Bu yeni davranış eşit geçmiş aday olarak kadar iyi ek bir aday dikkate alınması gereken aşırı yükleme çözünürlüğü neden olduğunda çağrısı belirsiz haline gelir ve derleyici derleyici hatası C2668 sonuç olarak yayımlar.  
  
    ```Output  
  
    error C2668: 'function' : ambiguous call to overloaded function.  
  
    ```  
  
     Örnek 1: Aşırı yüklenmiş işlevi (önce) belirsiz çağrısı  
  
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
  
     Örnek 1: aşırı yüklenmiş işlevi (sonra) belirsiz çağrısı  
  
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
  
     Bu yeni davranış çağrı belirsizliğe yer bırakmadan yeni adayı sürümüne çözümler geçmiş adayı daha iyi bir eşleşme olan ek bir aday dikkate alınması gereken aşırı yükleme çözünürlüğü neden olduğunda program davranışı bir değişiklik neden büyük olasılıkla farklıdır Programcı amaçlar.  
  
     Örnek 2: aşırı çözünürlük (önce) değiştirme  
  
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
  
     Örnek 2: aşırı çözünürlük (sonra) değiştirme  
  
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
  
-   **Switch deyimi uyarılar geri yükleme**  
  
     Önceden varolan uyarılarla ilgili Derleyici önceki sürümü kaldırılıyor `switch` deyimleri; bunlar uyarılar şimdi geri yüklendi. Derleyici şimdi geri yüklenen uyarıları sorunları ve belirli durumlarda (varsayılan durumu dahil) ilgili uyarılar şimdi soruna neden olan durum içeren satırı yerine switch deyimi son satırının verilir. Sonuç olarak bu uyarılar farklı satırlarındaki geçmişte şimdi veren, uyarıları daha önce gizlenen kullanarak `#pragma warning(disable:####)` tasarlandığı gibi artık gizlenen. Bu uyarılar tasarlandığı gibi gizlemek için bu taşımak gerekli olabilir `#pragma warning(disable:####)` ilk olası sorunlu çalışması üstüne bir çizgi yönergesi. Geri yüklenen uyarılar verilmiştir.  
  
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
  
     (Önce) C4063 örneği  
  
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
  
     (Sonra) C4063 örneği  
  
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
  
-   **#include: üst dizini tanımlayıcısı kullanın '..' pathname içinde** (yalnızca wln /WX etkiler)  
  
     Derleyici önceki sürümlerini üst dizini belirleyici kullanımını algılamadı '..' yol adı olarak `#include` yönergeleri. Bu şekilde yazılan kod genellikle yanlış proje göreli yollar kullanılarak dışında projesi mevcut üstbilgileri dahil etmek için tasarlanmıştır. Bu eski davranış program hedeflenen Programcı farklı bir kaynak dosyasından dahil ederek derlenmiş veya bu göreli yollar diğer yapı ortamlar için taşınabilir olmayacaktır riski oluşturulur. Derleyici şimdi algılar ve bu şekilde yazılan kod Programcı bildirir ve etkinleştirilirse isteğe bağlı bir derleyici C4464, uyarı verir.  
  
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
  
     Derleyici belirli bir tanılama sağlamaz, ancak buna ek olarak, ayrıca, üst dizini belirleyici öneririz "..." Not projenizin içeren dizinleri belirtmek için kullanılmalıdır.  
  
-   **#pragma optimize() genişletir üstbilgi dosyası sonunun** (yalnızca wln /WX etkiler)  
  
     Derleyici önceki sürümlerinde bulunan bir çeviri birimi bulunan bir üstbilgi dosyası kaçış iyileştirme bayrağı ayarlarında yapılan değişiklikler algılamadı. Derleyici şimdi algılar ve bu şekilde yazılan kod Programcı bildirir ve C4426 sorunlu konumda uyarı isteğe bağlı bir derleyici sorunları `#include`, etkinleştirilirse. En iyi duruma getirme bayraklarla değişiklikleri çakışma derleyici komut satırı bağımsız değişkenleri olarak ayarlarsanız bu uyarı yalnızca görüntülenir.  
  
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
  
-   **#Pragma warning(push) eşleşmeyen** ve **#pragma warning(pop)** (yalnızca wln /WX etkiler)  
  
     Derleyici önceki sürümlerini algılamadı `#pragma warning(push)` durumu değişir ile eşleştirilmiş `#pragma warning(pop)` durum nadiren kullanılmaya farklı bir kaynak dosyasındaki değişiklikleri. Bu eski davranışı bir risk, oluşturulan program hazırlanan Programcı etkin uyarıları büyük olasılıkla sessiz hatalı çalışma zamanı davranışını elde edilen farklı bir dizi derlenecek. Derleyici şimdi algılar ve bu şekilde yazılan kod Programcı bildirir ve eşleşen konumda C5031 uyarı isteğe bağlı bir derleyici sorunları `#pragma warning(pop)`, etkinleştirilirse. Bu uyarı, karşılık gelen #pragma warning(push) konumunu başvuran Not dahildir.  
  
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
  
     Bu şekilde yazılan kod bazen seyrek olsa kasıtlıdır. Bu şekilde yazılan kod değişikliklere hassas `#include` mümkün olduğunda, kaynak kodu dosyaları kendi içinde bulunan bir biçimde uyarı durumunu yönetme öneririz; sırası.  
  
-   **Eşleşmeyen #pragma warning(push)** (yalnızca wln /WX etkiler)  
  
     Derleyici önceki sürümlerini algılamadı eşleşmeyen `#pragma warning(push)` durum değişiklikleri çeviri birim sonunda. Derleyici şimdi algılar ve bu şekilde yazılan kod Programcı bildirir ve C5032 eşleşmeyen #pragma warning(push) konumda uyarı isteğe bağlı bir derleyici etkinleştirilirse sorunları. Bu uyarı, yalnızca çeviri biriminde hiç derleme hatası olması durumunda görüntülenir.  
  
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
  
-   **Ek uyarı sonucu olarak geliştirilmiş #pragma uyarı durumu izleme verilebilecek**  
  
     Derleyici önceki sürümlerinden de sorun için yeterince uyarı tüm uyarılar yönelik durum değişiklikleri #pragma izlenir. Bu davranış, uyarıları etkin hedeflenen Programcı farklı durumlarda atlanması, belirli bir risk oluşturulur. Derleyici şimdi #pragma uyarısı durumunu daha yerine--#pragma uyarısı durum değişiklikleri şablonları içinde--özellikle ilgili izler ve isteğe bağlı olarak istenmeyenkullanımlarınıbulunProgramcıyardımcıolmaküzeretasarlanmıştıryeniuyarılarC5031veC5032sorunları`#pragma warning(push)` ve `#pragma warning(pop)`.  
  
     Sonucu olarak geliştirilmiş #pragma durumu değişiklik izleme, eskiden yanlış gizlenen uyarılar veya önceden misdiagnosed sorunlarıyla ilgili uyarılar uyarı artık verilebilir.  
  
-   **Geliştirilmiş kimlik ulaşılamaz kod**  
  
     C++ Standart Kitaplığı değişiklikleri ve satır içi işlev çağrılarını Derleyici önceki sürümlerini üzerinden geliştirilmiş yeteneği belirli kod ulaşılamaz olduğunu kanıtlamak derleyici izin verebilir. Bu yeni davranış yeni ve daha sık uyarı C4720 örneklerini verilen sonuçlanabilir.  
  
    ```Output  
    warning C4720: unreachable code  
    ```  
  
     Çoğu durumda, bu uyarı, yalnızca iyileştirmeler etkinleştirilerek derlerken verilebilecek, bu yana iyileştirmeler satır içi daha işlev çağrıları, yedekli kod ortadan kaldırmak veya aksi halde belirli kod erişilemiyor belirlemek mümkün kılar. Biz uyarı C4720 yeni örneklerini try/catch blokları, kullanım için özellikle ilişkisi içinde sık gerçekleşen gözlenen [std::find](assetId:///std::find?qualifyHint=False&autoUpgrade=True).  
  
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
  
###  <a name="VS_Update2"></a>Güncelleştirme 2 uygunluk yenilikleri  
  
-   **Kısmi ifade SFINAE desteği sonucunda ek uyarıları ve hataları verilebilecek**  
  
     Derleyici önceki sürümlerini ifadelerinin içinde belirli bir türde değil ayrıştırma `decltype` tanımlayıcıları ifade SFINAE desteği eksikliği nedeniyle. Bu eski davranış yanlış ve C++ Standart uygun değil. Derleyici şimdi bu deyimler ayrıştırır ve kısmi ifade SFINAE devam eden uygunluk geliştirmeleri nedeniyle desteği sahiptir. Sonuç olarak, derleyici uyarıları şimdi sorunları ve derleyici önceki sürümleri olmayan incelenemedi ifadelerinde hatalar bulundu.  
  
     Bu yeni davranış zaman ayrıştırır bir `decltype` henüz bildirilmedi, bir tür derleyici içeren deyim derleyici hatası C2039 sonuç olarak verir.  
  
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
  
     Bu yeni davranış zaman ayrıştırır bir `decltype` gerekli kullanımını eksik ifade `typename` bağımlı bir ad yazın, derleyici olduğunu belirtmek için anahtar sözcüğü derleyici C4346 derleyici hatası C2923 birlikte uyarı verir.  
  
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
  
-   `volatile`**üye değişkenleri önlemek örtük olarak tanımlanan oluşturucuları ve atama işleçleri**  
  
     Derleyici önceki sürümlerini izin olan bir sınıfı `volatile` varsayılan üye değişkenleri copy/move oluşturucular ve kopyalama/taşıma atama işleçleri otomatik olarak oluşturulan varsayılan. Bu eski davranış yanlış ve C++ Standart uygun değil. Derleyici artık otomatik olarak oluşturulan varsayılan uygulamaları bu işleçlerinin önleyen volatile üye değişkenleri Önemsiz olmayan yapım ve atama işleçleri sahip olan bir sınıfı göz önünde bulundurur.  Böyle bir sınıfın UNION (veya bir sınıf içinde anonim bir birleşimi) bir üyesi olduğunda, copy/move oluşturucuları ve kopya/taşıma atama işleçleri UNION (veya unonymous UNION içeren sınıf) örtük olarak silindi olarak tanımlanır. Oluşturmak veya bunları açıkça tanımlamadan UNION (veya anonim UNION içeren sınıf) kopyalamak çalışırken bir hata derleyici sorunları derleyici hatası C2280 sonucunda ise.  
  
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
  
-   **Statik üye işlevleri MS niteleyicileri desteklemez.**  
  
     Visual Studio 2015 önceki sürümlerini MS niteleyicileri sağlamak statik üye işlevleri izin verilir. Visual Studio 2015 ve Visual Studio 2015 güncelleştirme 1'teki bir gerileme nedeniyle bu davranışı değildir; Visual Studio 2013 ve önceki sürümlerinde derleyici, bu şekilde yazılan kod reddeder. Visual Studio 2015 ve Visual Studio 2015 güncelleştirme 1 davranışını yanlış ve standart C++ için uygun değil.  Visual Studio 2015 güncelleştirme 2 Bu şekilde yazılan kod reddeder ve bunun yerine derleyici hatası C2511 verir.  
  
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
  
-   **Enum ileriye dönük bildirimi WinRT kodu izin verilmeyen** (/ZW yalnızca etkiler)  
  
     Windows çalışma zamanı (WinRT) izin vermediği için derlenmiş kod `enum` yönetilen C++ kodu için .net derlendiğinde İleri, benzer şekilde belirtilecek türleri çerçevesi/CLR derleyici kullanılarak geçin. Bu davranış olduğu numaralandırma boyutu her zaman bilinir ve doğru şekilde WinRT türü sisteme öngörülen sağlar. Derleyici bu şekilde yazılan kod reddeder ve derleyici hatası C2599 derleyici hatası C3197 birlikte verir.  
  
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
  
-   **Aşırı yüklenmiş üye olmayan işleci yeni ve delete işleci bildirilmemiş satır içi** (düzey 1 (/ W1) üzerinde tarafından-varsayılan)  
  
     Satır içi yeni üye olmayan işleci ve işleci silme işlevleri bildirirken Derleyici önceki sürümlerini bir uyarı vermek değil. Bu şekilde yazılan kodu bozuk biçimli (tanılama gerekli) ve kaynaklanan sorunlar yeni eşleşmeyen ve tanılamak zor olabilir (özellikle boyutlu ayırmayı kaldırma ile birlikte kullanıldığında) işleçleri silmek bellek neden olabilir.   Derleyici şimdi derleyici C4595 bu şekilde yazılan kod tanımlamaya yardımcı olmak üzere Uyarı yayınlar.  
  
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
  
     Bu şekilde yazılan kod çözme işleç tanımları üstbilgi dosyası dışında ve karşılık gelen bir kaynak dosyasına taşınmasına gerektirebilir.  
  
###  <a name="VS_Update3"></a>Güncelleştirme 3 uygunluk yenilikleri  
  
-   **Std::is_convertable otomatik atanmasını artık algılar** (standart kitaplığı)  
  
     Önceki sürümlerini `std::is_convertable` türü ayırdedici nitelik kopya kurucusu silindiğinde bir sınıf türünün otomatik atanmasını veya özel doğru algılamadı. Şimdi, `std::is_convertable<>::value` doğru bir şekilde ayarlamak `false` bir sınıf türü silindiğinde veya özel kopya Oluşturucu ile uygulandığında.  
  
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
  
     Derleyici önceki sürümlerde olduğundan bu örnek altındaki statik onaylar geçirmek `std::is_convertable<>::value` yanlış ayarlandı `true`. Şimdi, `std::is_convertable<>::value` doğru şekilde ayarlandığından `false`, statik onaylar başarısız olmasına neden olur.  
  
-   **Varsayılan veya önemsiz kopya silinir ve oluşturucular saygı erişim tanımlayıcıları taşıyın**  
  
     Derleyici önceki sürümlerini değil varsayılan veya silinen Önemsiz kopyasının erişim belirticisi denetleyin ve bunları çağrılmasına izin vermeden önce oluşturucular taşıyın. Bu eski davranış yanlış ve C++ Standart uygun değil. Bazı durumlarda, bu eski davranış sessiz hatalı kod oluşturmasına, öngörülemeyen çalışma zamanı davranışını kaynaklanan riski oluşturulur. Derleyici şimdi varsayılan veya silinen Önemsiz kopyasının erişim belirticisi denetler ve onu çağrılabilir olup olmadığını ve değilse, C2248 sonucunda uyarı sorunları derleyici olmadığını belirlemek için oluşturucular taşıyın.  
  
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
  
-   **Öznitelik atanmış ATL kodu desteğini kullanımdan** (düzey 1 (/ W1) üzerinde tarafından-varsayılan)  
  
     Desteklenen Derleyici önceki sürümlerini ATL kodu öznitelikli. Öznitelik atanmış ATL desteğini kaldırmanın sonraki aşaması olarak, kod [Visual Studio 2008'de başlangıcından](https://msdn.microsoft.com/library/bb384632\(v=vs.90\).aspx), öznitelik atanmış ATL kodu kullanım dışı bırakıldı. Derleyici şimdi derleyici C4467 bu tür kullanım dışı kodu tanımlamaya yardımcı olmak üzere Uyarı yayınlar.  
  
    ```Output  
    warning C4467: Usage of ATL attributes is deprecated  
    ```  
  
     Destek derleyiciden kaldırılana kadar atanmış ATL kodu kullanarak devam etmek istiyorsanız, bu uyarı ileterek devre dışı bırakabilirsiniz `/Wv:18` veya `/wd:4467` komut satırı bağımsız değişkenleri derleyici ya da ekleyerek `#pragma warning(disable:4467)` kaynak kodunuzdaki.  
  
     Örnek 1 (önce)  
  
    ```cpp  
              [uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]  
    class A {};  
  
    ```  
  
     Örnek 1 (sonra)  
  
    ```cpp  
    __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) A {};  
  
    ```  
  
     Bazen, veya ihtiyacınız olabilir bir IDL oluşturmak istediğiniz dosya kullanmaktan kaçının ATL öznitelikler, aşağıdaki örnek kod olduğu gibi kullanım dışı  
  
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
  
     Önce *.idl dosyası oluşturun; oluşturulan vc140.idl dosyası elde etmek için kullanılabilir bir \*arabirimleri ve ek açıklamaları içeren .idl dosyası.  
  
     Ardından, bir MIDL adımı C++ Arabirim tanımları oluşturulan emin olmak için derleme ekleyin.  
  
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
  
     Ardından, aşağıdaki örnek kod olduğu gibi uygulama dosyasındaki doğrudan ATL kullanın.  
  
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
  
-   **Önceden Derlenmiş Üstbilgi (PCH) dosyaları ve uyumsuzluğu # yönergeleri include** (yalnızca wln /WX etkiler)  
  
     Derleyici önceki sürümlerini kabul eşleşmeyen `#include` arasındaki kaynak dosyalarında yönergeleri `-Yc` ve `-Yu` kullanırken derlemeleri önceden derlenmiş üstbilgi (PCH) dosyaları. Bu şekilde yazılan kod artık derleyici tarafından kabul edilir.   Tanımlamaya yardımcı olmak üzere CC4598 uyarı sorunları derleyici eşleşmeyen artık derleyici `#include` PCH dosyalarını kullanırken yönergeleri.  
  
    ```Output  
  
    warning C4598: 'b.h': included header file specified for Ycc.h at position 2 does not match Yuc.h at that position  
  
    ```  
  
     (Önce) örnek:  
  
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
  
-   **Önceden Derlenmiş Üstbilgi (PCH) dosyaları ve uyumsuzluğu içeren dizinler** (yalnızca wln /WX etkiler)  
  
     Kabul Derleyici önceki sürümlerini eşleşmeyen içeren dizin (`-I`) arasındaki derleyici komut satırı bağımsız değişkenleri `-Yc` ve `-Yu` kullanırken derlemeleri önceden derlenmiş üstbilgi (PCH) dosyaları. Bu şekilde yazılan kod artık derleyici tarafından kabul edilir.   Tanımlamaya yardımcı olmak üzere CC4599 uyarı sorunları derleyici eşleşmeyen artık derleyici içeren dizin (`-I`) PCH dosyalarını kullanırken komut satırı bağımsız değişkenleri.  
  
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
  
## <a name="visual-studio-2013-conformance-changes"></a>Visual Studio 2013 uygunluk değişiklikleri  
  
### <a name="compiler"></a>Derleyici  
  
-   Son anahtar sözcüğü şimdi burada önceden derlenmiş bir çözümlenmemiş simgesi hata oluşturur:  
  
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
  
     Önceki sürümlerde, çağrı sanal bir çağrı olduğundan hata verilmiyordu; ancak program çalışma zamanında çöküyordu. Artık, sınıfın son olduğu bilindiğinden bir bağlayıcı hatası verilmektedir. Bu örnekte, hatayı düzeltmek için S2::f tanımını içeren obj karşı bağlantı.  
  
-   Arkadaş işlevleri ad alanları ile kullandığınızda, arkadaş işlevi için bakın veya derleyici şimdi ISO C++ Standart için uygun olduğundan bir hata iletisiyle karşılaşırsınız önce yeniden bildirmeniz gerekir. Örneğin, bu artık derlenmemektedir:  
  
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
  
     Bu kodu düzeltmek için arkadaş işlevini bildirin:  
  
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
  
-   C++ standart bir sınıfta açık uzmanlık izin vermiyor. Bazı durumlarda, aşağıdaki örnekte gibi durumlarda sağlayan Microsoft Visual C++ Derleyici rağmen derleyici ilk uzmanlaşması olmasını ikinci işlevi kabul etmediği için bir hata şimdi oluşturulur.  
  
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
  
-   Derleyici aşağıdaki örnekte iki işlevleri belirsizliğini ortadan kaldırmak artık çalışır ve şimdi bir hata gösterir:  
  
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
  
-   Derleyici ISO C ++ 11 ile uyumlu yapılmadan önce aşağıdaki kod derlenmiş ve neden x tür int çözümlemek için:  
  
    ```cpp  
    auto x = {0};  
    int y = x;  
  
    ```  
  
     Artık bu kodu çözümler std::initializer_list türü x\<int > ve atamayı dener sonraki satırda bir hata neden int türü için x (Varsayılan olarak herhangi bir dönüştürme yoktur.) Bu kod düzeltmek için int otomatik değiştirmek için kullanın:  
  
    ```cpp  
    int x = {0};  
    int y = x;  
  
    ```  
  
-   Sağ taraftaki değerin türü başlatıldığını sol değerin türü eşleşmediğinde toplu başlatma artık izin verilir ve C ++ 11 ISO standart olmadan çalışmaya tek düzen başlatma gerektirmesi nedeniyle bir hata verilir daraltma dönüşümleri. Daha önce bir daraltma varsa dönüştürme kullanılabilir bir [Derleyici Uyarısı (düzey 4) C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) uyarı yerine bir hata veren.  
  
    ```cpp  
    int i = 0;  
    char c = {i}; // error  
  
    ```  
  
     Bu kodu düzeltmek için açık bir daraltma dönüşümü ekleyin:  
  
    ```cpp  
    int i = 0;  
    char c = {static_cast<char>(i)};  
  
    ```  
  
-   Aşağıdaki başlatma artık izin verilir:  
  
    ```cpp  
    void *p = {{0}};  
  
    ```  
  
     Bu kodu düzeltmek için şu formlardan birini kullanın:  
  
    ```cpp  
    void *p = 0;  
    // or  
    void *p = {0};  
  
    ```  
  
-   Ad arama değişti. Aşağıdaki kod farklı Visual Studio 2012 ve Visual Studio 2013 C++ derleyicisi olarak çözümlendi:  
  
    ```cpp  
    enum class E1 { a };  
    enum class E2 { b };  
  
    int main()  
    {  
        typedef E2 E1;  
        E1::b;  
    }  
  
    ```  
  
     Visual Studio 2012'de E1::b ifadesinde E1 çözümlendi:: genel kapsamda E1. Visual Studio 2013, E1::b ifadesinde E1 main() E2 tanımında typedef çözümler ve türüne sahip:: E2.  
  
-   Nesne düzenini değişti. x64 üzerinde, bir sınıfın nesne düzeni önceki sürümlere göre değişebilmektedir. Bir sanal işlevi varsa, ancak sanal işleve sahip bir taban sınıfı yoksa, derleyicinin nesne modeli veri üyesi düzeninden sonra sanal işlev tablosuna bir işaretçi ekler. Başka bir deyişle, ilgili düzen her durumda en uygun düzen olmayabilir. Önceki sürümlerde bir iyileştirme x64 için Düzen artırmak yüklemeye, ancak karmaşık kodlar durumlarda düzgün çalışması başarısız olduğundan, Visual Studio 2013'te kaldırıldı. Örneğin, aşağıdaki kodu düşünün:  
  
    ```cpp  
    __declspec(align(16)) struct S1 {  
    };  
  
    struct S2 {  
        virtual ~S2();  
        void *p;  
        S1 s;  
    };  
  
    ```  
  
-   Visual Studio 2013'te x64 üzerinde sizeof(S2) 48 sonucudur, ancak isteğe bağlı olarak önceki sürümlerde, 32 olarak değerlendirir. Bu C++ derleyicisi x64 için Visual Studio 2013'te 32 değerlendirme yapmak için bir sanal işleve sahip kukla bir temel sınıf ekleyin:  
  
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
  
     Önceki bir sürüm en iyi duruma getirme denediyseniz, kodunuzda yerler bulmak için bir derleyici /W3 derleyici seçeneği ile birlikte bu sürümdeki kullanır ve uyarı 4370 üzerinde. Örneğin:  
  
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
  
     Visual Studio 2013 önce bu ileti bu kodu çıkarır: "C4370 Uyarı: 'S2': sınıf yerleşimini daha iyi paketleme nedeniyle Derleyici önceki bir sürümünden değişti".  
  
     X86 derleyici derleyici tüm sürümlerinde aynı iyinin düzeni sorunu var. Örneğin, bu kod x86 için derlenirse:  
  
    ```cpp  
    struct S {  
        virtual ~S();  
        int i;  
        double d;  
    };  
  
    ```  
  
     Sizeof (S) 24 sonucudur. Bununla birlikte, az önce x64 için sözü edilen geçici çözümü kullanırsanız bu sonuç 16'ya indirilebilir:  
  
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
 C++ derleyicisi Visual Studio 2013'te, Visual Studio 2010'da uygulanmıştır, _ITERATOR_DEBUG_LEVEL uyuşmazlıkları ve RuntimeLibrary uyuşmazlıkları algılar. (Statik sürüm) / MT derleyici seçenekleri bu oluşur, /MTd (statik hata ayıklama), /MD (dinamik sürüm) ve /MDd (dinamik hata ayıklama) karma.  
  
-   Önceki sürümünden bu kişinin benzetimli diğer şablonları kodunuzu bildirir, bunu değiştirmeniz gerekir. Örneğin, allocator_traits yerine\<A >:: rebind_alloc\<U >:: diğer allocator_traits söyleyin zorunda artık\<A >:: rebind_alloc\<U >. Ancak ratio_add\<R1, R2 >:: türü artık gerekli ve şimdi ratio_add söyleyin öneririz\<R1, R2 >, önceki hala çünkü derlenir oranı\<N, D > bir azaltılmış için "type" typedef olması gerekir aynı türde zaten azaltıldığında olacağı oranı.  
  
-   Kullanmalısınız #include \<algoritması > std::min() veya std::max() çağırdığınızda.  
  
-   Önceki sürüm benzetimli, varolan kod kullanılan numaralandırmaları kapsamlı varsa — geleneksel dizininden kapsam dışı ad alanları Sarmalanan numaralandırmaları — bunu değiştirmeniz gerekir. Tür std::future_status::future_status başvurulan Örneğin, şimdi std::future_status söylemek varsa. Bununla birlikte, çoğu kod etkilenmez — Örneğin, std::future_status::ready hala derler.  
  
-   Explicit işleci bool() işleci unspecified-bool-type() katı. Explicit işleci bool() bool için açık dönüşümler verir — Örneğin, shared_ptr verilen\<X > sp, her iki static_cast\<bool > (sp) ve bool b(sp) geçerli — ve Boolean-sınanabilir "bağlamsal dönüştürme" bool — Örneğin, varsa (sp)! sp, sp & & ne olursa olsun. Ancak, açık işleci bool() örtük dönüşümler engelliyor bool b söyleyin edilemez şekilde sp; bool için = ve bool dönüş türü verildiğinde, dönüş sp söyleyin olamaz.  
  
-   Gerçek variadic şablonları uygulanır, _VARIADIC_MAX ve ilgili makroları hiçbir etkisi yoktur. Halen _VARIADIC_MAX öğesini tanımlıyorsanız, sadece yok sayılır. Benzetilmiş değişen sayıda bağımsız değişken içeren şablonları farklı bir şekilde desteklemeye yönelik makro makinemizi kabul ettiyseniz, kodunuzu değiştirmeniz gerekir.  
  
-   Sıradan anahtar yanı sıra, C++ Standart Kitaplığı üstbilgilerini şimdi bağlama duyarlı anahtar sözcükler "geçersiz kılma" ve "son" makrosu izing yasaklamaz.  
  
-   reference_wrapper/ref()/cref() şimdi geçici nesnelere bağlama yasaklamaz.  
  
-   \<rastgele > şimdi, derleme zamanı önkoşulları kesinlikle zorlar.  
  
-   Çeşitli C++ Standart Kitaplığı tür özellikleri, "T tam türü tutulamaz" önkoşulu vardır. Derleyici artık bunu daha katı şekilde zorladığı halde, her durumda zorla kabul ettiremeyebilir. (C++ Standart Kitaplığı önkoşulu ihlalleri tanımsız davranış tetiklemek için standart zorlama garanti etmez.)  
  
-   C++ Standart Kitaplığı /clr:oldSyntax desteklemez.  
  
-   C ++ 11 belirtimi için common_type <> vardı beklenmeyen ve istenmeyen sonuçlara; Özellikle, common_type yapar\<int, int >:: tür dönüş int & &. Bu nedenle, önerilen common_type kılan sorun için çözüm kitaplık çalışma grubu 2141, derleyici uygulayan\<int, int = "" >:: dönüş tamsayı yazın  
  
     Yan-etkisi bu değişiklik, artık kimlik durumda çalışır (common_type\<T > her zaman T türü sonuçlanmaz). Bu Önerilen Çözünürlük ile uyumludur, ancak önceki çalışma biçimine dayalı kodları keser.  
  
     Bir kimlik türü ayırdedici nitelik gerekiyorsa için çalışmayacağından, < type_traits > içinde tanımlanan standart std::identity kullanmayan \<void >. Bunun yerine, gereksinimlerinize uyan kendi kimlik türü ayırt edici niteliğini uygulayın. Örnek buradadır:  
  
    ```cpp  
    template < typename T> struct Identity {  
        typedef T type;  
    };  
  
    ```  
  
### <a name="mfc-and-atl"></a>MFC ve ATL  
  
-  **Yalnızca Visual Studio 2013**: MFC MBCS kitaplığı eklenmedi Visual Studio'da Unicode olduğundan bu nedenle popüler ve MBCS kullanımını önemli ölçüde azaltılır. Yeni denetimlerin ve iletilerin çoğu salt Unicode olduğundan, bu değişiklik aynı zamanda MFC'yi Windows SDK ile daha paralel halde tutar. MFC MBCS kitaplığı kullanmaya devam etmeniz gerekir, ancak bu MSDN İndirme Merkezi'nden indirebilirsiniz [çok baytlı MFC Kitaplığı Visual Studio 2013 için](https://www.microsoft.com/en-us/download/details.aspx?id=40770). Visual C++ Yeniden Dağıtılabilir Paketi'nde bu kitaplık halen yer almaktadır.  (Not: MBCS DLL C++ Kurulum bileşenlerinde Visual Studio 2015 ve sonraki sürümlerinde bulunur).
  
-   MFC Şerit için erişilebilirlik değiştirilir.  Bir düzey mimari yerine, şimdi hiyerarşik bir mimarisi yoktur. Eski davranış arama CRibbonBar::EnableSingleLevelAccessibilityMode() tarafından kullanmaya devam edebilirsiniz.  
  
-   CDatabase::GetConnect yöntemi kaldırılır. Güvenlik artırmak için bağlantı dizesi artık depolanan şifrelenmiş ve gerektiğinde; yalnızca şifresi düz metin olarak döndürülemiyor.  Dize CDatabase::Dump yöntemi kullanılarak elde edilebilir.  
  
-   CWnd::OnPowerBroadcast imzası değiştirilir. Bu ileti işleyicisinin imzası ikinci parametre olarak bir LPARAM alacak şekilde değiştirilir.  
  
-   İmzaları ileti işleyicileri uyacak şekilde değiştirilir. Aşağıdaki işlevlerin parametre listeleri yeni eklenen ON_WM_* ileti işleyicilerini kullanacak şekilde değiştirilmiştir:  
  
    -   CWnd::OnDisplayChange yeni ON_WM_DISPLAYCHANGE makrosu ileti eşlemesinde kullanılabilir şekilde (UINT, int, int) (WPARAM yerine LPARAM) değiştirilmiştir.  
  
    -   CFrameWnd::OnDDEInitiate yeni ON_WM_DDE_INITIATE makrosu ileti eşlemesinde kullanılabilir şekilde (CWnd *, UINT, birim için) (WPARAM yerine LPARAM) değiştirilmiştir.  
  
    -   CFrameWnd::OnDDEExecute yeni ON_WM_DDE_EXECUTE makrosu ileti eşlemesinde kullanılabilir şekilde (CWnd * için tanıtıcı) (WPARAM yerine LPARAM) değiştirilmiştir.  
  
    -   CFrameWnd::OnDDETerminate yeni ON_WM_DDE_TERMINATE makrosu ileti eşlemesinde kullanılabilir şekilde (CWnd *) için (WPARAM, LPARAM) yerine parametre olarak değiştirilmiştir.  
  
    -   CMFCMaskedEdit::OnCut yeni ON_WM_CUT makrosu ileti eşlemesinde kullanılabilir şekilde (WPARAM, LPARAM) yerine herhangi bir parametre için değiştirilmiştir.  
  
    -   CMFCMaskedEdit::OnClear yeni ON_WM_CLEAR makrosu ileti eşlemesinde kullanılabilir şekilde (WPARAM, LPARAM) yerine herhangi bir parametre için değiştirilmiştir.  
  
    -   CMFCMaskedEdit::OnPaste yeni ON_WM_PASTE makrosu ileti eşlemesinde kullanılabilir şekilde (WPARAM, LPARAM) yerine herhangi bir parametre için değiştirilmiştir.  
  
-   \#MFC üstbilgi dosyalarında ifdefs kaldırılır. MFC üstbilgisinde çok sayıda #ifdefs ilgili desteklenmeyen Windows sürümleri dosyaları (WINVER &lt; 0x0501'i) kaldırılır.  
  
-   ATL DLL (atl120.dll) kaldırılır. ATL artık, üst bilgiler ve statik kitaplık (atls.lib) olarak sağlanmaktadır.  
  
-   Atlsd.lib, atlsn.lib ve atlsnd.lib kaldırılır. Atls.lib artık, karakter kümesi bağımlılıkları veya hata ayıklamaya/yayınlamaya özgü kod içermez. Unicode/ANSI ve hata ayıklama/yayınlama için aynı çalıştığından, kitaplığın yalnızca tek bir sürümü gereklidir.  
  
-   ATL/MFC izleme aracı ile birlikte ATL DLL kaldırılır ve izleme mekanizması basitleştirilmiştir. CTraceCategory Oluşturucusu artık bir parametre (kategori adı) alır ve raporlama işlevleri CRT hata ayıklama izleme makroları çağırın.  
  
## <a name="visual-c-2012-breaking-changes"></a>Visual C++ 2012 önemli değişiklikler  
  
### <a name="compiler"></a>Derleyici  
  
-   /Yl derleyici seçeneği değiştirildi. Varsayılan olarak, bu seçenek, belirli koşullar altında LNK2011 hatalara yol açabilir derleyici kullanır. Daha fazla bilgi için bkz: [/Yl (eklenmeye PCH başvurusu hata ayıklama kitaplığı için)](../build/reference/yl-inject-pch-reference-for-debug-library.md).  
  
-   / CLR kullanarak derlenmiş kodda enum class anahtar sözcüğü bir C ++ 11 enum, olmayan bir ortak dil çalışma zamanı (CLR) sabit listesi tanımlar. CLR enum tanımlamak için kendi erişilebilirlik hakkında açık olması gerekir.  
  
-   Template anahtar sözcüğü açıkça bağımlı adları (C++ dili standart uyumluluk) belirsizliğini ortadan kaldırmak için kullanın. Aşağıdaki örnekte vurgulanmış template anahtar sözcüğü karışıklığı çözmek için zorunludur. Daha fazla bilgi için bkz: [bağımlı türleri ad çözme](../cpp/name-resolution-for-dependent-types.md).  
  
    ```cpp  
    template < typename X = "", typename = "" AY = "">  
    struct Container { typedef typename AY::template Rebind< X> ::Other AX; };  
  
    ```  
  
-   Float türünde sabit ifadesine artık aşağıdaki örnekte gösterildiği gibi bir şablon bağımsız değişken olarak izin verilir.  
  
    ```cpp  
    template<float n=3.14>  
    struct B {};  // error C2993: 'float': illegal type for non-type template parameter 'n'  
  
    ```  
  
-   /GS komut satırı seçeneğini kullanarak derlenir ve devre dışı tek güvenlik açığı olan kodu çalışma zamanında sonlandırma işlemek için aşağıdaki yarı kodu örnekte gösterildiği gibi neden olabilir.  
  
    ```cpp  
    char buf[MAX]; int cch; ManipulateString(buf, &cch); // ... buf[cch] = '\0'; // if cch >= MAX, process will terminate  
    ```  
  
-   Derlemeleri için SSE2 değiştirildiğinde x86 varsayılan mimarisi; Bu nedenle, derleyici SSE yönergeleri yayabilir ve XMM kayıtları kayan nokta hesaplamalar için kullanır. Önceki davranışa geri dönmek istiyorsanız, /arch:IA32 derleyici bayrağı mimarisi IA32 belirtmek için kullanın.  
  
-   Derleyici uyarıları verebileceği [Derleyici Uyarısı (düzey 4) C4703](../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md) ve C4701 burada daha önce onu belirtmiyor. Derleyici daha güçlü denetimleri işaretçi türü başlatılmayan yerel değişkenlerde kullanımı için geçerlidir.  
  
-   / Highentropyva belirtilirse, yeni bağlayıcı bayrağı Windows 8 genellikle bir 64-bit adresine geri dönmek bellek ayırma sebep olduğunda.                 (Önce Windows 8, bu tür ayırmaları daha sık 2 GB'den az olan adresleri döndürdü.)  Bu işaretçi kesilmesi hatalar var olan kodda getirebilir. Varsayılan olarak, bu anahtarı açıktır.  Bu davranışı devre dışı bırakmak için /HIGHENTROPYVA:NO belirtin.  
  
-   Yönetilen derleyici (Visual Basic / C#) / highentropyva Yönetilen derlemeler için de destekler.  Ancak, bu durumda, /HIGHENTROPYVAswitch varsayılan olarak kapalıdır.  
  
### <a name="ide"></a>IDE  
  
-   Windows Forms uygulamaları C + oluşturmamanızı öneririz, ancak +/ CLI, bakım varolan C + +/ CLI UI uygulamalar desteklenir. Bir Windows Forms uygulaması veya başka bir .NET kullanıcı arabirimini uygulaması oluşturmak varsa, C# veya Visual Basic kullanın. Kullanın: C + +/ CLI birlikte çalışabilirlik için yalnızca amacıyla.  
  
### <a name="parallel-patterns-library-and-concurrency-runtime-library"></a>Paralel Desen kitaplığı ve Eşzamanlılık Çalışma Zamanı Kitaplığı  
 UmsThreadDefault SchedulerType numaralandırması kullanım dışıdır. UmsThreadDefault belirtimi kullanım dışı bir uyarı üretir ve dahili olarak geri ThreadScheduler eşler.  
  
### <a name="standard-library"></a>Standart Kitaplık  
  
-   C ++ 98/03 ve C ++ 11 standartları arasında önemli bir değişiklik, çağrılacak make_pair () bağımsız açık şablon kullanarak — inmake_pair olarak\<int, int >(x, y) — Visual Studio 2012'de Visual C++'ta genellikle derlenmiyor. Çözüm her zaman açık şablon bağımsız değişkenler olmadan make_pair () çağırmaktır — make_pair (x, y) olduğu gibi. Açık şablon bağımsız değişken hedefini uğratır işlevin amacı sağlama. Elde edilen türü kesin denetime ihtiyacınız varsa çifti yerine make_pair kullanın — çifti olduğu gibi\<kısa, kısa >(int1, int2).  
  
-   C ++ 98/03 ve C ++ 11 standartları arasında başka bir önemli değişiklik: A örtük olarak dönüştürülebilir olduğunda B ve B, C örtük olarak dönüştürülebilir ancak A C, C ++ 98/03 ve çifti izin Visual C++ 2010 örtük olarak dönüştürülebilir değil\<X > alanına dönüştürülmelidir () örtük veya açık olarak) çiftine\<C, X >. (Bir tür, X, burada ilgilendiren ve bu çiftindeki ilk türüne özgü değildir değil.) C ++ 11 ve C++ derleyicisi Visual Studio 2012'de bir C örtük olarak dönüştürülebilir olmadığını algılamak için bunlar aşırı çözümlemesi çiftinin dönüştürme kaldırın. Bu, birçok senaryoları için pozitif bir değişikliktir. Örneğin, işlev aşırı yüklemesi (const çifti\<int, int > &) ve func (const çifti\<dize, dize > &) ve func() çifti ile çağırma\<const char *, const char \*> bu değişiklikle derlenir. Ancak, bu değişikliği agresif çiftinin dönüştürme üzerinde dayanıyordu kod keser. Kodun bir parçası dönüştürme açıkça gerçekleştirerek genellikle düzeltilebilir — Örneğin, geçirme make_pair tarafından (static_cast\<B > (a), x) çifti bekleyen bir işleve\<C, X >.  
  
-   Visual C++ 2010 benzetimli variadic şablonları — Örneğin, make_shared\<T > (arg1, arg2, argN) — aşırı ve özelleştirmeleri çıkış ile önişlemci makineler damgası tarafından 10 değişkenlerin sınırına kadar. Visual Studio 2012'de, derleme sürelerini ve kullanıcıların çoğu için derleyici bellek tüketimini artırmak için 5 bağımsız değişkenler için bu sınır azaltılır. Ancak, önceki sınırı olarak 10, proje çapındaki açıkça _VARIADIC_MAX tanımlayarak ayarlayabilirsiniz.  
  
-   C ++ 11 17.6.4.3.1 [macro.names]/2 yasaklıyor makrosu izing anahtar sözcükleri C++ Standart Kitaplığı üstbilgilerini dahil olduğunda. Makro ized anahtar sözcükleri tespit ederse üstbilgileri derleyici hataları şimdi yayma. (_ALLOW_KEYWORD_MACROS tanımlama derlemek bu kodu sağlar, ancak biz kesinlikle konusu kullanımı önerilmemektedir.) Üstbilgileri kapsamlı kendilerini #pragma push_macro("new") / #undef yeni / #pragma pop_macro("new") kullanarak korumak için bir özel durum varsayılan olarak, ized yeni makrosu izin verilir. _ENFORCE_BAN_OF_MACRO_NEW tanımlama tam olarak bu ne adından da anlaşılacağı yapar.  
  
-   Çeşitli iyileştirmeler ve hata ayıklama denetimler uygulamak için C++ standart kitaplık uygulaması özellikle Visual Studio sürümleri arasında ikili uyumluluğu keser (2005, 2008, 2010, 2012). C++ Standart Kitaplığı kullanıldığında, bu nesne dosyaları ve bir ikili olarak (EXE ya da DLL) farklı sürümlerini kullanarak derlenir ve C++ Standart Kitaplığı nesneleri geçirme tarafından derlenmiş ikili dosyalar arasında engelliyor statik kitaplıklarından karıştırma engelliyor farklı sürümlerini kullanan. Nesne dosyaları ve statik kitaplıklarından karıştırma (Visual C++ 2010 C++ kullanarak derlendi o kullanılarak derlendi C++ Standart Kitaplığı kullanarak Visual Studio 2012'de derleyicisi bağlayıcı hataları _MSC_VER olduğu _MSC_VER uyuşmazlığı hakkında yayar Derleyicinin ana sürüm (Visual Studio 2012'de Visual C++ için 1700) içeren makrosu. Bu onay DLL karıştırma algılayamaz ve Visual C++ 2008 veya önceki bir sürümü içeren karıştırma algılayamıyor.  
  
-   C++ derleyicisi Visual Studio 2012'de, _ITERATOR_DEBUG_LEVEL uyuşmazlıkları, Visual C++ 2010'da uygulanan algılama ek olarak, çalışma zamanı kitaplığı uyuşmazlıkları algılar. (Statik sürüm) / MT derleyici seçenekleri bu oluşur, /MTd (statik hata ayıklama), /MD (dinamik sürüm) ve /MDd (dinamik hata ayıklama) karma.  
  
-   İşleç\<(), işleç > (), işleç\<() ve işleç = > () = kendi uygulamalarını gerçekten yararlı değildir ancak daha önce kapsayıcıları, std::unordered_map andstdext::hash_map aileleri için kullanılabilen. Bu standart işleçler, Visual Studio 2012'de Visual C++'de kaldırılmıştır. Ayrıca, operator==() ve operator!=() thestd::unordered_map ailesi için uyarlamasını stdext::hash_map ailesi kapsayacak şekilde genişletilmiştir. (Yeni kod thestdext::hash_map ailesinde kullanmaktan kaçının öneririz.)  
  
-   C ++ 11 22.4.1.4 [locale.codecvt] belirtir codecvt::length() ve codecvt::do_length() değiştirilebilir stateT & parametre almalıdır, ancak Visual C++ 2010 sürdü const stateT &. C++ derleyicisi Visual Studio 2012 alır stateT & standart tarafından zorunlu olarak. Bu fark sanal işlev do_length() geçersiz kılmak için çalışıyor herkes için önemlidir.  
  
### <a name="crt"></a>CRT  
  
-   Yeni kullanılan C çalışma zamanı (CRT) öbek ve malloc(), özel artık. CRT şimdi işlem yığın kullanır. Bunun anlamı DLL kaldırıldığında yığın yok edilmez, statik olarak bağlamak için CRT DLL'leri tarafından ayrılan bellek emin olmalısınız şekilde bunu kaldırıldı önce DLL kodu temizlenir.  
  
-   İscsymf() işlevi negatif değerleri ile onaylar.  
  
-   Threadlocaleinfostruct yapısı yerel işlevler değişiklikleri uyum sağlayacak şekilde değiştirdi.  
  
-   CRT işlevleri iç bilgileri memxxx() gibi karşılık gelen sahip, strxxx() intrin.h kaldırılır. Yalnızca bu işlevler için intrin.h dahil edilmişse, karşılık gelen CRT üstbilgileri şimdi eklemeniz gerekir.  
  
### <a name="mfc-and-atl"></a>MFC ve ATL  
  
-   Fusion desteği (afxcomctl32.h); kaldırıldı Bu nedenle, afxcomctl32.h içinde tanımlanan tüm yöntemleri kaldırılmıştır. Üstbilgi dosyaları afxcomctl32.h ve afxcomctl32.inl silindi.  
  
-   CDockablePane::RemoveFromDefaultPaneDividier adı için CDockablePane::RemoveFromDefaultPaneDivider değiştirildi.  
  
-   CFileDialog::SetDefExt LPCTSTR kullanılacak imzasını değiştirildi; Bu nedenle, Unicode derlemeleri etkilenir.  
  
-   Artık kullanılmayan ATL İzleme kategorileri kaldırıldı.  
  
-   Const CRect yapılacak CBasePane::MoveWindow imza değiştirildi.  
  
-   CMFCEditBrowseCtrl::EnableBrowseButton imza değiştirildi.  
  
-   Kaldırılan m_fntTabs ve CMFCBaseTabCtrl gelen m_fntTabsBold.  
  
-   Bir parametre CMFCRibbonStatusBarPane oluşturucular eklendi. (Varsayılan bir parametre olan ve bu nedenle kaynakta önemli değildir.)  
  
-   Bir parametre CMFCRibbonCommandsListBox oluşturucuya eklendi. (Varsayılan bir parametre olan ve bu nedenle kaynakta önemli değildir.)  
  
-   AFXTrackMouse API kaldırıldı (ve ilişkili Zamanlayıcı proc). Win32 TrackMouseEvent API kullanın.  
  
-   Bir parametre CFolderPickerDialog oluşturucuya eklendi. (Varsayılan bir parametre olan ve bu nedenle kaynakta önemli değildir.)  
  
-   CFileStatus yapısı boyutu değişti: m_attribute üyesi (fromGetFileAttributes döndürdü değerle eşleşecek şekilde) DWORD için bayt değiştirildi.  
  
-   CRichEditCtrl ve CRichEditView MSFTEDIT_CLASS (RichEdit 4.1 denetimi) RICHEDIT_CLASS (RichEdit 3.0 denetimi) yerine Unicode derlemelerde kullanın.  
  
-   Her zaman Windows Vista, Windows 7 ve Windows 8 TRUE olduğundan AFX_GLOBAL_DATA::IsWindowsThemingDrawParentBackground kaldırıldı.  
  
-   Her zaman Windows Vista, Windows 7 ve Windows 8 TRUE olduğundan AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable kaldırıldı.  
  
-   Kaldırılan AFX_GLOBAL_DATA::DwmExtendFrameIntoClientArea. Windows API doğrudan Windows Vista, Windows 7 ve Windows 8 çağırın.  
  
-   Kaldırılan AFX_GLOBAL_DATA::DwmDefWindowProc. Windows API doğrudan Windows Vista, Windows 7 ve Windows 8 çağırın.  
  
-   AFX_GLOBAL_DATA::DwmIsCompositionEnabled ad çakışması ortadan kaldırmak için Isdwmcompositionenabled için yeniden adlandırıldı.  
  
-   MFC iç zamanlayıcılar sayısı için tanımlayıcıları değişti ve tanımları için afxres.h (AFX_TIMER_ID_ *) taşınır.  
  
-   ON_WM_EXITSIZEMOVE makrosu ile uyuşacak şekilde OnExitSizeMove yöntemi imzası değiştirilmiştir:  
  
    -   CFrameWndEx  
  
    -   CMDIFrameWndEx  
  
    -   CPaneFrameWnd  
  
-   Ad ve ON_WM_DWMCOMPOSITIONCHANGED makrosu ile uyuşacak şekilde OnDWMCompositionChanged imzasını değişti:  
  
    -   CFrameWndEx  
  
    -   CMDIFrameWndEx  
  
    -   CPaneFrameWnd  
  
-   ON_WM_MOUSELEAVE makrosu ile uyuşacak şekilde OnMouseLeave yöntemi imzası değiştirilmiştir:  
  
    -   CMFCCaptionBar  
  
    -   CMFCColorBar  
  
    -   CMFCHeaderCtrl  
  
    -   CMFCProperySheetListBox  
  
    -   CMFCRibbonBar  
  
    -   CMFCRibbonPanelMenuBar  
  
    -   CMFCRibbonRichEditCtrl  
  
    -   CMFCSpinButtonCtrl  
  
    -   CMFCToolBar ReplaceThisText  
  
    -   CMFCToolBarComboBoxEdit  
  
    -   CMFCToolBarEditCtrl  
  
    -   CMFCAutoHideBar  
  
-   ON_WM_POWERBROADCAST makrosu ile uyuşacak şekilde OnPowerBroadcast imza değiştirilmiştir:  
  
    -   CFrameWndEx  
  
    -   CMDIFrameWndEx  
  
-   ON_WM_STYLECHANGED makrosu ile uyuşacak şekilde OnStyleChanged imza değiştirilmiştir:  
  
    -   CMFCListCtrl  
  
    -   CMFCStatusBar  
  
-   İç yöntem FontFamalyProcFonts FontFamilyProcFonts için yeniden adlandırıldı.  
  
-   Bellek sızıntıları bazı durumlarda ortadan kaldırmak için çok sayıda genel statik CString nesneleri kaldırıldı (yerine #defines), ve aşağıdaki sınıf üye değişkenleri:  
  
    -   CKeyBoardManager::m_strDelimiter  
  
    -   CMFCPropertyGridProperty::m_strFormatChar  
  
    -   CMFCPropertyGridProperty::m_strFormatShort  
  
    -   CMFCPropertyGridProperty::m_strFormatLong  
  
    -   CMFCPropertyGridProperty::m_strFormatUShort  
  
    -   CMFCPropertyGridProperty::m_strFormatULong  
  
    -   CMFCPropertyGridProperty::m_strFormatFloat  
  
    -   CMFCPropertyGridProperty::m_strFormatDouble  
  
    -   CMFCToolBarImages::m_strPngResType  
  
    -   CMFCPropertyGridProperty::m_strFormat  
  
-   CKeyboardManager::ShowAllAccelerators imza değişti ve Hızlandırıcı sınırlayıcı parametresi kaldırıldı.  
  
-   CPropertyPage::GetParentSheet eklenir ve üst olabilir ve doğru ana sayfası penceresini veya CPropertyPage iki üst penceresine almak için GetParent yerine çağrı CPropertyPage sınıfta. GetParentSheet yerine ofGetParent çağırmak için kodunu değiştirmeniz gerekebilir.  
  
-   Dengesiz #pragma warning(push) ATLBASE içinde sabit. H uyarıları hatalı devre dışı bırakılmasına neden oldu. Bu uyarılar şimdi ATLBASE sonra doğru bir şekilde etkinleştirilir. H ayrıştırılır.  
  
-   Taşınan D2D ilgili yöntemleri AFX_GLOBAL_DATA _AFX_D2D_STATE için:  
  
    -   GetDirectD2dFactory  
  
    -   GetWriteFactory  
  
    -   Getwıcfactory  
  
    -   Initd2d  
  
    -   ReleaseD2DRefs  
  
    -   Isd2dınitialized  
  
    -   D2D1MakeRotateMatrix  
  
    -   , Örneğin, afxGlobalData.IsD2DInitialized, çağırmak yerine çağrısı AfxGetD2DState -> Isd2dınitialized.  
  
-   Artık kullanılmayan ATL * kaldırıldı. \Atlmfc\include\ klasöründeki CPP dosyaları.  
  
-   İsteğe bağlı yerine afxGlobalData başlatma DLLMain gereksinimlerini karşılamak için CRT başlatma zamanında taşındı.  
  
-   RemoveButtonByIndex yöntemi CMFCOutlookBarPane sınıfı eklendi.  
  
-   CMFCCmdUsageCount::IsFreqeuntlyUsedCmd IsFrequentlyUsedCmd için düzeltildi.  
  
-   RestoreOriginalstate RestoreOriginalState (CMFCToolBar, CMFCMenuBar, CMFCOutlookBarPane) için birden çok örneği düzeltildi.  
  
-   Kullanılmayan yöntemleri CDockablePane kaldırıldı: SetCaptionStyle, IsDrawCaption, IsHideDisabledButtons, GetRecentSiblingPaneInfo, andCanAdjustLayout.  
  
-   Kaldırılan CDockablePane statik üye değişkenleri m_bCaptionText ve m_bHideDisabledButtons.  
  
-   Bir geçersiz kılma DeleteString yöntemi için CMFCFontComboBox eklendi.  
  
-   Kullanılmayan yöntemleri CPane kaldırıldı: GetMinLength ve IsLastPaneOnLastRow.  
  
-   Yeniden adlandırılmış CPane::GetDockSiteRow(CDockingPanesRow *) CPane::SetDockSiteRow için.  
  
## <a name="visual-c-2010-breaking-changes"></a>Visual C++ 2010 yeni değişiklikler  
  
### <a name="compiler"></a>Derleyici  
  
-   Auto anahtar sözcüğü yeni bir varsayılan anlamı yoktur. Eski anlamı kullanımını nadir olduğu için uygulamaların çoğu bu değişiklikten etkilenmez.  
  
-   Yeni static_assert anahtar sözcüğü sunulan, zaten varsa bir tanımlayıcı, ada göre kodunuzda, bir ad çakışması neden olur.  
  
-   IDL UUID öznitelik tırnak işareti olmayan bir GUID kodlamak için destek yeni lambda gösterimi dışlar desteği.  
  
-   .NET Framework 4 işlem kurtarılamaz bir bozuk durumda bırakır özel durumlar bozuk durumda özel durumlar kavramını sunmaktadır. Varsayılan olarak, hatta diğer tüm özel durumları yakalar /EHa derleyici seçeneği ile bozuk durumu bir özel durum catch olamaz.                 Açıkça bir bozuk durumda özel yakalamak için yapıda - kullanın\__except deyimleri. Veya bozuk durumda özel durumları yakalamak için bir işlev etkinleştirmek için [HandledProcessCorruptedStateExceptions] özniteliğini uygulayın.  Bu değişiklik öncelikle kimin bozuk durumda özel durumu yakalayın gerekebilir sistem programcıları etkiler. Sekiz istisnaları STATUS_ACCESS_VIOLATION, STATUS_STACK_OVERFLOW, EXCEPTION_ILLEGAL_INSTRUCTION, EXCEPTION_IN_PAGE_ERROR, EXCEPTION_INVALID_DISPOSITION, EXCEPTION_NONCONTINUABLE_EXCEPTION, EXCEPTION_PRIV_INSTRUCTION, STATUS_ UNWIND_CONSOLIDATE.                 Bu özel durumları hakkında daha fazla bilgi için bkz: [GetExceptionCode](https://msdn.microsoft.com/en-us/library/windows/desktop/ms679356.aspx) makrosu.  
  
-   Düzenlenen /GS derleyici seçeneği arabellek taşmaları karşı daha da fazla kapsamlı korur önceki sürümleri. Bu sürüm ek güvenlik denetimleri performansı düşebilir yığınında ekleyebilirsiniz. Güvenlik denetimleri için belirli bir işlev değil eklenecek görevlendirin için yeni __declspec(safebuffers) anahtar sözcüğü kullanın.  
  
-   /GL (bütün Program iyileştirmesi) ve/CLR (ortak dil çalışma zamanı derlemesi) derleyici seçenekleri ile derleme yaparsanız /GLoption göz ardı edilir. Derleyici Seçenekleri birleşimini az avantajı sağlamadığı bu değişiklik yapılmıştır. Bu değişiklik sonucunda, yapı performansı geliştirildi.  
  
-   Trigrafları desteği devre dışı Visual C++ 2010'da varsayılan olarak. / ZC: trigraphs derleyici seçeneği trigrafları desteğini etkinleştirmek için kullanın. Bir trigrafı oluşur iki ardışık soru işaretleri ("??") benzersiz bir üçüncü karakter. Derleyici bir trigrafı karşılık gelen bir noktalama karakteri ile değiştirir. Örneğin, derleyici değiştirir "?? = "'#' karakteriyle trigrafı. Bazı noktalama karakterleri için uygun grafik sunumlarını içermeyen bir karakter kümesi kullanan C kaynak dosyalarında trigrafları kullanın.  
  
-   Bağlayıcı, artık Windows 98 için en iyi duruma getirme destekler. OPT (iyileştirmeler) seçeneğini belirtirseniz bir derleme zamanı hatası oluşturur / OPT: WIN98 veya /OPT:NOWIN98.  
  
-   Sistem özellikleri değiştirilmiştir derleme RuntimeLibrary ve DebugInformationFormat tarafından belirtilen varsayılan derleyici seçenekleri. Varsayılan olarak, Visual C++ tarafından oluşturulan projeleri özellikleri belirtilen bu yapı 7.0 10.0 ile serbest bırakır. Visual C++ 6.0 tarafından oluşturulan proje geçirirseniz, bu özellikleri için bir değer belirtmek kullanılıp göz önünde bulundurun.  
  
-   Visual C++ 2010, RuntimeLibrary = birden çok iş parçacıklı (/ MD) ve DebugInformationFormat ProgramDatabase (/Zi) =. Visual c++ 9.0, RuntimeLibrary = birden çok iş parçacıklı (/ MT) ve DebugInformationFormat = devre dışı.  
  
### <a name="clr"></a>CLR  
  
-   Microsoft C# ve Visual Basic derleyicileri artık hiçbir birincil birlikte çalışma derlemesi (PIA Hayır) oluşturabilir. Hayır PIA derleme COM türleri ilgili birincil birlikte çalışma derlemesi (PIA) dağıtımını olmadan kullanabilirsiniz. Kitaplık kullanan tüm Hayır PIA derleme başvurusu önce Visual C# veya Visual Basic tarafından üretilen Hayır PIA derlemeleri kullanırken derleme komutunda PIA derleme başvurmalıdır.  
  
### <a name="visual-c-projects-and-msbuild"></a>Visual C++ projeleri ve MSBuild  
  
-   Visual C++ projeleri, artık MSBuild araç temel alır. Sonuç olarak, proje dosyalarını yeni bir XML dosya biçimi ve .vcxproj Dosya sonekini kullanın. Visual C++ 2010 proje dosyalarını yeni bir dosya biçimine Visual Studio'nun önceki sürümlerden dönüştürür. Varolan projeyi önceki yapı aracı, VCBUILD.exe veya proje dosyası soneki .vcproj üzerinde bağımlıysa etkilenir.  
  
-   Önceki sürümlerde, Visual C++ özellik sayfaları geç değerlendirmesi desteklenir. Örneğin, bir alt özellik sayfası bir üst özellik sayfası içeri aktarmak ve üst alt tanımlanan bir değişken diğer değişkenlerini tanımlamak için kullanabilirsiniz. Geç değerlendirme alt özellik sayfası bile içeri aktarılmış önce alt değişken kullanmak üzere üst etkin. MSBuild yalnızca erken değerlendirme desteklediğinden tanımlanmadan önce Visual C++ 2010'da, bir proje sayfası değişken kullanılamaz.  
  
### <a name="ide"></a>IDE  
  
-   Uygulama sonlandırma iletişim kutusu artık bir uygulama sona erer. Abort() veya terminate() işlevi bir uygulamanın perakende yapı kapatıldığında önceki sürümlerde, C çalışma zamanı kitaplığı uygulama sonlandırma iletisinde bir konsol penceresi veya iletişim kutusu görüntülenir. İleti denirse parçası olarak, "Bu uygulama çalışma zamanının bir biçimde sonlandırmasını istedi. Uygulamanın destek ekibinin daha fazla bilgi için temasa geçin."                 Windows, Windows hata bildirimi (Dr. genellikle geçerli sonlandırma işleyicisi, daha sonra görüntülenen uygulama sonlandırma iletisi olarak yedekli Watson) iletişim kutusu veya Visual Studio hata ayıklayıcısı. Visual Studio 2010'dan başlayarak, C çalışma zamanı kitaplığı iletiyi görüntülemez. Ayrıca, çalışma zamanı hata ayıklayıcı başlamadan önce uygulamanın bitiş engeller. Yalnızca uygulama sonlandırma iletisi önceki davranışı bağımlıysa önemli bir değişiklik budur.  
  
-   Özellikle Visual Studio 2010 için IntelliSense C + çalışmaz +/ CLI kod öznitelikleri tüm başvuruları için yerel değişkenleri çalışmıyor bulma ve kod modeli değil alınan derlemelerden tür adları alma veya türleri için kendi tam olarak qualifi çözümleyin Ed adları.  
  
### <a name="libraries"></a>Kitaplıklar  
  
-   SafeInt sınıfı Visual C++'de bulunan ve artık ayrı bir indirme. Ayrıca "SafeInt" adlı bir sınıf yalnızca geliştirdiyseniz, önemli bir değişiklik budur.  
  
-   Kitaplıkları dağıtım modeli, bildirimler artık bir dinamik bağlantı kitaplığı belirli bir sürümü bulmak için kullanır. Bunun yerine, her dinamik bağlantı kitaplığının adı, sürüm numarasını içerir ve kitaplık bulmak için bu adı kullanın.  
  
-   Visual Studio'nun önceki sürümleri çalışma zamanı kitaplıkları yeniden oluşturulamadı. Visual C++ 2010 artık zamanı kitaplık dosyalarını çalıştırmak C kendi kopyalarını oluşturma destekler.  
  
### <a name="standard-library"></a>Standart Kitaplık  
  
-   \<Yineleyici > Üstbilgi artık dahil otomatik olarak tarafından diğer birçok üstbilgi dosyaları. Önceki yapı aracı, VCBUILD.exe veya proje dosyası soneki, bağımlı olması durumunda bir var olan proje tanımlanan tek başına yineleyiciler desteği etkilenen gerekiyorsa bunun yerine, bu açıkça üstbilgisini. vcproj.interator >. ader.  
  
-   İçinde \<algoritması > Üstbilgi, checked_ * ve unchecked_\* işlevleri kaldırılır. Ve \<yineleyici >> başlık checked_iteratorclass kaldırılır ve unchecked_array_iterator sınıfı eklendi.  
  
-   CComPtr::CComPtr(int) Oluşturucusu kaldırılır. Bu oluşturucu bir CComPtr nesnesi NULL makro oluşturulması izin verilen ancak gereksiz ve nonsensical sıfır olmayan tamsayılar gelen kurulumlarını.  
  
     Bir CComPtr 0 olarak tanımlanır, ancak tamsayı dışında değişmez değer 0'dan oluşturulan bırakılırsa NULL gelen hala oluşturulabilir. nullptr kullanın.  
  
-   Aşağıdaki ctype üye işlevleri kaldırıldı: ctype::_Do_narrow_s, ctype::_Do_widen_s, ctype::_narrow_s, ctype::_widen_s. Bir uygulama bu üye işlevleri kullanıyorsa, karşılık gelen güvenli olmayan sürümü ile değiştirmeniz gerekir: ctype::do_narrow, ctype::do_widen, ctype::narrow, ctype::widen.  
  
### <a name="crt-mfc-and-atl-libraries"></a>CRT, MFC ve ATL kitaplıkları  
  
-   CRT, MFC ve ATL kitaplıklarını oluşturmak kullanıcılar için destek kaldırılmıştır. Örneğin, bir uygun nmake dosyası sağlanmadı.                 Ancak, kullanıcıların bu kitaplıklar için kaynak koduna erişim çözümlenmedi. Ve Microsoft bu kitaplıklar oluşturmak için kullandığı MSBuild seçenekleri açıklayan bir belge bir Visual C++ ekip blogu büyük olasılıkla nakledilir.  
  
-   IA64 için MFC Desteği kaldırılmıştır. Ancak, CRT ve IA64 üzerinde ATL desteği hala sağlanır.  
  
-   Sıra numaraları artık MFC modül-tanımlama (.def) dosyaları yeniden kullanılır. Bu değişiklik, sıra numaraları ikincil sürümleri arasında farklı olmaz ve hizmet paketlerini ve hızlı sürümleri mühendislik düzeltme için ikili uyumluluğu geliştirilmiş anlamına gelir.  
  
-   Yeni bir sanal işlev CDocTemplate sınıfı eklendi. Bu yeni sanal işlev [CDocTemplate sınıfı](../mfc/reference/cdoctemplate-class.md). OpenDocumentFile'nın önceki sürümünü iki parametre vardı. Yeni sürüm üç parametre yok. Yeniden başlatma Yöneticisi'ni desteklemek için CDocTemplate türetilmiş herhangi bir sınıf üç parametre sürümü uygulamalıdır. Yeni bAddToMRU parametresidir.  
  
### <a name="macros-and-environment-variables"></a>Makrolar ve ortam değişkenleri  
  
-   Ortam değişkeni __MSVCRT_HEAP_SELECT artık desteklenmiyor. Bu ortam değişkenini kaldırılır ve bir yenileme yoktur.  
  
### <a name="microsoft-macro-assembler-reference"></a>Microsoft Macro Assembler Başvurusu  
  
-   Microsoft Macro Assembler başvurusu derleyiciden birkaç yönergeleri kaldırıldı. .186, kaldırılan yönergeleri olan.286, .286P.287,.8086,.8087, ve. NO87.  
  
## <a name="visual-c-2008-breaking-changes"></a>Visual C++ 2008 önemli değişiklikler  
  
### <a name="compiler"></a>Derleyici  
  
-   Windows 95, Windows 98, Windows ME ve Windows NT platformları artık desteklenmemektedir. Bu işletim sistemlerinin Hedef platformlar listesinden kaldırıldı.  
  
-   Derleyici artık doğrudan olan birden çok öznitelik destekleyen ATL sunucusu ile ilişkili. Aşağıdaki öznitelikler artık desteklenir:  
  
    -   perf_counter  
  
    -   perf_object  
  
    -   Perfmon  
  
    -   request_handler  
  
    -   soap_handler  
  
    -   soap_header  
  
    -   soap_method  
  
    -   tag_name  
  
### <a name="visual-c-projects"></a>Visual C++ projeleri  
  
-   Projeleri, Visual Studio'nun önceki sürümlerinden yükseltme yaparken, böylece 0x0500 eşit veya daha büyük WINVER ve _WIN32_WINNT makroları değiştirmeniz gerekebilir.  
  
-   Visual Studio 2008'den itibaren Yeni Proje Sihirbazı'nı bir SQL Server C++ projesi oluşturmak için bir seçenek yok. Visual Studio'nun önceki bir sürümü kullanılarak oluşturulan SQL Server projeleri hala derleyin ve düzgün çalışır.  
  
-   Windows API üstbilgi dosyası Winable.h kaldırılmıştır. Bunun yerine Winuser.h içerir.  
  
-   Windows API kitaplığı Rpcndr.lib kaldırılmıştır. Bunun yerine Rpcrt4.lib ile bağlayın.  
  
### <a name="crt"></a>CRT  
  
-   Windows 95, Windows 98, Windows Millennium Edition ve Windows NT 4.0 Desteği kaldırılmıştır.  
  
-   Aşağıdaki genel değişkenleri kaldırıldı:  
  
    -   _osplatform  
  
    -   _osver  
  
    -   _winmajor  
  
    -   _winminor  
  
    -   _winver  
  
-   Aşağıdaki işlevleri kaldırılmıştır. Windows API işlevleri GetVersion veya GetVersionEx kullanın:  
  
    -   _get_osplatform  
  
    -   _get_osver  
  
    -   _get_winmajor  
  
    -   _get_winminor  
  
    -   _get_winver  
  
-   SAL ek açıklamaları sözdizimi değişti. Daha fazla bilgi için bkz: [SAL ek açıklamaları](../c-runtime-library/sal-annotations.md).  
  
-   IEEE filtre artık SSE 4.1 yönerge kümesi destekler. Daha fazla bilgi için bkz: [_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)_fpieee_flt.  
  
-   C çalışma zamanı kitaplıkları Visual Studio ile birlikte, artık sistem DLL'i msvcrt.dll üzerinde bağımlıdır.  
  
### <a name="standard-library"></a>Standart Kitaplık  
  
-   Windows 95, Windows 98, Windows Millennium Edition ve Windows NT 4.0 Desteği kaldırılmıştır.  
  
-   Hata ayıklama modunda tanımlanmış _HAS_ITERATOR_DEBUGGING ile derlerken (yerini [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) Visual Studio 2010 sonra), yineleyici Artır veya eski azaltma girişiminde bulunduğunda bir uygulama artık onaylama temel alınan kapsayıcı sınırları.  
  
-   Üye değişkeni c sınıfı yığınının artık korumalı bildirildi. Daha önce bu üye değişkeni ortak bildirildi.  
  
-   Money_get::do_get davranışı değişmiştir. Daha önce ile para miktarını ayrıştırılırken daha fazla kesir basamak için frac_digits, tümünü kullanmak için kullanılan do_get denir. Şimdi, en çok frac_digits karakter tükettikten sonra ayrıştırma do_get durdurur.  
  
### <a name="atl"></a>ATL  
  
-   ATL bir bağımlılık CRT üzerinde oluşturulamıyor. Visual Studio'nun önceki sürümleri kullanabilirsiniz # ATL projesinde CRT üzerinde en düşük düzeyde bağımlı hale atl_mın_crt define. Visual C++ 2008'de tüm ATL projeleri atl_mın_crt tanımlanan bağımsız olarak CRT üzerinde en az bağımlıdır.  
  
-   ATL Sunucu codebase CodePlex üzerinde paylaşılan kaynaklı proje olarak yayımlanmıştır ve Visual Studio bir parçası olarak yüklü değil. Kodlama ve kod çözme atlenc.h ve yardımcı işlevlerini sınıflardan ve atlutil.h ve atlpath.h sınıflardan veri tutulmuştur ve şimdi ATL kitaplığının parçasıdır. ATL Sunucu ile ilişkilendirilen çeşitli dosyaları artık Visual Studio bir parçasıdır.  
  
-   Bazı işlevler artık DLL'de dahil edilir. Bunlar, hala içeri aktarma kitaplığı'nda bulunur. Bu işlevler statik olarak kullanan kodu etkilemez. Bu işlevler dinamik olarak kullanan kodu etkiler.  
  
-   Makroları PROP_ENTRY ve PROP_ENTRY_EX kullanım ve güvenlik nedenleriyle makroları PROP_ENTRY_TYPE andPROP_ENTRY_TYPE_EX ile değiştirilir.  
  
### <a name="atlmfc-shared-classes"></a>ATL/MFC Paylaşılan Sınıfları  
  
-   ATL bir bağımlılık CRT üzerinde oluşturulamıyor. Visual Studio'nun önceki sürümleri kullanabilirsiniz # ATL projesinde CRT üzerinde en düşük düzeyde bağımlı hale atl_mın_crt define. Visual C++ 2008'de tüm ATL projeleri atl_mın_crt tanımlanan bağımsız olarak CRT üzerinde en az bağımlıdır.  
  
-   ATL Sunucu codebase CodePlex üzerinde paylaşılan kaynaklı proje olarak yayımlanmıştır ve Visual Studio bir parçası olarak yüklü değil. Kodlama ve kod çözme atlenc.h ve yardımcı işlevlerini sınıflardan ve atlutil.h ve atlpath.h sınıflardan veri tutulmuştur ve şimdi ATL kitaplığının parçasıdır. ATL Sunucu ile ilişkilendirilen çeşitli dosyaları artık Visual Studio bir parçasıdır.  
  
-   Bazı işlevler artık DLL'de dahil edilir. Bunlar, hala içeri aktarma kitaplığı'nda bulunur. Bu işlevler statik olarak kullanan kodu etkilemez. Bu işlevler dinamik olarak kullanan kodu etkiler.  
  
### <a name="mfc"></a>MFC  
  
-   CTime sınıfı: CTime sınıfı şimdi C.E. 1/1/1900 ' başlayarak tarihleri kabul eder 1/1/1970 C.E. yerine              
-   Sekme sırası MFC iletişim kutuları denetimlerin: MFC ActiveX denetimi sekme sırası eklediyseniz birden çok denetimlerin bir MFC iletişim kutusunda doğru sekme sırasını dağıtılmış. Bu değişiklik, bu sorunu düzeltir.  
  
     Örneğin, bir ActiveX denetimi olan bir MFC iletişim uygulama oluşturun ve birkaç denetimleri düzenleyin. ActiveX denetimi Düzenle denetimlerin sekme sırasını ortasında getirin. Uygulamayı başlatmak, ActiveX denetimi sonra sekmesini sonra sekme sırası olan bir düzenleme denetimine tıklayın. Bu değişiklik öncesinde, odağını sekme sırasında bir sonraki düzenleme denetimi yerine ActiveX denetimi aşağıdaki düzenleme denetimine geçti.  
  
-   CFileDialog sınıfı: CFileDialog sınıfı için özel şablonlar otomatik olarak Windows Vista için bağlantı noktası kurulmuş olamaz. Bunlar hala kullanılabilir, ancak ek işlevsellik mevcut değil veya Windows Vista Stili iletişim kutularını bakar.  
  
-   CWnd sınıfı ve CFrameWnd sınıfı: CWnd::GetMenuBarInfo yöntemi kaldırıldı.  
  
     CFrameWnd::GetMenuBarInfo yöntemi artık sanal olmayan bir yöntemdir. Daha fazla bilgi için Windows SDK'sı GetMenuBarInfo Functionin bakın.  
  
-   MFC ISAPI desteği: MFC artık uygulamaları oluşturma ile Internet sunucusu uygulama programı arabirimi (ISAPI) destekler. ISAPI uzantıları, ISAPI uygulaması oluşturmak istiyorsanız, doğrudan çağırın.  
  
-   Kullanım dışı ANSI API'ları: MFC için bazı yöntemler ANSI sürümlerini kullanım dışı bırakılmıştır. Bu yöntemlerin Unicode sürümleri gelecekteki uygulamalarınızda kullanır. Daha fazla bilgi için yapı gereksinimleri için Windows Vista ortak denetimleri bakın.  
  
## <a name="visual-c-2005-breaking-changes"></a>Visual C++ 2005 önemli değişiklikler  
  
### <a name="crt"></a>CRT  
  
-   Birçok işlevler kullanım dışı bırakıldı. Kullanım dışı CRT işlevleri bakın.  
  
-   Birçok işlevleri artık geçersiz parametreler verildiyse yürütme durdurma kendi parametrelerini doğrulayın. Bu, geçersiz parametreleri geçirir ve bunları yoksayılıyor veya yalnızca bir hata kodu döndürüyor işlevi kullanır. kodu kesilebilir. Parametre doğrulaması bakın.  
  
-   Dosya tanımlayıcısı değeri -2 şimdi stdout ve stderr konsol penceresine sahip bir Windows uygulaması örnekte olduğu gibi çıktı için kullanılabilir olmadığını göstermek için kullanılır. Kullanılan önceki değeri -1 idi. Daha fazla bilgi için bkz: [_fileno](../c-runtime-library/reference/fileno.md).  
  
-   Tek iş parçacıklı CRT kitaplıkları, libc.lib ve libcd.lib, kaldırılmış. Çok iş parçacıklı CRT kitaplıkları kullanabilirsiniz. /ML derleyici bayrağı artık desteklenmiyor. Bazı işlevler olmayan kilitleme sürümleri birden çok iş parçacıklı kodu ve tek iş parçacıklı kodu arasındaki performans farkının potansiyel olarak önemli olduğu durumlarda eklenmiştir.  
  
-   Pow, çift pow (int, int) yüklemesini standarda daha iyi uyacak şekilde kaldırıldı.  
  
-   Doğası gereği güvenilir olmaması nedeniyle %n Biçim belirticisi işlevlerin printf ailesinin hiçbirinde varsayılan artık desteklenmiyor. %N karşılaştıysanız varsayılan davranışı geçersiz parametre işleyicisi çağırmaktır. %N desteğini etkinleştirmek için _set_printf_count_output (aynı zamanda see_get_printf_count_output) kullanın.  
  
-   sprintf şimdi imzalanmış sıfır eksi işareti yazdırır.  
  
-   swprintf standart uyacak şekilde değiştirildi; Şimdi, bir boyut parametresi gerektirir. Swprintf boyutu parametresi olmadan form kullanım dışı bırakıldı.  
  
-   _set_security_error_handler kaldırılmıştır. Bu işlev tüm çağrıları kaldırın; varsayılan işleyici kadar güvenli güvenlik hataları postalarla yoludur.  
  
-   (_USE_32BIT_TIME_T tanımlanmadığı sürece) time_t şimdi bir 64-bit değeridir.  
  
-   _Spawn, _wspawn işlevleri şimdi errno dokunulmadan C Standart tarafından belirtilen başarı bırakın.  
  
-   RTC geniş karakterler artık varsayılan olarak kullanır.  
  
-   Kayan nokta denetim word destek işlevlerini kullanımdan kaldırıldı/CLR veya/CLR ile derlenmiş uygulamalar için: Saf. Etkilenen işlevlerdir _clear87, _clearfp, _control87, _controlfp, _fpreset, _status87, _statusfp. _CRT_MANAGED_FP_NO_DEPRECATE tanımlayarak kullanımdan kaldırma uyarısı devre dışı bırakabilir, ancak yönetilen kodda bu işlevlerin öngörülemeyen ve desteklenmeyen kullanılmasıdır.  
  
-   Bazı işlevler şimdi const işaretçileri döndürür. Eski, const dışı davranış _CONST_RETURN tanımlayarak reinstated. Etkilenen işlevleri  
  
    1.  memchr, wmemchr  
  
    2.  strchr, wcschr, _mbschr, _mbschr_l  
  
    3.  strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l  
  
    4.  strrchr, wcsrchr, _mbsrchr, _mbsrchr_l  
  
    5.  strstr, wcsstr, _mbsstr, _mbsstr_l  
  
-   Setargv.obj veya Wsetargv.obj bağlanırken artık çift tırnak içine kapsayan tarafından komut satırında bir joker karakter genişletmesi gizlemek mümkündür. Daha fazla bilgi için bkz: [joker karakter bağımsız değişkenlerini genişletme](../c-language/expanding-wildcard-arguments.md).  
  
### <a name="standard-library-2005"></a>Standart Kitaplığı (2005)  
  
-   Özel durum sınıfı (bulunan \<özel durum > Üstbilgi) std ad alanına taşındı. Önceki sürümlerde, bu sınıfın genel ad alanında oluştu. Özel durum sınıfı bulunamadığını belirten hataları gidermek için aşağıdakileri ekleyin kodunuzu deyimiyle: ad alanını kullanarak std;  
  
-   Valarray::resize() çağrılırken valarray içeriğini kaybolur ve varsayılan değerlerle değiştirilecek. Resize() yöntemi valarray yeniden başlatmak yerine gibi vektör dinamik olarak büyütmek için tasarlanmıştır.  
  
-   Hata ayıklama yineleyiciler: Uygulamalar C çalışma zamanı kitaplığı hata ayıklama sürümü ile oluşturulmuş ve çalışma zamanında onaylar hangi kullanım yineleyiciler görmek yanlış başlayabilir. Bunlar devre dışı bırakmak için onaylar, _HAS_ITERATOR_DEBUGGING tanımlaması gerekir (yerini [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) Visual Studio 2010 sonra) 0. Daha fazla bilgi için bkz: [hata ayıklama yineleyici desteği](../standard-library/debug-iterator-support.md)  
  
## <a name="visual-c-net-2003-breaking-changes"></a>Visual C++ .NET 2003 önemli değişiklikler  
  
### <a name="compiler"></a>Derleyici  
  
-   Şimdi tanımlanan önişlemci yönergesi (C2004) için gerekli parantez kapatılıyor.  
  
-   Açık özelleştirmeleri artık birincil şablondan şablon parametreleri Bul ([derleyici hatası C2146](../error-messages/compiler-errors-1/compiler-error-c2146.md)).  
  
-   Korumalı üye (n) yalnızca bir üye işlevi, (n) olduğu bir üye (A) sınıftan bir sınıfın (B) aracılığıyla erişilebilir ([derleyici hatası C2247](../error-messages/compiler-errors-1/compiler-error-c2247.md)).  
  
-   Derleyici iyileştirilmiş erişilebilirlik denetimlerinde şimdi Algıla erişilemez temel sınıflar ([derleyici hatası C2248](../error-messages/compiler-errors-1/compiler-error-c2248.md)).  
  
-   Bir özel durum yakalandı olamaz yıkıcı ve/veya kopya Oluşturucu olduğu erişilemez (C2316).  
  
-   Varsayılan bağımsız değişkenler artık izin işlev işaretçileri ([derleyici hatası C2383](../error-messages/compiler-errors-1/compiler-error-c2383.md)).  
  
-   Statik veri üyesi türetilmiş sınıf başlatılamıyor ([derleyici hatası C2477](../error-messages/compiler-errors-1/compiler-error-c2477.md)).  
  
-   Bir typedef başlatma standardına göre izin verilmiyor ve şimdi derleyici hatası oluşturur ([derleyici hatası C2513](../error-messages/compiler-errors-2/compiler-error-c2513.md)).  
  
-   bool olduğu şimdi uygun türde ([derleyici hatası C2632](../error-messages/compiler-errors-2/compiler-error-c2632.md)).  
  
-   Bir UDC aşırı yüklenmiş işleçler ile artık belirsizlik oluşturabilirsiniz ([C2666](../error-messages/compiler-errors-2/compiler-error-c2666.md)).  
  
-   Daha fazla ifade artık geçerli null işaretçinin sabitleri olarak kabul edilir ([derleyici hatası C2668](../error-messages/compiler-errors-2/compiler-error-c2668.md)).  
  
-   Şablon <> yerde burada derleyici önceden gelmez, artık gerekli ([derleyici hatası C2768](../error-messages/compiler-errors-2/compiler-error-c2768.md)).  
  
-   Üye işlevi ourside expilicit uzmanlaşması sınıf işlevi zaten açıkça bir şablon sınıfı uzmanlık özelleştirilmiş, geçerli değil ([derleyici hatası C2910](../error-messages/compiler-errors-2/compiler-error-c2910.md)).  
  
-   Kayan nokta tür olmayan şablon parametreleri artık izin ([derleyici hatası C2993](../error-messages/compiler-errors-2/compiler-error-c2993.md)).  
  
-   Sınıf şablonları şablon tür bağımsız değişkenleri (C3206) izin verilmez.  
  
-   Arkadaş işlev adları, ad alanı içeren içine artık sunulan ([derleyici hatası C3767](../error-messages/compiler-errors-2/compiler-error-c3767.md)).  
  
-   Derleyici artık ek virgül makrosu (C4002) olarak kabul eder.  
  
-   Bir form () Başlatıcı ile oluşturulan POD türünde bir nesne varsayılan başlatıldı (C4345) olacaktır.  
  
-   TypeName olduğu şimdi bağımlı bir adı bir tür olarak kabul edilmesi için ise gereklidir ([Derleyici Uyarısı (düzey 1) C4346](../error-messages/compiler-warnings/compiler-warning-level-1-c4346.md)).  
  
-   Yanlış şablon özelleştirmeleri olarak kabul işlevleri artık bunu (C4347) olarak kabul edilir.  
  
-   Statik veri üyeleri (C4356) türetilmiş sınıf başlatılamaz.  
  
-   Sınıf şablonu uzmanlık bir dönüş türü kullanılmadan önce tanımlanması gerekiyor ([Derleyici Uyarısı (Düzey 3) C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md)).  
  
-   Derleyici şimdi ulaşılamaz kod (C4702) bildirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Visual Studio'da Visual c++ yenilikleri](../what-s-new-for-visual-cpp-in-visual-studio.md)

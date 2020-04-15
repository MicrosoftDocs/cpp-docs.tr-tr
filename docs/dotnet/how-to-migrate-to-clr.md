---
title: "Nasıl yapılur: -clr'ye geçirin"
ms.custom: get-started-article
ms.date: 09/18/2018
helpviewer_keywords:
- upgrading Visual C++ applications, /clr compiler option
- compiling native code [C++]
- interoperability [C++], /clr compiler option
- interop [C++], /clr compiler option
- migration [C++], /clr compiler option
- /clr compiler option [C++], porting to
ms.assetid: c9290b8b-436a-4510-8b56-eae51f4a9afc
ms.openlocfilehash: 339b1f3172d8b82ece3e98f117f53ed399cbd4e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376076"
---
# <a name="how-to-migrate-to-clr"></a>Nasıl yapılır: /clr'ye Geçiş

Bu konu, **/clr** ile yerel kodu derlerken ortaya çıkan sorunları tartışır (daha fazla bilgi için [/clr (Ortak Dil Çalışma Süresi Derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) bakın). **/clr,** diğer yerel C++ koduna ek olarak yerel C++ kodunun çağrılmasına ve .NET derlemelerinden çağrılmasına olanak tanır. **/clr**ile derlemenin avantajları hakkında daha fazla bilgi için [Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md) [ve Yerel ve .NET Birlikte Çalışabilirlik](../dotnet/native-and-dotnet-interoperability.md) bölümüne bakın.

## <a name="known-issues-compiling-library-projects-with-clr"></a>/clr ile Kitaplık Projelerini Derlemede Bilinen Sorunlar

Visual Studio **/ clr**ile kütüphane projeleri derleme könemli bazı sorunları içerir:

- Kodunuz CRuntimeClass ile çalışma zamanında türleri [sorgulayabilir::FromName](../mfc/reference/cruntimeclass-structure.md#fromname). Ancak, bir tür MSIL .dll 'de **(/clr**ile `FromName` derlenmişse), yönetilen .dll'de statik oluşturucular çalışmadan önce oluşursa çağrı başarısız olabilir (FromName çağrısı yönetilen .dll'de kod yürütüldükten sonra gerçekleşirse bu sorunu görmezsiniz). Bu sorunu aşmak için, yönetilen .dll'deki bir işlevi tanımlayarak, dışa aktararak ve yerel MFC uygulamasından çağırarak yönetilen statik oluşturucunun yapısını zorlayabilirsiniz. Örneğin:

    ```
    // MFC extension DLL Header file:
    __declspec( dllexport ) void EnsureManagedInitialization () {
       // managed code that won't be optimized away
       System::GC::KeepAlive(System::Int32::MaxValue);
    }
    ```

## <a name="compile-with-visual-c"></a>Visual C++ ile derleme

Projenizdeki herhangi bir modülde **/clr** kullanmadan önce, öncelikle yerel projenizi Visual Studio 2010 ile derleyip bağla.

Sırayla izlenen aşağıdaki adımlar, **bir /clr** derlemesi için en kolay yolu sağlar. Bu adımların her biri sonra projenizi derlemek ve çalıştırmak önemlidir.

### <a name="versions-prior-to-visual-studio-2003"></a>Visual Studio 2003 Öncesi Versiyonlar

Visual Studio 2003'ten önceki bir sürümden Visual Studio 2010'a yükseltiyorsanız, Visual Studio 2003'teki gelişmiş C++ standart uygunluğuyla ilgili derleyici hatalarını görebilirsiniz

### <a name="upgrading-from-visual-studio-2003"></a>Visual Studio 2003'ten yükseltme

Visual Studio 2003 ile daha önce inşa edilen projeler de ilk olarak **/clr** olmadan derlenmelidir, çünkü Visual Studio artık ANSI/ISO uyumluluğunu ve bazı kırılma değişikliklerini artırmıştır. En çok dikkat gerektiren değişiklik [CRT Güvenlik Özellikleri.](../c-runtime-library/security-features-in-the-crt.md) CRT kullanan kod, amortisman uyarıları oluşturma olasılığı çok yüksektir. Bu uyarılar bastırılabilir, ancak [crt işlevlerinin yeni Güvenlikgelişmiş Sürümlerine](../c-runtime-library/security-enhanced-versions-of-crt-functions.md) geçiş tercih edilir, çünkü bunlar daha iyi güvenlik sağlar ve kodunuzda güvenlik sorunları ortaya çıkarabilir.

### <a name="upgrading-from-managed-extensions-for-c"></a>C++ için Yönetilen Uzantılardan Yükseltme

Visual Studio 2005'ten başlayarak, C++ için Yönetilen Uzantılar ile yazılan kod **/clr**altında derlenmeyen.

## <a name="convert-c-code-to-c"></a>C Kodunu C++'a dönüştürün

Visual Studio C dosyalarını derleyecek olsa da, **/clr** derlemesi için bunları C++'a dönüştürmek gerekir. Gerçek dosya adının değiştirilmesi gerekmez; **/Tp** kullanabilirsiniz (bkz: [/Tc, /Tp, /TC, /TP (Kaynak Dosya Türünü Belirt) .)](../build/reference/tc-tp-tc-tp-specify-source-file-type.md) **/clr**için C++ kaynak kodu dosyaları gerekli olsa da, nesne yönelimli paradigmaları kullanmak için kodunuzu yeniden hesaba katmaya gerek olmadığını unutmayın.

C kodu, C++ dosyası olarak derlendiğinde değişiklik gerektirme olasılığı çok yüksektir. C++ türü güvenlik kuralları katıdır, bu nedenle tür dönüştürmeleri dökümlerle açık olarak yapılmalıdır. Örneğin, malloc geçersiz bir işaretçi döndürür, ancak c'de herhangi bir türe döküm ile atanabilir:

```
int* a = malloc(sizeof(int));   // C code
int* b = (int*)malloc(sizeof(int));   // C++ equivalent
```

İşlev işaretçileri c++'da kesinlikle tür açısından güvenlidir, bu nedenle aşağıdaki C kodu değişiklik gerektirir. C++'da işlev işaretçisi türünü tanımlayan bir sözcük `typedef` oluşturmak ve ardından işlev işaretçileri oluşturmak için bu türü kullanmak en iyisidir:

```
NewFunc1 = GetProcAddress( hLib, "Func1" );   // C code
typedef int(*MYPROC)(int);   // C++ equivalent
NewFunc2 = (MYPROC)GetProcAddress( hLib, "Func2" );
```

C++ ayrıca işlevlerin başvurulmadan veya çağrılmadan önce prototiple denilmesini veya tam olarak tanımlanmasını da gerektirir.

C++'da anahtar kelime olması gereken C kodunda kullanılan tanımlayıcıların **(sanal,** **yeni,** **silme,** **bool,** **doğru,** **yanlış,** vb.) yeniden adlandırılması gerekir. Bu genellikle basit arama ve değiştirme işlemleri ile yapılabilir.

```
COMObj1->lpVtbl->Method(COMObj, args);  // C code
COMObj2->Method(args);  // C++ equivalent
```

## <a name="reconfigure-project-settings"></a>Proje Ayarlarını Yeniden Yapılandır

Projeniz Visual Studio 2010'da derleyip çalıştırıladıktan sonra varsayılan yapılandırmaları değiştirmek yerine **/clr** için yeni proje yapılandırmaları oluşturmanız gerekir. **/clr** bazı derleyici seçenekleriyle uyumsuzdur ve ayrı yapılandırmalar oluşturmak, projenizi yerel veya yönetilen olarak oluşturmanıza olanak tanır. Özellik sayfaları iletişim kutusunda **/clr** seçildiğinde, **/clr** ile uyumlu olmayan proje ayarları devre dışı bırakılır (ve **/clr** daha sonra seçilmemişse devre dışı bırakılan seçenekler otomatik olarak geri yüklenmez).

### <a name="create-new-project-configurations"></a>Yeni Proje Yapılandırmaları Oluşturma

Varolan proje ayarlarınızı temel alan bir proje yapılandırması oluşturmak için **Yeni Proje Yapılandırma İletişim Kutusu'ndaki** **(Yapı** > **Yapılandırma Yöneticisi** > **Etkin Çözüm Yapılandırması** > **Yeni)**'deki **Ayarlar'dan Kopyala** seçeneğini kullanabilirsiniz. Hata Ayıklama yapılandırması için bunu bir kez ve Sürüm yapılandırması için bir kez yapın. Sonraki değişiklikler daha sonra **/clr'ye** özgü yapılandırmalara uygulanarak özgün proje yapılandırmaları bozulmadan bırakılabilir.

Özel yapı kuralları kullanan projeler ekstra dikkat gerektirebilir.

Bu adım, makefiles kullanan projeler için farklı etkileri vardır. Bu durumda ayrı bir yapı hedefi yapılandırılabilir veya orijinalin bir kopyasından **/clr** derlemesine özgü sürüm oluşturulabilir.

### <a name="change-project-settings"></a>Proje Ayarlarını Değiştirme

**/clr** geliştirme ortamında [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)yönergelerini izleyerek seçilebilir. Daha önce de belirtildiği gibi, bu adım çakışan proje ayarlarını otomatik olarak devre dışı kalacaktır.

> [!NOTE]
> Yönetilen bir kitaplık veya web hizmeti projesini Visual Studio 2003'ten yükseltirken, **/Zl** derleyici seçeneği **Komut Satırı** özelliği sayfasına eklenir. Bu LNK2001 neden olur. Çözmek için **Komut Satırı** özelliği sayfasından **/Zl'yi** kaldırın. Bkz. [/Zl (Varsayılan Kitaplık Adı Atla)](../build/reference/zl-omit-default-library-name.md) ve Daha fazla bilgi için [derleyici yi ve yapı özelliklerini ayarlayın.](../build/working-with-project-properties.md) Veya, bağlayıcının **Ek Bağımlılıklar** özelliğine msvcrt.lib ve msvcmrt.lib ekleyin.

Makefiles ile oluşturulan projelerde, **/clr** eklendikten sonra uyumsuz derleyici seçenekleri el ile devre dışı bırakılmalı. [/clr](../build/reference/clr-restrictions.md) ile uyumlu olmayan derleyici seçenekleri hakkında **/clr**bilgi için bkz.

### <a name="precompiled-headers"></a>Önceden Derlenmiş Üstbilgi

Önceden derlenmiş üstbilgi **/clr**altında desteklenir. Ancak, CPP dosyalarınızın bazılarını **/clr** ile derlerseniz (geri kalanını yerel olarak derleyerek) bazı değişiklikler gerekir, çünkü **/clr** ile oluşturulan önceden derlenmiş üstbilgi **/clr**olmadan oluşturulanlarla uyumlu değildir. Bu uyumsuzluk **/ clr** üretir ve meta veri gerektirir gerçeğinden kaynaklanmaktadır. Bu nedenle **/clr** derlenen modüller meta veri içermeyen önceden derlenmiş üstbilgileri kullanamaz ve **/clr** olmayan modüller meta veri içeren önceden derlenmiş üstbilgi dosyalarını kullanamaz.

Bazı modüllerin derlendiği **/clr'ın** derlendiği bir projeyi derlemenin en kolay yolu, önceden derlenmiş üstbilgilerden tamamen devre dışı kalmaktır. (Proje Özelliği Sayfaları iletişim kutusunda C/C++ düğümünü açın ve Önceden Derlenmiş Üstbilgi'yi seçin. Ardından, Önceden Derlenmiş Üstbilgi Oluştur/Kullan özelliğini "Önceden Derlenmiş Üstbilgi Kullanmama" olarak değiştirin.)

Ancak, özellikle büyük projeleriçin, önceden derlenmiş üstbilgi çok daha iyi derleme hızı sağlar, bu nedenle bu özelliği devre dışı bırakmak istenmez. Bu durumda, önceden derlenmiş ayrı üstbilgi kullanmak için **/clr** ve **/clr** olmayan dosyaları yapılandırmak en iyisidir. Bu, **Solution Explorer**kullanarak **/clr** olarak derlenecek modülleri çok seçerek, gruba sağ tıklayarak ve Özellikleri seçerek tek adımda yapılabilir. Ardından, sırasıyla farklı bir üstbilgi dosya adı ve PCH dosyası kullanmak için Hem Dosya Aracılığıyla PCH Oluşturma/Kullan Hem de Önceden Derlenmiş Üstbilgi Dosyası özelliklerini değiştirin.

## <a name="fixing-errors"></a>Hataları Düzeltme

**/clr** ile derleme derleyici, bağlayıcı veya çalışma zamanı hatalarına neden olabilir. Bu bölümde en sık karşılaşılan sorunlar tartışılmaktadır.

### <a name="metadata-merge"></a>Meta veri birleştirme

İki tür için oluşturulan meta veriler eşleşmediği için, veri türlerinin farklı sürümleri bağlayıcının başarısız lığına neden olabilir. (Bu genellikle bir türün üyeleri koşullu olarak tanımlandığında kaynaklanır, ancak koşullar türü kullanan tüm CPP dosyaları için aynı değildir.) Bu durumda bağlayıcı başarısız olur, yalnızca sembol adı ve türün tanımlandığı ikinci OBJ dosyasının adını bildirin. Veri türünün diğer sürümünün konumunu bulmak için OBJ dosyalarının bağlayıcıya gönderilme sırasını döndürmek genellikle yararlıdır.

### <a name="loader-lock-deadlock"></a>Yükleyici Kilidi Kilitlenme

"Yükleyici kilidi kilitlenme" oluşabilir, ancak deterministic ve algılanır ve çalışma zamanında rapor. Ayrıntılı arka plan, kılavuzve çözümler için [Karışık Derlemelerin Başlatılması'na](../dotnet/initialization-of-mixed-assemblies.md) bakın.

### <a name="data-exports"></a>Veri Dışa Aktarma

DLL verilerinin dışa aktarılması hataya açıktır ve önerilmez. Bunun nedeni, DLL'nin yönetilen bir bölümü çalıştırılana kadar bir DLL'nin veri bölümünün baş harfe çevrilmesi garanti edilmemesidir. [#using Yönergesi](../preprocessor/hash-using-directive-cpp.md)ile referans meta veri .

### <a name="type-visibility"></a>Tür Görünürlüğü

Yerel türler varsayılan olarak özeldir. Bu, yerel bir türün DLL dışında görünmemesine neden olabilir. Bu türlere `public` ekleyerek bu hatayı çözümle.

### <a name="floating-point-and-alignment-issues"></a>Kayan Nokta ve Hizalama Sorunları

`__controlfp`ortak dilde çalışma zamanında desteklenmez (daha fazla bilgi için [_control87, _controlfp \__control87_2'](../c-runtime-library/reference/control87-controlfp-control87-2.md) ye bakın). CLR de [hizalamak](../cpp/align-cpp.md)saygı olmaz.

### <a name="com-initialization"></a>COM Başlatma

Ortak Dil Çalışma Süresi, bir modül başharflendiğinde (COM otomatik olarak başharfe geçtiğinde, mta olarak yapılır) COM'u otomatik olarak başlatmayı gerçekleştirir. Sonuç olarak, com'un zaten başolarak başlatılmasını gösteren iade kodları açıkça başlatılması. CLR COM'u başka bir iş parçacığı modeline zaten başlattığında, com'u bir iş parçacığı modeliyle açıkça başlatmaya çalışmak uygulamanızın başarısız olmasına neden olabilir.

Ortak dil çalışma süresi varsayılan olarak MTA olarak COM başlar; bunu değiştirmek için [/CLRTHREADATTRIBUTE (ClR İş Parçacığı Atföy'i ayarla)](../build/reference/clrthreadattribute-set-clr-thread-attribute.md) kullanın.

### <a name="performance-issues"></a>Performans Sorunları

MSIL'e oluşturulan yerel C++ yöntemleri dolaylı olarak çağrıldığında (sanal işlev çağrıları veya işlev işaretçileri kullanılarak) azalan performans görebilirsiniz. Bu konuda daha fazla bilgi için [Double Thunking](../dotnet/double-thunking-cpp.md)'e bakın.

Yerel den MSIL'e taşınırken, çalışma setinizin boyutunda bir artış fark edeceksiniz. Bunun nedeni, ortak dil çalışma süresinin programların doğru çalışmasını sağlamak için birçok özellik sağlamasıdır. **/clr** uygulamanız düzgün çalışmıyorsa, daha fazla bilgi için C4793'ü (varsayılan olarak kapalı) etkinleştirmek isteyebilirsiniz, bkz. [Compiler Warning (level 1 and 3) C4793](../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md)

### <a name="program-crashes-on-shutdown"></a>Program Kapatma üzerinde Çöküyor

Bazı durumlarda, yönetilen kodunuz çalışma tamamlanmadan CLR kapatılabilir. Kullanma `std::set_terminate` `SIGTERM` ve buna neden olabilir. Daha fazla bilgi için [sinyal Sabitleri](../c-runtime-library/signal-constants.md) ve [set_terminate](../c-runtime-library/abnormal-termination.md) bakın.

## <a name="using-new-visual-c-features"></a>Yeni Görsel C++ Özelliklerini Kullanma

Uygulamanız derlendikten, bağlantılar aladıktan ve çalıştırıldıktan sonra **,clr**ile derlenen herhangi bir modülde .NET özelliklerini kullanmaya başlayabilirsiniz. Daha fazla bilgi [için, Runtime Platformları için Bileşen Uzantıları'na](../extensions/component-extensions-for-runtime-platforms.md)bakın.

Visual C++'da .NET programlama hakkında bilgi için bkz:

- [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

- [Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)

- [Çalışma Zamanı Platformları için Bileşen Uzantıları](../extensions/component-extensions-for-runtime-platforms.md)

## <a name="see-also"></a>Ayrıca bkz.

[Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)

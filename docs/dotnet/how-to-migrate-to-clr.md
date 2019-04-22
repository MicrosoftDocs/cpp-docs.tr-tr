---
title: "Nasıl yapılır: -CLR'ye geçiş"
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
ms.openlocfilehash: 6ac470b85a14bfe32c7f3fe47168180687669ec6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58781321"
---
# <a name="how-to-migrate-to-clr"></a>Nasıl yapılır: / CLR'ye geçiş

Bu konuda, yerel kod ile derleme yaparken ortaya çıkan sorunları ele alınmıştır **/CLR** (bkz [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) daha fazla bilgi için). **/ CLR** yerel C++ kodunu çağırır ve diğer yerel C++ kod yanı sıra .NET derlemelerinden çağrılmasına olanak sağlar. Bkz: [karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md) ve [Native ve .NET ile birlikte çalışabilirlik](../dotnet/native-and-dotnet-interoperability.md) avantajları hakkında daha fazla bilgi ile derlenen **/CLR**.

## <a name="known-issues-compiling-library-projects-with-clr"></a>Bilinen sorunlar derlenirken kitaplık projeleri/CLR ile

Visual Studio, kitaplık projeleri ile derleme yaparken bazı bilinen sorunlar içeren **/CLR**:

- Kodunuzu türleri ile çalışma zamanında sorgulayabilir [CRuntimeClass::FromName](../mfc/reference/cruntimeclass-structure.md#fromname). Ancak, bir türü bir MSIL .dll ise (ile derlenmiş **/CLR**), çağrı `FromName` statik oluşturucular (görmezsiniz Bu sorun kod sahip olduktan sonra FromName çağrısı olursa yönetilen .dll çalıştırmadan önce gerçekleşirse başarısız olabilir Yönetilen .dll yürütülür). Bu sorunu gidermek için bir işlev içinde yönetilen .dll tanımlama, vermek ve yerel bir MFC uygulamasından çağırma tarafından yönetilen statik oluşturucunun oluşumu zorlayabilirsiniz. Örneğin:

    ```
    // MFC extension DLL Header file:
    __declspec( dllexport ) void EnsureManagedInitialization () {
       // managed code that won't be optimized away
       System::GC::KeepAlive(System::Int32::MaxValue);
    }
    ```

## <a name="compile-with-visual-c"></a>Visual C++ ile derleme

Kullanmadan önce **/CLR** , projenizdeki herhangi bir modülü üzerinde derleyin ve Visual Studio 2010 ile yerel projenize bağlayın.

Sırayla aşağıdaki adımlar, kolay yolunu belirtin. bir **/CLR** derleme. Derlemek ve bu adımların her biri sonra projenizi çalıştırmak önemlidir.

### <a name="versions-prior-to-visual-c-2003"></a>Visual C++ 2003 önceki sürümler

Visual Studio 2010 Visual C++ 2003'ten önceki bir sürümden yükseltiyorsanız, Gelişmiş C++ Standart uyumluluk Visual C++ 2003'te ilgili derleyici hataları görebilirsiniz.

### <a name="upgrading-from-visual-c-2003"></a>Visual C++ 2003'ten yükseltme

Önceki Visual C++ 2003 ile oluşturulan projeleri de ilk derlenmelidir olmadan **/CLR** gibi Visual Studio artık ANSI/ISO uyumluluk ve bazı önemli değişiklikler arttı. Büyük olasılıkla en dikkat etmeniz gereken değişiklik [CRT'deki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md). CRT kullanan kodu kullanımdan kaldırma uyarıları üretmek neredeyse kesindir. Bu uyarı bastırılabilir, ancak yeni geçirme [CRT işlevleri, Security-Enhanced sürümleri](../c-runtime-library/security-enhanced-versions-of-crt-functions.md) daha iyi güvenlik sağlar ve güvenlik sorunlarını kodunuzda gösterebilir tercih edilen, aynıdır.

### <a name="upgrading-from-managed-extensions-for-c"></a>C++ için Yönetilen Uzantılar'dan yükseltme

Visual Studio 2005'te başlayarak, C++ için Yönetilen Uzantılar'ile yazılan kod altında derlenemeyecektir **/CLR**.

## <a name="convert-c-code-to-c"></a>C++ için C kodu Dönüştür

Visual Studio C dosyaları derleyeceği olsa da, bunları C++ için dönüştürmek gerekli olan bir **/CLR** derleme. Gerçek dosya adının değiştirilmesi gerekmez; kullanabileceğiniz **/Tp** (bkz [/Tc, /Tp, /TC, /TP (kaynak dosya türünü belirtin)](../build/reference/tc-tp-tc-tp-specify-source-file-type.md).) C++ kaynak kodu dosyaları için gerekli olmasına rağmen dikkat **/CLR**, nesne yönelimli paradigmalarını kullanmak için kodunuzu yeniden etkimesi gerekli değildir.

C kodu bir C++ dosyası olarak derlenmiş değişiklikleri gerektirilecek olasılıktır. C++ tür güvenliği kuralları strict, olduğundan tür dönüştürmeleri yayınları ile açık olarak yapılmalıdır. Örneğin, malloc void bir işaretçi döndürür, ancak c herhangi bir türü ile bir atama bir işaretçiye atanabilir:

```
int* a = malloc(sizeof(int));   // C code
int* b = (int*)malloc(sizeof(int));   // C++ equivalent
```

Ayrıca işlev işaretçileri kesinlikle tür kullanımı uyumlu C++'da olduğundan, aşağıdaki C kodu değişikliği gerektiriyor. C++'da oluşturmak en iyi bir `typedef` işlev işaretçisi türü tanımlar ve ardından işlev işaretçilerine dönüştürme için söz konusu türünü kullanın:

```
NewFunc1 = GetProcAddress( hLib, "Func1" );   // C code
typedef int(*MYPROC)(int);   // C++ equivalent
NewFunc2 = (MYPROC)GetProcAddress( hLib, "Func2" );
```

C++ aynı zamanda gerektirir işlevleri prototipli ya da tam olarak tanımlanmış ya da bunlar başvurulan veya çağrılan yüklenmeden önce.

C++ anahtar sözcükleri hareketlidir C kod içinde kullanılan tanımlayıcıları (gibi **sanal**, **yeni**, **Sil**, **bool**, **true** , **false**, vs.) kaydedilmelidir. Bu, genellikle basit arama ve değiştirme işlemlerini ile yapılabilir.

```
COMObj1->lpVtbl->Method(COMObj, args);  // C code
COMObj2->Method(args);  // C++ equivalent
```

## <a name="reconfigure-project-settings"></a>Proje ayarlarını yeniden yapılandırın

Projenizi derler ve Visual Studio 2010'da çalışan sonra yeni proje yapılandırmaları için oluşturmalısınız **/CLR** varsayılan yapılandırmaları değiştirmek yerine. **/ CLR** bazı derleyici seçenekleri ile uyumlu değildir ve ayrı yapılandırmaları projeniz yerel veya yönetilen olarak oluşturmanızı sağlar. Zaman **/CLR** özellik sayfaları iletişim kutusu, proje ayarları ile uyumlu değil olarak seçili **/CLR** devre dışı bırakıldı (ve devre dışı bırakılan seçeneklerin otomatik olarak geri yüklenmez varsa **/CLR** sonradan seçildiyse).

### <a name="create-new-project-configurations"></a>Yeni proje yapılandırmaları oluşturma

Kullanabileceğiniz **Ayarları Şuradan Kopyala** seçeneğini **yeni proje yapılandırma iletişim kutusu** (**derleme** > **Configuration Manager**  >  **Etkin çözüm yapılandırması** > **yeni**) var olan proje ayarlarınızı temel alan bir proje yapılandırması oluşturmak için. Bu kez hata ayıklama yapılandırması için ve yayın yapılandırması için bir kez yaparsınız. Sonraki değişiklikler ardından uygulanabilir **/CLR** -özgün proje yapılandırmalarını dokunmadan özgü yapılandırmalar.

Özel derleme kuralları kullanan projeler çok dikkat gerektirebilir.

Bu adım, derleme görevleri dosyalarını kullanan projeler için farklı etkilere sahiptir. Bu durumda, ayrı bir yapı hedefi yapılandırılabilir veya sürüme özgü **/CLR** derleme özgün bir kopyasından oluşturulabilir.

### <a name="change-project-settings"></a>Proje ayarlarını değiştir

**/ CLR** yönergelerini takip ederek geliştirme ortamında seçilebilir [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md). Daha önce belirtildiği gibi bu adımı çakışan proje ayarları devre dışı bırakır.

> [!NOTE]
>  Yönetilen kitaplık veya web hizmeti projesi Visual C++ 2003'ten yükseltme yaparken **/Zl** eklenen derleyici seçeneği olacak **komut satırı** özellik sayfası. Bu, LNK2001 neden olur. Kaldırma **/Zl** gelen **komut satırı** çözmek için özellik sayfası. Bkz: [/Zl (varsayılan kitaplık adını atla)](../build/reference/zl-omit-default-library-name.md) ve [derleyici ayarlayın ve derleme özellikleri](../build/working-with-project-properties.md) daha fazla bilgi için. Veya, msvcrt.lib ve msvcmrt.lib bağlayıcıya ait ekleme **ek bağımlılıklar** özelliği.

Derleme görevleri dosyası ile oluşturulan projeleri için uyumlu derleyici seçenekleri el ile bir kez devre dışı bırakılmalıdır **/CLR** eklenir. Bkz: /[/CLR kısıtlamalar](../build/reference/clr-restrictions.md) ile uyumlu derleyici seçenekleri hakkında bilgi için **/CLR**.

### <a name="precompiled-headers"></a>Önceden derlenmiş üst bilgiler

Önceden derlenmiş üst bilgiler desteklenen altında **/CLR**. Ancak, yalnızca CPP dosyalarınızdan bazıları derlerseniz **/CLR** (rest yerel olarak derleme) bazı değişiklikler ile oluşturulan önceden derlenmiş üstbilgiler gerekli olacaktır **/CLR** olanlar uyumlu değil olmadan oluşturulan **/CLR**. Bu uyumsuzluk olduğu Bunun nedeni, **/CLR** oluşturur ve meta verileri gerektirir. Derlenmiş modüller **/CLR** meta verileri içermez önceden derlenmiş üst bilgiler kullanamaz ve olmayan **/CLR** modülleri, meta verileri içeren önceden derlenmiş üst bilgi dosyaları kullanamaz.

Burada bazı modüller derlendiği bir projeyi derlemek için en kolay yolu **/CLR** önceden derlenmiş üst bilgiler tamamen devre dışı bırakmaktır. (Proje özellik sayfaları iletişim kutusu C/C++ düğümünü açın ve önceden derlenmiş üst bilgiler seçin. Ardından önceden derlenmiş üst bilgi Oluştur/Kullan özelliğini "Kullanarak önceden derlenmiş üstbilgi için" olarak değiştirin.)

Ancak, özellikle büyük projeler için bu özelliği devre dışı bırakmayı tercih, yani çok daha iyi derleme hızı önceden derlenmiş üst bilgiler sağlar. Bu durumda yapılandırmak en iyi **/CLR** ve olmayan **/CLR** ayrı önceden derlenmiş üstbilgileri kullanmak için dosyaları. Bu, tek bir adımda tarafından yapılabilir çoklu seçilen derlenmesi için modülleri **/CLR** kullanarak **Çözüm Gezgini**grubuna sağ tıklayın ve Özellikler'i seçerek. Ardından farklı bir üst bilgi dosyası adını ve PCH dosyası sırasıyla kullanılacak dosya üzerinden PCH Oluştur/Kullan ve önceden derlenmiş üst bilgi dosyası özelliklerini değiştirin.

## <a name="fixing-errors"></a>Hataları düzeltme

İle derlerken **/CLR** derleyici, bağlayıcı veya çalışma zamanı hatalarına neden olabilir. Bu bölümde, en yaygın sorunlar ele alınmaktadır.

### <a name="metadata-merge"></a>Meta veri birleştirme

Veri türleri farklı sürümleri, bağlayıcının iki tür için oluşturulan meta verileri eşleşmediğinden başarısız olmasına neden olabilir. (Bu genellikle bir türün üyeleri koşullu olarak tanımlanmıştır, ancak koşulları türünü kullanan tüm CPP dosyalarına aynı olmayan neden olur.) Bu durumda yalnızca sembol adı ve türü tanımlandığı ikinci OBJ dosyası adını raporlama bir bağlayıcı başarısız. Genellikle, bir veri türü sürümü konumunu bulmak için OBJ dosyaları bağlayıcıya gönderilir sırasını döndürmek kullanışlıdır.

### <a name="loader-lock-deadlock"></a>Yükleyici kilidi kilitlenmesi

"Yükleyici kilidi kilitlenmesi" oluşabilir, ancak kararlı ve algılanır ve çalışma zamanında bildirdi. Bkz: [karışık derlemeleri başlatma](../dotnet/initialization-of-mixed-assemblies.md) ayrıntılı arka plan, rehberlik ve çözümler.

### <a name="data-exports"></a>Verileri dışarı aktarma

DLL'leri dışarı aktarma, hata yapmaya açık ve önerilmez. Bir DLL veri bölümünü yönetilen DLL kısmı yürütülene kadar başlatılması garanti edilmez olmasıdır. Başvuru meta verileriyle [#using yönergesi](../preprocessor/hash-using-directive-cpp.md).

### <a name="type-visibility"></a>Tür Görünürlüğü

Yerel türler varsayılan olarak özeldir. Bu, DLL dışında görünür olmadığı bir yerel tür içinde sonuçlanabilir. Ekleyerek bu hatayı gidermek `public` bu türleri için.

### <a name="floating-point-and-alignment-issues"></a>Nokta ve hizalama sorunları kayan

`__controlfp` Ortak dil çalışma zamanı üzerinde desteklenmiyor (bkz [_control87, _controlfp, \__control87_2](../c-runtime-library/reference/control87-controlfp-control87-2.md) daha fazla bilgi için). CLR ayrıca değil uyar [hizalama](../cpp/align-cpp.md).

### <a name="com-initialization"></a>COM başlatması

Bir modül başlatıldığında ortak dil çalışma zamanı COM otomatik olarak başlatır (COM otomatik olarak başlatıldığında, bunu MTA gibi yapılır). Sonuç olarak, açıkça COM başlatılıyor, COM zaten başlatılmış olduğunu gösteren dönüş kodları verir. CLR başka bir iş parçacığı modeline COM önceden başlatıldı, COM ile bir iş parçacığı modeli açıkça başlatılmaya çalışılırken, uygulamanızın başarısız olmasına neden olabilir.

Ortak dil çalışma zamanı, varsayılan olarak COM MTA başlatır; kullanma [/CLRTHREADATTRIBUTE (CLR iş parçacığı özniteliğini Ayarla)](../build/reference/clrthreadattribute-set-clr-thread-attribute.md) değiştirmek için.

### <a name="performance-issues"></a>Performans sorunları

Yerel C++ yöntemler için MSIL oluşturulan dolaylı olarak çağrıldığında, performansın görebilirsiniz (sanal işlev çağrıları veya işlev işaretçilerine kullanarak). Bunun hakkında daha fazla bilgi edinmek için [çift dönüştürme](../dotnet/double-thunking-cpp.md).

MSIL Yerelden taşırken, çalışma kümenizin boyutunu artış fark edeceksiniz. Ortak dil çalışma zamanı programların doğru çalışmasını sağlamak için birçok özellik sağlar olmasıdır. Varsa, **/CLR** uygulama düzgün çalışmıyorsa, C4793 etkinleştirmek isteyebilirsiniz (varsayılan olarak kapalıdır) bkz [Derleyici Uyarısı (düzey 1 ve 3) C4793](../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md) daha fazla bilgi için.

### <a name="program-crashes-on-shutdown"></a>Kapatma sırasında program kilitleniyor

Bazı durumlarda, CLR kapatılabilir yönetilen kodunuzun bitirmeden önce çalışıyor. Kullanarak `std::set_terminate` ve `SIGTERM` bu neden olabilir. Bkz: [sinyal sabitleri](../c-runtime-library/signal-constants.md) ve [set_terminate](../c-runtime-library/abnormal-termination.md) daha fazla bilgi için.

## <a name="using-new-visual-c-features"></a>Yeni Visual C++ özellikleri kullanma

Uygulama derlerken, bağlantılar ve çalıştırmaları sonra herhangi bir modüle ile derlenmiş .NET özellikleri kullanmaya başlayabilirsiniz **/CLR**. Daha fazla bilgi için [çalışma zamanı platformları için bileşen uzantıları](../extensions/component-extensions-for-runtime-platforms.md).

C++ için Yönetilen Uzantılar'ı kullandıysanız, kodunuzu yeni söz dizimini kullanacak şekilde dönüştürebilirsiniz. Ayrıntılar için Yönetilen Uzantılar dönüştürme için C++, bkz: [ C++CLI geçiş öncüsü](../dotnet/cpp-cli-migration-primer.md).

Visual c++'ta .NET hakkında bilgi için bkz:

- [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

- [Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)

- [Çalışma Zamanı Platformları için Bileşen Uzantıları](../extensions/component-extensions-for-runtime-platforms.md)

## <a name="see-also"></a>Ayrıca bkz.

[Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)

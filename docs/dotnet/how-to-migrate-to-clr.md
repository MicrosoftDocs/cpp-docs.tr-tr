---
title: "Nasıl yapılır: - clr geçirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- upgrading Visual C++ applications, /clr compiler option
- compiling native code [C++]
- interoperability [C++], /clr compiler option
- interop [C++], /clr compiler option
- migration [C++], /clr compiler option
- /clr compiler option [C++], porting to
ms.assetid: c9290b8b-436a-4510-8b56-eae51f4a9afc
caps.latest.revision: "37"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f38450831ad85a09d3a43173f8febc7841f02c09
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-migrate-to-clr"></a>Nasıl yapılır: /clr'ye Geçiş
Bu konuda yerel kodu derleme sırasında ortaya çıkan sorunları ele alınmıştır **/CLR** (bkz [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) daha fazla bilgi için). **/ CLR** çağırma ve .NET derlemelerden yönetilmeyen modüller ile uyumluluğunu korurken çağrılması için Visual C++ modül sağlar. Bkz: [karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md) ve [yerel ve .NET birlikte çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md) avantajları hakkında daha fazla bilgi ile derlenen **/CLR**.  
  
## <a name="known-issues-compiling-library-projects-with-clr"></a>Bilinen sorunlar derleme kitaplık projeleri/CLR ile  
 Visual Studio kitaplık projeleri ile derlerken bazı bilinen sorunlar içerir **/CLR**:  
  
-   Kodunuz ile çalışma zamanında türleri sorgulayabilir [CRuntimeClass::FromName](../mfc/reference/cruntimeclass-structure.md#fromname). Ancak, bir tür bir MSIL .dll ise (ile derlenmiş **/CLR**), çağrısı `FromName` statik oluşturucular (görmezsiniz Bu sorun kod sahip olduktan sonra FromName çağrısı durumda yönetilen .dll çalıştırmadan önce meydana gelmesi durumunda başarısız olabilir Yönetilen .dll yürütülen). Bu sorunu geçici olarak çözmek için bir işlev yönetilen .dll tanımlayarak, vermek ve yerel MFC uygulamasından çağırma yönetilen statik oluşturucunun yapımı zorlayabilirsiniz. Örneğin:  
  
    ```  
    // MFC extension DLL Header file:  
    __declspec( dllexport ) void EnsureManagedInitialization () {  
       // managed code that won't be optimized away  
       System::GC::KeepAlive(System::Int32::MaxValue);  
    }  
    ```  
  
## <a name="compile-with-visual-c"></a>Visual C++ ile derleme  
 Kullanmadan önce **/CLR** projenizdeki herhangi bir modül üzerinde ilk derlemek ve Visual Studio 2010 ile yerel projenizi bağlantı.  
  
 Sırada, aşağıdaki adımlar, kolay yolunu girin bir **/CLR** derleme. Derlemek ve projenizin bu adımların her biri sonra çalıştırmak önemlidir.  
  
### <a name="versions-prior-to-visual-c-2003"></a>Visual C++ 2003'den önceki sürümleri  
 Visual Studio 2010 için Visual C++ 2003'ten önceki bir sürümünden yükseltme yapıyorsanız, Gelişmiş C++ standart uygunluğuna Visual C++ 2003'te ilgili derleyici hataları görebilirsiniz  
  
### <a name="upgrading-from-visual-c-2003"></a>Visual C++ 2003'ten yükseltme  
 Visual C++ 2003 ile oluşturulan projeleri önceki ayrıca ilk derlenmelidir olmadan **/CLR** Visual Studio şimdi ANSI/ISO uyumluluk ve bazı önemli değişiklikler artırmıştır gibi. En dikkat gerektiren büyük olasılıkla değişiklik [CRT'deki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md). CRT kullanan kodu kullanımdan kaldırma uyarıları üretmek olasılığı yüksektir. Bu uyarılar gizlenen, ancak yeni geçirme [CRT işlevleri, Security-Enhanced sürümleri](../c-runtime-library/security-enhanced-versions-of-crt-functions.md) daha iyi güvenlik sağlar ve güvenlik sorunları kodunuzda gösterebilir tercih edilen, aynıdır.  
  
### <a name="upgrading-from-managed-extensions-for-c"></a>C++ için Yönetilen Uzantılar'dan yükseltme  
 Visual Studio 2005'ten başlayarak, C++ için Yönetilen Uzantılar ile yazılan kod altında derleme olmaz **/CLR**.  
  
## <a name="convert-c-code-to-c"></a>C kodunu C++ olarak dönüştürme  
 Visual Studio C dosyalarını derleyecek rağmen C++ için dönüştürmek gerekli olan bir **/CLR** derleme. Gerçek dosya adının değiştirilmesi gerekmez; kullanabileceğiniz **/Tp** (bkz [TP, /Tp, TP, /TP (kaynak dosya türünü belirtin)](../build/reference/tc-tp-tc-tp-specify-source-file-type.md).) C++ kaynak kodu dosyaları için gerekli olsa unutmayın **/CLR**, nesne yönelimli örneklerinde kullanmak için kodunuzu yeniden faktörü gerekli değildir.  
  
 C kodu C++ dosyası olarak derlenmiş değiştiğinde gerektirecek şekilde olasılığı yüksektir. Tür dönüştürmeleri atamaları ile açık hale getirilmesi gereken şekilde C++ tür güvenliği katı, kurallardır. Örneğin, malloc void işaretçi verir, ancak bir cast ile c herhangi bir türü için bir işaretçi atanabilir:  
  
```  
int* a = malloc(sizeof(int));   // C code  
int* b = (int*)malloc(sizeof(int));   // C++ equivalent  
```  
  
 Ayrıca işlev işaretçileri kesinlikle tür kullanımı uyumlu C++'da olduğundan, aşağıdaki C kodu değişikliği gerektiriyor. C++'ta oluşturmak en iyi bir `typedef` işlev işaretçisi türü tanımlar ve işlev işaretçisi dönüştürmek için bu türü kullanın:  
  
```  
NewFunc1 = GetProcAddress( hLib, "Func1" );   // C code  
typedef int(*MYPROC)(int);   // C++ equivalent  
NewFunc2 = (MYPROC)GetProcAddress( hLib, "Func2" );  
```  
  
 C++ de gerektirir işlevleri örneklenmiş veya tam olarak tanımlanan ya da bunlar başvurulan veya çağrılan yüklenmeden önce.  
  
 C++ anahtar sözcükleri olurlarsa C kodunda kullanılan tanımlayıcılar (gibi `virtual`, `new`, `delete`, `bool`, `true`, `false`, vs.) kaydedilmelidir. Bu, genellikle basit arama ve değiştirme işlemleri ile yapılabilir.  
  
 Son olarak, C tarzı COM çağrıları v tablosunun açık kullanımını gerektirdiğinde ve `this` işaretçi, C++ şunları desteklemez:  
  
```  
COMObj1->lpVtbl->Method(COMObj, args);  // C code  
COMObj2->Method(args);  // C++ equivalent  
```  
  
## <a name="reconfigure-project-settings"></a>Proje ayarlarını yeniden Yapılandır  
 Sonra Proje derlenir ve Visual Studio 2010'da çalışan yeni proje yapılandırmaları için oluşturmalısınız **/CLR** varsayılan yapılandırmaları değiştirmek yerine. **/ CLR** bazı derleyici seçenekleri ile uyumlu değildir ve ayrı yapılandırmaları oluşturma projeniz yerel veya yönetilen olarak oluşturmanızı sağlar. Zaman **/CLR** özellik sayfaları iletişim kutusunda, proje ayarları ile uyumlu değil seçili **/CLR** devre dışı bırakıldı (ve devre dışı bırakılmış seçenekler otomatik olarak geri yüklenmez varsa   **/CLR** sonradan seçildiyse).  
  
### <a name="create-new-project-configurations"></a>Yeni proje yapılandırmaları oluşturma  
 Kullanabileceğiniz **ayarları kopyalama kaynağı** seçeneğini [yeni proje yapılandırması iletişim kutusu](http://msdn.microsoft.com/en-us/cca616dc-05a6-4fe3-bdc1-40c72a66f2be) mevcut proje ayarlarınızı temel alan bir proje yapılandırma oluşturmak için. Bu kez hata ayıklama yapılandırması için ve bir kez yayın yapılandırmasını yapın. Sonraki değişiklikler ardından uygulanabilir **/CLR** -özgün proje yapılandırmaları dokunmadan özgü yapılandırmalar.  
  
 Özel derleme kuralları kullanan projelerin çok dikkat gerektirebilir.  
  
 Bu adım, derleme görevleri dosyaları kullanan projeler için farklı etkilere sahiptir. Bu durumda, ayrı bir derleme hedefi yapılandırılabilir veya sürüme özgü **/CLR** derleme özgün kopyadan oluşturulabilir.  
  
### <a name="change-project-settings"></a>Proje ayarlarını değiştir  
 **/ CLR** 'ndaki yönergeleri izleyerek geliştirme ortamında seçilebilir [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md). Daha önce belirtildiği gibi bu adım çakışan proje ayarlarını devre dışı bırakır.  
  
> [!NOTE]
>  Yönetilen bir kitaplığı veya web hizmeti projesini Visual C++ 2003'ten yükseltirken **/Zl** eklenen derleyici seçeneği **komut satırı** özellik sayfası. Bu LNK2001 neden olur. Kaldırma **/Zl** gelen **komut satırı** çözümlemek için özellik sayfası. Bkz: [/Zl (varsayılan kitaplık adını atla)](../build/reference/zl-omit-default-library-name.md) ve [proje özellikleriyle çalışma](../ide/working-with-project-properties.md) daha fazla bilgi için. Veya msvcrt.lib ve msvcmrt.lib bağlayıcıya ait ekleme **ek bağımlılıklar** özelliği.  
  
 Derleme görevleri dosyaları ile oluşturulmuş projelerde uyumsuz derleyici seçenekleri el ile bir kez devre dışı bırakılmalıdır **/CLR** eklenir. Bkz: /[/CLR kısıtlamalar](../build/reference/clr-restrictions.md) ile uyumlu olmayan derleyici seçenekleri hakkında bilgi için **/CLR**.  
  
### <a name="precompiled-headers"></a>Önceden derlenmiş üst bilgileri  
 Önceden derlenmiş başlıklar altında desteklenir **/CLR**. Ancak, yalnızca bazı CPP dosyalarınız derleme varsa **/CLR** (doğal olarak kalanı derleme) bazı değişiklikler ile oluşturulan önceden derlenmiş üstbilgiler gerekli olacak **/CLR** olanlar uyumlu değil olmadan oluşturulan **/CLR**. Bu uyumsuzluğun nedeni due için nedeni olduğunu **/CLR** oluşturur ve meta verileri gerektirir. Derlenmiş modüller **/CLR** meta verileri, içerme önceden derlenmiş üstbilgiler kullanamazsınız ve olmayan **/CLR** modülleri meta verileri içeren önceden derlenmiş üstbilgi dosyaları kullanamazsınız.  
  
 Burada bazı modüllerin derlendiği bir projeyi derlemek için en kolay yolu **/CLR** önceden derlenmiş üstbilgiler tamamen devre dışı bırakmaktır. (Proje özellik sayfaları iletişim kutusunda, C/C++ düğümünü açın ve önceden derlenmiş başlıkları seçin. Ardından Oluştur/Kullan önceden derlenmiş üstbilgiler özelliğini "Kullanarak önceden derlenmiş üstbilgi için" olarak değiştirin.)  
  
 Bu özellik devre dışı bırakma arzu değil ancak, özellikle büyük projeler için önceden derlenmiş üst bilgiler çok daha iyi derleme hızı sağlar, böylece. Bu durumda yapılandırmak en iyisidir **/CLR** ve olmayan **/CLR** dosyalarını ayrı önceden derlenmiş üst bilgileri kullanın. Bu, tek bir adımda tarafından yapılabilir birden fazla seçerek derlenmesi için modülleri **/CLR** Solution Explorer kullanarak grubuna sağ tıklatıp Özellikler'i seçerek. Ardından bir üstbilgisi farklı dosya adı ve PCH dosyası kullanmak için sırasıyla dosya üzerinden PCH Oluştur/Kullan ve önceden derlenmiş üstbilgi dosyası özelliklerini değiştirin.  
  
## <a name="fixing-errors"></a>Hatalarını çözme  
 İle derleme **/CLR** derleyici, bağlayıcı veya çalışma zamanı hatalarına neden olabilir. Bu bölümde, en sık karşılaşılan sorunlar açıklanmaktadır.  
  
### <a name="metadata-merge"></a>Meta veri birleştirme  
 Veri türleri farklı sürümlerini bağlayıcının iki tür için oluşturulan meta veri eşleşmediği için başarısız olmasına neden olabilir. (Bu genellikle bir türün üyeleri koşullu olarak tanımlanır, ancak koşulları türünü kullanan tüm CPP dosyaları için aynı olmayan neden olur.) Bu durumda bağlayıcı, yalnızca simge adı ve türü tanımlandığı ikinci OBJ dosyasının adı raporlama başarısız olur. Genellikle, bir veri türü sürümünün konumunu bulmak için OBJ dosyaları bağlayıcıya gönderilir sırasını döndürmek kullanışlıdır.  
  
### <a name="loader-lock-deadlock"></a>Yükleyici kilidi kilitlenmesi  
 Visual Studio 2010 ve daha sonra "Yükleyici kilidi kilitlenmesi" hala önceki sürümlerde, ancak belirleyici ve oluşabilir algıladı ve çalışma zamanında bildirdi. Bkz: [karışık derlemeleri başlatma](../dotnet/initialization-of-mixed-assemblies.md) ayrıntılı arka plan, konusunda rehberlik ve çözümler.  
  
### <a name="data-exports"></a>Verileri dışarı aktarma  
 DLL'leri dışarı aktarma hata eğilimindedir ve önerilmez. Bu durum, DLL veri bölümü yönetilen DLL kısmı yürütülene kadar başlatılması için kesin değildir çünkü. Başvuru meta verileriyle [#using yönergesi](../preprocessor/hash-using-directive-cpp.md).  
  
### <a name="type-visibility"></a>Tür Görünürlüğü  
 Yerel türler varsayılan olarak özeldir. Bu DLL dışında görünür olmaması yerel bir tür neden olabilir. Ekleyerek bu hatayı gidermek `public` bu tür için.  
  
### <a name="floating-point-and-alignment-issues"></a>Kayan nokta ve hizalama sorunları  
 `__controlfp`Ortak dil çalışma zamanı üzerinde desteklenmiyor (bkz [_control87, _controlfp, \__control87_2](../c-runtime-library/reference/control87-controlfp-control87-2.md) daha fazla bilgi için). CLR ayrıca saygı göstermeyecektir [Hizala](../cpp/align-cpp.md).  
  
### <a name="com-initialization"></a>COM başlatma  
 Bir modül başlatıldığında ortak dil çalışma zamanı COM otomatik olarak başlatır (COM otomatik olarak başlatıldığında, bunu MTA gibi yapılır). Sonuç olarak, COM açıkça başlatma COM önceden başlatıldı gösteren dönüş kodları verir. CLR zaten başka bir iş parçacığı modeline COM başlatıldı, COM ile bir iş parçacığı modelini açıkça başlatma girişiminde, uygulamanızın başarısız olmasına neden olabilir.  
  
 Ortak dil çalışma zamanı COM MTA gibi varsayılan olarak başlatır; kullanmak [/CLRTHREADATTRIBUTE (CLR iş parçacığı özniteliğini Ayarla)](../build/reference/clrthreadattribute-set-clr-thread-attribute.md) değiştirmek için.  
  
### <a name="performance-issues"></a>Performans sorunları  
 MSIL için üretilen yerel C++ yöntemleri dolaylı olarak çağrıldığında performansın görebilirsiniz (sanal işlev çağrıları veya işlev işaretçileri kullanarak). Bunun hakkında daha fazla bilgi edinmek için [çift dönüştürme](../dotnet/double-thunking-cpp.md).  
  
 MSIL Yerelden taşırken, çalışma kümesi boyutu artış fark edeceksiniz. Ortak dil çalışma zamanı programların doğru çalışmasını sağlamak için birçok özellik sağlamasından kaynaklanır. Varsa, **/CLR** uygulama düzgün çalışmıyorsa, C4793 etkinleştirmek isteyebilirsiniz (varsayılan olarak kapalıdır) bkz [Derleyici Uyarısı (düzey 1 ve 3) C4793](../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md) daha fazla bilgi için.  
  
### <a name="program-crashes-on-shutdown"></a>Kapatma sırasında program kilitleniyor  
 Bazı durumlarda, CLR kapatılabilir, yönetilen kod bitmeden önce çalışan. Kullanarak `std::set_terminate` ve `SIGTERM` bu neden olabilir. Bkz: [sinyal sabitleri](../c-runtime-library/signal-constants.md) ve [set_terminate](../c-runtime-library/abnormal-termination.md) daha fazla bilgi için.  
  
## <a name="using-new-visual-c-features"></a>Yeni Visual C++ özellikleri kullanma  
 Uygulama derlerken, bağlantılar ve çalıştırmalarını sonra ile derlenmiş herhangi bir modüle .NET özellikleri kullanmaya başlayabilirsiniz **/CLR**. Daha fazla bilgi için bkz: [çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md).  
  
 C++ için Yönetilen Uzantılar kullandıysanız, kodunuzu yeni sözdizimini kullanmak için dönüştürebilirsiniz. Söz dizimi farkları özeti için bkz: [C++ sözdizimi yükseltme denetim listesi için (NOTINBUILD) Yönetilen Uzantılar](http://msdn.microsoft.com/en-us/edbded88-7ef3-4757-bd9d-b8f48ac2aada). C++ için Yönetilen Uzantılar dönüştürme hakkında daha fazla bilgi için bkz: [C + +/ CLI geçiş öncüsü](../dotnet/cpp-cli-migration-primer.md).  
  
 Visual C++ içinde .NET programlama hakkında bilgi için bkz:  
  
-   [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)  
  
-   [Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)  
  
-   [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
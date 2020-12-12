---
description: "Daha fazla bilgi edinin: nasıl yapılır:/clr ' a geçiş"
title: "Nasıl yapılır: -clr'ye geçiş"
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
ms.openlocfilehash: 39853f755074a4999f39f9e04445234abfbe93b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286403"
---
# <a name="how-to-migrate-to-clr"></a>Nasıl yapılır: /clr'ye Geçiş

Bu konuda, yerel kodu **/clr** ile derlerken ortaya çıkan sorunlar ele alınmaktadır (daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) ). **/clr** , yerel c++ kodunun diğer yerel c++ koduna ek olarak .net derlemelerinden çağrılmasını ve çağrılmasını sağlar. **/Clr** ile derlemenin avantajları hakkında daha fazla bilgi için bkz. [karma (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md) ve [yerel ve .net birlikte çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md) .

## <a name="known-issues-compiling-library-projects-with-clr"></a>Clr ile kitaplık projelerini derleme bilinen sorunları

Visual Studio, **/clr** ile kitaplık projelerini derlerken bazı bilinen sorunları içerir:

- Kodunuz, [CRuntimeClass:: FromName](../mfc/reference/cruntimeclass-structure.md#fromname)ile çalışma zamanında türleri sorgulayabilir. Ancak, bir tür MSIL. dll ' de ( **/clr** ile derlenmiş) ise, `FromName` statik oluşturucular yönetilen. dll ' de çalıştırılmadan önce oluşursa, çağrısı başarısız olabilir (Bu sorunu, bu durum yönetilen. dll ' de kod yürütüldükten sonra FromName çağrısı gerçekleşirse bu sorunu görmezsiniz). Bu sorunu geçici olarak çözmek için yönetilen. dll ' de bir işlev tanımlayarak, dışarı aktararak ve yerel MFC uygulamasından çağırarak, yönetilen statik oluşturucunun oluşturulmasını zorlayabilirsiniz. Örneğin:

    ```
    // MFC extension DLL Header file:
    __declspec( dllexport ) void EnsureManagedInitialization () {
       // managed code that won't be optimized away
       System::GC::KeepAlive(System::Int32::MaxValue);
    }
    ```

## <a name="compile-with-visual-c"></a>Visual C++ ile derle

Projenizdeki herhangi bir modülde **/clr** kullanmadan önce, önce Visual Studio 2010 ile yerel projenizi derleyin ve bağlayın.

Aşağıdaki adımlar sırayla bir **/clr** derlemesinin en kolay yolunu sağlar. Bu adımların her biri sonrasında projenizi derlemek ve çalıştırmak önemlidir.

### <a name="versions-prior-to-visual-studio-2003"></a>Visual Studio 2003 öncesi sürümler

Visual Studio 2003 ' den önceki bir sürümden Visual Studio 2010 ' e yükseltiyorsanız, Visual 2003 Studio 'da gelişmiş C++ standart uyumluluğu ile ilgili derleyici hataları görebilirsiniz.

### <a name="upgrading-from-visual-studio-2003"></a>Visual Studio 2003 ' den yükseltme

Visual Studio 2003 ile daha önce oluşturulmuş Projeler, Visual Studio artık ANSI/ISO uyumluluğunu ve bazı önemli değişiklikleri arttığı için ilk olarak **/clr** olmadan derlenmelidir. En çok dikkat gerektiren değişiklikler [CRT 'Daki güvenlik özellikleridir](../c-runtime-library/security-features-in-the-crt.md). CRT kullanan kodun kullanımdan kaldırma uyarıları üretme olasılığı yüksektir. Bu uyarılar bastırılabilir, ancak daha iyi güvenlik sağladığı ve kodunuzda güvenlik sorunlarını açığa çıkarmayabilecekleri [CRT işlevlerinin yeni güvenlik Gelişmiş sürümlerine](../c-runtime-library/security-enhanced-versions-of-crt-functions.md) geçiş tercih edilir.

### <a name="upgrading-from-managed-extensions-for-c"></a>C++ için Yönetilen Uzantılar 'den yükseltme

Visual Studio 2005 ' den başlayarak C++ için Yönetilen Uzantılar ile yazılan kod **/clr** altında derlenmez.

## <a name="convert-c-code-to-c"></a>C kodunu C++ ' ya Dönüştür

Visual Studio C dosyalarını derleyebilse de, bir **/clr** derlemesi Için bunları C++ ' a dönüştürmeniz gerekir. Gerçek dosya adının değiştirilmesi gerekmez; **/TP** kullanabilirsiniz (bkz. [/TC,/TP,/TC,/TP (kaynak dosya türünü belirtin)](../build/reference/tc-tp-tc-tp-specify-source-file-type.md).) C++ kaynak kodu dosyalarının **/clr** için gerekli olmasına rağmen, nesne odaklı paradigmalarına kullanmak üzere kodunuzun yeniden çarpanının gerekli olmadığı unutulmamalıdır.

C kodu, C++ dosyası olarak derlendiğinde değişiklik yapılmasını çok olasıdır. C++ tür güvenliği kuralları katı, bu nedenle tür dönüştürmeleriyle açık yapılmalıdır. Örneğin, malloc void bir işaretçi döndürür, ancak Cast ile C içindeki herhangi bir tür işaretçisine atanabilir:

```
int* a = malloc(sizeof(int));   // C code
int* b = (int*)malloc(sizeof(int));   // C++ equivalent
```

İşlev işaretçileri C++ ' da kesinlikle tür açısından güvenlidir, bu nedenle aşağıdaki C kodu değişiklik gerektirir. C++ ' da **`typedef`** , işlev işaretçisi türünü tanımlayan bir oluşturmak ve ardından işlev işaretçilerini atamak için bu türü kullanmak en iyisidir:

```
NewFunc1 = GetProcAddress( hLib, "Func1" );   // C code
typedef int(*MYPROC)(int);   // C++ equivalent
NewFunc2 = (MYPROC)GetProcAddress( hLib, "Func2" );
```

C++ Ayrıca işlevlerine başvurulmadan veya çağrılabilecek şekilde işlevlerin prototip veya tam olarak tanımlanması gerekir.

C++ ' de (örneğin,,,,, vb.) anahtar sözcük olarak gerçekleşen C kodunda kullanılan tanımlayıcılar **`virtual`** **`new`** **`delete`** **`bool`** **`true`** **`false`** yeniden adlandırılması gerekir. Bu, genellikle basit arama ve değiştirme işlemleri ile yapılabilir.

```
COMObj1->lpVtbl->Method(COMObj, args);  // C code
COMObj2->Method(args);  // C++ equivalent
```

## <a name="reconfigure-project-settings"></a>Proje ayarlarını yeniden yapılandırın

Projeniz Visual Studio 2010 ' de derlendikten ve çalıştıktan sonra, varsayılan yapılandırmalarda değişiklik yapmak yerine **/clr** için yeni proje konfigürasyonları oluşturmanız gerekir. **/clr** bazı derleyici seçenekleriyle uyumsuzdur ve ayrı yapılandırma oluşturma, projenizi yerel veya yönetilen olarak oluşturmanıza imkan tanır. Özellik sayfaları iletişim kutusunda **/clr** seçildiğinde, **/clr** ile uyumlu olmayan proje ayarları devre dışı bırakılır (ve **/clr** daha sonra seçili değilse devre dışı bırakma seçenekleri otomatik olarak geri yüklenmez).

### <a name="create-new-project-configurations"></a>Yeni proje yapılandırması oluştur

    >    >    >  Mevcut proje ayarlarınıza göre bir proje yapılandırması oluşturmak için yeni proje yapılandırması iletişim kutusundaki (derleme Configuration Manager etkin çözüm yapılandırması yeni) ayarları Kopyala seçeneğini kullanabilirsiniz. Bunu hata ayıklama yapılandırması için ve yayın yapılandırması için bir kez yapın. Daha sonra, sonraki değişiklikler yalnızca **/clr** 'e özgü yapılandırmalara uygulanabilir ve özgün proje yapılandırmalarının bozulmadan bırakılır.

Özel yapı kuralları kullanan projeler, fazladan dikkat gerektirebilir.

Bu adımın, makefiles kullanan projeler için farklı etkileri vardır. Bu durumda, ayrı bir yapı hedefi yapılandırılabilir veya **/clr** derlemesine özgü sürüm, orijinalin bir kopyasından oluşturulabilir.

### <a name="change-project-settings"></a>Proje ayarlarını değiştir

/clr [(ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)içindeki yönergeleri izleyerek, **/clr** geliştirme ortamında seçilebilir. Daha önce belirtildiği gibi, bu adım çakışan proje ayarlarını otomatik olarak devre dışı bırakır.

> [!NOTE]
> Yönetilen bir kitaplığı veya Web hizmeti projesini Visual Studio 2003 ' den yükseltirken, **/zl** derleyici seçeneği **komut satırı** Özellik sayfasına eklenir. Bu, LNK2001 neden olur. Çözümlemek için **komut satırı** özellik sayfasından **/zl** 'yi kaldırın. Daha fazla bilgi için bkz. [/zl (varsayılan kitaplık adını atla)](../build/reference/zl-omit-default-library-name.md) ve [derleyici ve derleme özelliklerini ayarlayın](../build/working-with-project-properties.md) . Veya, bağlayıcının **ek bağımlılıklar** özelliğine Msvcrt. lib ve msvcmrt. lib ekleyin.

Makefiles ile oluşturulmuş projeler için, **/clr** eklendikten sonra uyumsuz derleyici seçeneklerinin el ile devre dışı bırakılması gerekir. **/Clr** ile uyumlu olmayan derleyici seçenekleri hakkında bilgi için bkz./[/clr kısıtlamaları](../build/reference/clr-restrictions.md) .

### <a name="precompiled-headers"></a>Önceden derlenmiş üstbilgiler

Ön derlenmiş üstbilgiler **/clr** altında desteklenir. Ancak, CPP dosyalarından bazılarını **/clr** ile derlerseniz (geri kalanı yerel olarak derlerken), **/clr** ile oluşturulan önceden derlenmiş üstbilgiler **/clr** olmadan oluşturulanlarla uyumlu olmadığından bazı değişiklikler yapmanız gerekir. Bu uyumsuzluk, **/clr** ' ın oluşturduğu ve meta verileri gerektiren olguyu nedeniyle yapılır. Bu nedenle **, derlenen modüller** meta verileri içermeyen önceden derlenmiş üstbilgiler kullanamaz ve **/clr** olmayan modüller meta veri içeren önceden derlenmiş üst bilgi dosyalarını kullanamaz.

Bazı modüllerin derlendiği bir projeyi derlemenin en kolay **yolu, önceden** derlenmiş üst bilgilerin tamamen devre dışı bırakılması. (Proje özellik sayfaları iletişim kutusunda C/C++ düğümünü açın ve önceden derlenmiş üstbilgiler ' i seçin. Daha sonra önceden derlenmiş üstbilgiler oluştur/kullan özelliğini "önceden derlenmiş üst bilgileri kullanma" olarak değiştirin.

Ancak, özellikle büyük projeler için, önceden derlenmiş üstbilgiler çok daha iyi derleme hızı sağlar, bu nedenle bu özelliğin devre dışı bırakılması istenmez. Bu durumda, **/clr** ve **/clr** olmayan dosyaları ayrı önceden derlenmiş üst bilgileri kullanacak şekilde yapılandırmak en iyisidir. Bu, **Çözüm Gezgini** kullanılarak **/clr** derlenecek, gruba sağ tıklanarak özellikler seçilerek tek bir adımda yapılabilir. Ardından, sırasıyla farklı bir üstbilgi dosya adı ve PCH dosyası kullanmak için dosya ve önceden derlenmiş üst bilgi dosyası özelliklerini kullanarak oluşturma/kullanma PCH 'yi değiştirin.

## <a name="fixing-errors"></a>Hataları düzeltme

**/Clr** ile derleme, derleyici, bağlayıcı veya çalışma zamanı hatalarına neden olabilir. Bu bölümde en yaygın sorunlar ele alınmaktadır.

### <a name="metadata-merge"></a>Meta veri birleştirme

Farklı veri türleri sürümleri, iki tür için oluşturulan meta veriler eşleşmediğinden bağlayıcının başarısız olmasına neden olabilir. (Bu durum genellikle, bir tür üyelerinin koşullu olarak tanımlanmasından kaynaklanır ancak koşulların türü kullanan tüm CPP dosyaları için aynı değildir.) Bu durumda bağlayıcı başarısız olur, yalnızca sembol adını ve türün tanımlandığı ikinci OBJ dosyasının adını rapor edin. Veri türünün diğer sürümünün konumunu öğrenmek için OBJ dosyalarının bağlayıcıya gönderilme sırasını döndürmek genellikle yararlıdır.

### <a name="loader-lock-deadlock"></a>Yükleyici kilidi kilitlenmesi

"Yükleyici kilidi kilitlenmesi" oluşabilir, ancak bu durum belirleyici olur ve çalışma zamanında algılanır ve raporlanır. Ayrıntılı arka plan, kılavuz ve çözümler için [Karışık derlemelerin başlatılmasına](../dotnet/initialization-of-mixed-assemblies.md) bakın.

### <a name="data-exports"></a>Veri dışarı aktarmaları

DLL verilerini dışa aktarma işlemi hataya açıktır ve önerilmez. Bunun nedeni, dll 'nin bazı yönetilen kısımları yürütülene kadar bir DLL 'nin veri bölümünün başlatılmayacağından garanti edilmez. [#Using yönergesi](../preprocessor/hash-using-directive-cpp.md)ile meta verilere başvur.

### <a name="type-visibility"></a>Tür Görünürlüğü

Yerel türler varsayılan olarak özeldir. Bu, yerel bir türün DLL dışında görünmediğine yol açabilir. Bu türlere ekleyerek bu hatayı çözün **`public`** .

### <a name="floating-point-and-alignment-issues"></a>Kayan nokta ve hizalama sorunları

`__controlfp` ortak dil çalışma zamanında desteklenmez (daha fazla bilgi için bkz. [_control87, _controlfp \_ _control87_2](../c-runtime-library/reference/control87-controlfp-control87-2.md) ). CLR de [hizalı](../cpp/align-cpp.md)olmaz.

### <a name="com-initialization"></a>COM Başlatma

Ortak dil çalışma zamanı, bir modül başlatıldığında COM otomatik olarak başlatılır (yani, COM otomatik olarak başlatıldığında MTA olarak yapılır). Sonuç olarak com, com 'un Zaten başlatılmış olduğunu belirten dönüş kodlarını açıkça başlatma. CLR 'nin COM 'ı başka bir iş parçacığı modeline zaten başlatması durumunda bir iş parçacığı modeliyle COM başlatılmaya çalışılıyor uygulamanızın başarısız olmasına neden olabilir.

Ortak dil çalışma zamanı, COM 'yi varsayılan olarak MTA olarak başlatır; Bunu değiştirmek için [/CLRTHREADATTRIBUTE (clr Iş parçacığı özniteliğini ayarla)](../build/reference/clrthreadattribute-set-clr-thread-attribute.md) kullanın.

### <a name="performance-issues"></a>Performans Sorunları

MSIL 'e oluşturulan yerel C++ yöntemleri dolaylı olarak çağrıldığında (sanal işlev çağrıları veya işlev işaretçileri kullanarak) daha düşük performans görebilirsiniz. Bunun hakkında daha fazla bilgi için bkz. [Double thunking](../dotnet/double-thunking-cpp.md).

Yerelden MSIL 'e geçiş yaparken, çalışma kümesinin boyutunda bir artış olduğunu fark edeceksiniz. Bunun nedeni, ortak dil çalışma zamanının programların doğru şekilde çalışmasını sağlamak için birçok özellik sağlamaktır. **/Clr** uygulamanız doğru çalışmıyorsa, C4793 (varsayılan olarak kapalı) özelliğini etkinleştirmek isteyebilirsiniz. daha fazla bilgi için bkz. [Derleyici Uyarısı (düzey 1 ve 3) C4793](../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md) .

### <a name="program-crashes-on-shutdown"></a>Program kapatılırken kilitleniyor

Bazı durumlarda, yönetilen kodunuzun çalışması tamamlanmadan önce CLR kapanıyor. `std::set_terminate`Ve kullanarak `SIGTERM` buna neden olabilir. Daha fazla bilgi için bkz. [sinyal sabitleri](../c-runtime-library/signal-constants.md) ve [set_terminate](../c-runtime-library/abnormal-termination.md) .

## <a name="using-new-visual-c-features"></a>Yeni Visual C++ özellikleri kullanma

Uygulamanız derlendikten, bağlanır ve çalıştıktan sonra **/clr** ile derlenen herhangi bir modülde .NET özelliklerini kullanmaya başlayabilirsiniz. Daha fazla bilgi için bkz. [çalışma zamanı platformları Için bileşen uzantıları](../extensions/component-extensions-for-runtime-platforms.md).

Visual C++ .NET programlama hakkında daha fazla bilgi için bkz:

- [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

- [Yerel ve .NET birlikte çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)

- [Çalışma Zamanı Platformları için Bileşen Uzantıları](../extensions/component-extensions-for-runtime-platforms.md)

## <a name="see-also"></a>Ayrıca bkz.

[Karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)

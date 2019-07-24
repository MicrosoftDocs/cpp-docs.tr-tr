---
title: Visual Studio’da C++ derleyicisi ve derleme özelliklerini ayarlama
description: Derleyici ve bağlayıcı seçeneklerini ve diğer derleme C++ ayarlarını değiştirmek Için VISUAL Studio IDE 'yi kullanın.
ms.date: 07/17/2019
helpviewer_keywords:
- project properties [C++], modifying
- properties [C++]
- Visual C++ projects, properties
- projects [C++], properties
ms.assetid: 9b0d6f8b-7d4e-4e61-aa75-7d14944816cd
ms.openlocfilehash: 436c9c47d7e08176860144ce62cc874919351029
ms.sourcegitcommit: 610751254a01cba6ad15fb1e1764ecb2e71f66bf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2019
ms.locfileid: "68313443"
---
# <a name="set-compiler-and-build-properties"></a>Derleyici ve derleme özelliklerini ayarlama

IDE 'de, bir proje oluşturmak için gereken tüm bilgiler *Özellikler*olarak gösterilir. Bu bilgiler, uygulama adı, uzantı (DLL, LIB, EXE), derleyici seçenekleri, bağlayıcı seçenekleri, hata ayıklayıcı ayarları, özel derleme adımları ve diğer birçok şeyi içerir. Genellikle, bu özellikleri görüntülemek ve değiştirmek için *özellik sayfalarını* kullanırsınız. Özellik sayfalarına erişmek için, ana menüden **Proje** >  **_ProjectName_ Özellikler** ' i seçin veya **Çözüm Gezgini** ' de proje düğümüne sağ tıklayıp **Özellikler**' i seçin.

## <a name="default-properties"></a>Varsayılan Özellikler

Bir proje oluşturduğunuzda, sistem çeşitli özellikler için değerler atar. Varsayılanlar proje türüne ve uygulama sihirbazında belirlediğiniz seçeneklere bağlı olarak farklılık gösterir. Örneğin, bir ATL projesinde MıDL dosyaları ile ilgili özellikler vardır, ancak bunlar temel konsol uygulamasında yok. Varsayılan Özellikler, özellik sayfalarındaki genel bölmesinde gösterilir:

![Visual C&#43; &#43; Proje Varsayılanları](media/visual-c---project-defaults.png "görsel C++ Proje Varsayılanları")

## <a name="applying-properties-to-build-configurations-and-target-platforms"></a>Derleme yapılandırmalarına ve hedef platformlara Özellikler uygulanıyor

Uygulama adı gibi bazı özellikler, hedef platformdan bağımsız olarak tüm derleme çeşitlemelerine veya bir hata ayıklama ya da yayın derlemesi olup olmamasına bakılmaksızın uygulanır. Ancak özelliklerin çoğu yapılandırmaya bağımlıdır. Bunun nedeni, derleyicinin programın hangi platforma çalışacağını ve doğru kodu oluşturmak için hangi derleyici seçeneklerini kullanacağınızı bilmesi gerekir. Bu nedenle, bir özelliği ayarladığınızda, yeni değerin uygulanması gereken yapılandırma ve platforma dikkat etmeniz önemlidir. Yalnızca Win32 yapılarında hata ayıklamak için mi, yoksa hata ayıklama ARM ve hata ayıklama x64 için de geçerlidir mı? Örneğin, **optimizasyon** özelliği varsayılan olarak, sürüm yapılandırmasındaki **Hız (/O2) ekranı en üst düzeye** çıkaracak şekilde ayarlanmıştır, ancak hata ayıklama yapılandırmasında devre dışıdır.

Özellik sayfaları, her zaman görebileceğiniz ve gerekirse, bir özellik değerinin hangi yapılandırma ve platform için uygulanacağını görmek üzere tasarlanmıştır. Aşağıdaki çizimde, en üstteki liste kutularındaki yapılandırma ve platform bilgilerine sahip Özellik sayfaları gösterilmektedir. **Optimizasyon** özelliği burada ayarlandığında, yalnızca kırmızı oklarla gösterildiği gibi etkin yapılandırma olarak gerçekleşen Win32 Derlemeleriyle hata ayıklama için geçerli olur.

![Etkin yapılandırmayı&#43; &#43; gösteren etkin yapılandırma görsel](media/visual-c---property-pages-showing-active-configuration.png " C++ özellik sayfalarını") gösteren Visual C Özellik sayfaları

Aşağıdaki çizimde aynı proje özelliği sayfası görülmektedir, ancak yapılandırma yayın olarak değiştirilmiştir. Optimizasyon özelliğinin farklı değerini aklınızda edin. Ayrıca etkin yapılandırmanın hata ayıklama olduğunu unutmayın. Burada herhangi bir yapılandırmanın özelliklerini ayarlayabilirsiniz; etkin bir tane olması gerekmez.

![Yayın yapılandırmasını&#43; &#43; gösteren sürüm yapılandırması görsel](media/visual-c---property-pages-showing-release-config.png " C++ özellik sayfalarını") gösteren Visual C Özellik sayfaları

## <a name="target-platforms"></a>Hedef platformlar

*Hedef platform* , yürütülebilir dosyanın çalışacağı cihaz ve/veya işletim sisteminin türünü ifade eder. Birden fazla platform için bir proje oluşturabilirsiniz. Projeler için C++ kullanılabilir hedef platformlar proje türüne bağlıdır; Bunlar, Win32, x64, ARM, Android ve iOS 'a dahil değildir ancak bunlarla sınırlı değildir.     **Configuration Manager** görebileceğiniz **x86** hedef platformu, yerel C++ projelerde **Win32** ile aynıdır. Win32, 32 bit Windows ve **x64** için 64 bit Windows anlamına gelir. Bu iki platform hakkında daha fazla bilgi için bkz. [32 bitlik uygulamalar çalıştırma](/windows/desktop/WinProg64/running-32-bit-applications).

**Configuration Manager** GÖREBILECEĞINIZ C++ **tüm CPU** hedefi platformu, yerel projeler üzerinde hiçbir etkiye sahip değildir; /CLI ve diğer .NET C++proje türleri için geçerlidir. Daha fazla bilgi için bkz. [/Clrimagetype (clr görüntü türünü belirt)](reference/clrimagetype-specify-type-of-clr-image.md).

Hata ayıklama derlemesinin özelliklerini ayarlama hakkında daha fazla bilgi için bkz.:

- [C++ hata ayıklama yapılandırması proje ayarları](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration)
- [Hata Ayıklayıcısı Ayarları ve Hazırlığı](/visualstudio/debugger/debugger-settings-and-preparation)
- [Hata Ayıklama Hazırlığı: Görsel C++ proje türleri](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)
- [Visual Studio hata ayıklayıcısında simge (.pdb) ve kaynak dosyaları belirtme](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger)

## <a name="c-compiler-and-linker-options"></a>C++derleyici ve bağlayıcı seçenekleri

C++derleyici ve bağlayıcı seçenekleri sol bölmedeki **yapılandırma özellikleri**altında **CC++ /** ve **bağlayıcı** düğümleri altında bulunur. Bu, doğrudan derleyiciye geçirilecek komut satırı seçeneklerine çeviri yapar. Belirli bir seçeneğe ilişkin belgeleri okumak için orta bölmedeki seçeneğini belirleyin ve **F1**tuşuna basın. Ya da [MSVC derleyici seçenekleri](reference/compiler-options.md) ve [MSVC bağlayıcı seçenekleri](reference/linker-options.md)'ndeki tüm seçenekler için belgelere gözatabilmeniz gerekir. 

**Özellik sayfaları** iletişim kutusu yalnızca geçerli projeyle ilgili olan özellik sayfalarını gösterir. Örneğin, projede bir .idl dosyası yoksa, MIDL özellik sayfası görüntülenmez. Her özellik sayfalarında ayarı hakkında daha fazla bilgi için bkz. [Özellik sayfaları (C++)](reference/property-pages-visual-cpp.md). 

## <a name="directory-and-path-values"></a>Dizin ve yol değerleri

MSBuild, belirli dize değerleri için "Makrolar" adlı derleme zamanı sabitlerinin kullanımını, dizinler ve yollar içerir. Bunlar özellik sayfalarında gösterilir. burada, [özellik düzenleyicisini](#property_editor)kullanarak bunları bulabilirsiniz ve değiştirebilirsiniz. 

Aşağıdaki çizimde, bir Visual Studio C++ projesi için özellik sayfaları gösterilmektedir. Sol bölmede, **VC + + dizinleri** *kuralı* seçilidir ve sağ bölmede bu kuralla ilişkili özellikler listelenir. Değerler makrolar olarak adlandırılır.  `$(...)` *Makro* , Visual Studio veya MSBuild sistemi tarafından tanımlanan bir değere veya Kullanıcı tanımlı bir değere başvurabilen bir derleme zamanı sabiti. Dizin yolları gibi sabit kodlu değerler yerine makroları kullanarak, Özellikler ayarlarını makineler arasında ve Visual Studio sürümleri arasında daha kolay bir şekilde paylaşabilir ve proje ayarlarınızın özelliği içinde doğru bir şekilde katılmasını sağlayabilirsiniz. [ devralma](project-property-inheritance.md). 

![Proje özellik sayfaları](media/project_property_pages_vc.png "Project_Property_Pages_VC")

Tüm kullanılabilir makroların değerlerini görüntülemek için özellik düzenleyicisini kullanabilirsiniz.

### <a name="predefined-macros"></a>Önceden tanımlanmış makrolar

*genel makrolar*<br/>
Bir proje yapılandırmasındaki tüm öğelere uygulanır. Sözdizimi `$(name)`vardır. Visual Studio yüklemenizin kök dizinini depolayan genel `$(VCInstallDir)`bir makroya bir örnektir. Genel makro, MSBuild içindeki bir `PropertyGroup` öğesine karşılık gelir.

*öğe makroları*<br/>
Sözdizimi `%(name)`vardır. Bir dosya için, bir öğe makrosu yalnızca o dosya için geçerlidir — Örneğin, yalnızca belirli bir dosya `%(AdditionalIncludeDirectories)` için geçerli olan içerme dizinlerini belirtmek için öğesini kullanabilirsiniz. Bu tür bir öğe makrosu MSBuild içindeki bir `ItemGroup` meta veriye karşılık gelir. Bir proje yapılandırması bağlamında kullanıldığında, öğe makrosu belirli bir türdeki tüm dosyalar için geçerli olur. Örneğin, C/C++ **Önişlemci tanımları** yapılandırma özelliği, projedeki tüm. cpp `%(PreprocessorDefinitions)` dosyaları için geçerli olan bir öğe makrosunu alabilir. Bu tür bir öğe makrosu MSBuild içindeki bir `ItemDefinitionGroup` meta veriye karşılık gelir. Daha fazla bilgi için bkz. [öğe tanımları](/visualstudio/msbuild/item-definitions).

### <a name="user-defined-macros"></a>Kullanıcı tanımlı makrolar

Proje yapılarında değişken olarak kullanmak için *Kullanıcı tanımlı makrolar* oluşturabilirsiniz. Örneğin, bir özel yapı adımına veya özel yapı aracına değer sağlayan kullanıcı tanımlı bir makro oluşturabilirsiniz. Kullanıcı tanımlı makro bir ad/değer çiftidir. Bir proje dosyasında, değere erişmek için **$ (** <em>ad</em> **)** gösterimini kullanın.

Kullanıcı tanımlı makrolar bir özellik sayfasında depolanır. Projeniz zaten bir özellik sayfası içermiyorsa, [Visual Studio proje ayarlarını paylaşma veya yeniden kullanma](create-reusable-property-configurations.md)bölümündeki adımları izleyerek bir tane oluşturabilirsiniz.

#### <a name="to-create-a-user-defined-macro"></a>Kullanıcı tanımlı makro oluşturmak için

1. **Özellik Yöneticisi** penceresini açın. (Menü çubuğunda**Özellik Yöneticisi** **görüntüle** > ' yi seçin veya**diğer Windows** > **Özellik Yöneticisi** **görüntüleyin** > .) Bir özellik sayfası için kısayol menüsünü açın (adı. User ile biter) ve ardından **Özellikler**' i seçin. Bu özellik sayfası için **Özellik sayfaları** iletişim kutusu açılır.

1. İletişim kutusunun sol bölmesinde **Kullanıcı makroları**' nı seçin. Sağ bölmede, **makro Ekle** düğmesini seçerek **Kullanıcı makrosu Ekle** iletişim kutusunu açın.

1. İletişim kutusunda, makro için bir ad ve değer belirtin. İsteğe bağlı olarak, **Bu makroyu yapı ortamında bir ortam değişkeni olarak ayarla** onay kutusunu seçin.

## <a name="property_editor">Özellik Düzenleyicisi</a>

Belirli dize özelliklerini değiştirmek ve makroları değer olarak seçmek için Özellik Düzenleyicisi'ni kullanabilirsiniz. Özellik Düzenleyicisi'ne erişmek için, özellik sayfasında bir özellik seçin ve sonra sağdaki aşağı ok düğmesini seçin. Açılan listede  **\<Düzenle >** varsa, bu özellik için özellik düzenleyicisini göstermek üzere bu seçeneği belirleyebilirsiniz.

![Özellik&#95;Düzenleyicisi&#95;açılan kutusu](media/property_editor_dropdown.png "Property_Editor_Dropdown")

Özellik Düzenleyicisi 'nde, kullanılabilir makroları ve bunların geçerli değerlerini görüntülemek için **makrolar** düğmesini seçebilirsiniz. Aşağıdaki çizimde, **makrolar** düğmesi seçildikten sonra **ek Içerme dizinleri** özelliğinin Özellik Düzenleyicisi gösterilmektedir. **Üst veya proje varsayılanlarından devralma** onay kutusu seçildiğinde ve yeni bir değer eklediğinizde, o anda devralınmakta olan tüm değerlere eklenir. Onay kutusunun işaretini kaldırırsanız, yeni değeriniz devralınan değerlerin yerini alır. Çoğu durumda, onay kutusunu seçili bırakın.

![Özellik Düzenleyicisi, Visual C&#43; ](media/propertyeditorvc.png "Propertyeditorvc")

## <a name="add-an-include-directory-to-the-set-of-default-directories"></a>Varsayılan dizinler kümesine bir içerme dizini ekleyin

Bir projeye ekleme dizini eklediğinizde, tüm varsayılan dizinleri geçersiz kılmamak önemlidir. Dizin eklemenin doğru yolu, örneğin "C:\MyNewIncludeDir\"" gibi yeni yolu eklemek ve ardından **$ (IncludePath)** makrosunu özellik değerine eklemek içindir.

## <a name="quickly-browse-and-search-all-properties"></a>Tüm özelliklere hızla gözatıp arama

**Tüm seçenekler** Özellik sayfası ( **Özellik sayfaları** iletişim kutusundaki **yapılandırma &#124; özellikleri CC++ /** düğüm altında), geçerli bağlamda kullanılabilen özelliklere gözatmanız ve bunları aramanız için hızlı bir yol sağlar. Özel bir arama kutusu ve sonuçlara filtre uygulamanıza yardımcı olacak basit bir sözdizimi vardır:

Önek yok:<br/>
Yalnızca özellik adlarında arayın (büyük/küçük harf duyarsız alt dize).

'/' veya '-' :<br/>
Yalnızca derleyici anahtarlarında arayın (büyük/küçük harf duyarsız önek)

v:<br/>
Yalnızca değerlerde arayın (büyük/küçük harf duyarsız alt dize).

## <a name="set-environment-variables-for-a-build"></a>Yapı için ortam değişkenlerini ayarlama

MSVC derleyicisi (CL. exe) özellikle LıB, LıBPATH, PATH ve ıNCLUDE gibi belirli ortam değişkenlerini tanır. IDE ile derleme yaparken, bu ortam değişkenlerini ayarlamak için [VC + + dizinleri Özellik sayfası](reference/vcpp-directories-property-page.md) Özellik sayfasında ayarlanan özellikler kullanılır. LIB, LIBPATH ve INCLUDE değerleri zaten ayarlanmışsa (örneğin, bir Geliştirici Komutu İstemi ile), bunlar karşılık gelen MSBuild özelliklerinin değerleriyle değiştirilir. Yapı daha sonra, VC++ Dizinleri yürütülebilir dizinler özelliğinin değerini PATH öğesinin başına ekler. Kullanıcı tanımlı bir makro oluşturup **Bu makroyu yapı ortamında bir ortam değişkeni olarak ayarla**yazılı kutuyu işaretleyerek Kullanıcı tanımlı bir ortam değişkeni ayarlayabilirsiniz.

## <a name="set-environment-variables-for-a-debugging-session"></a>Hata ayıklama oturumu için ortam değişkenlerini ayarlama

Projenin **Özellik sayfaları** iletişim kutusunun sol bölmesinde **yapılandırma özellikleri** ' ni genişletin ve ardından **hata ayıklama**' yı seçin.

Sağ bölmede, **ortam** veya **birleştirme ortamı** proje ayarlarını değiştirin ve **Tamam** düğmesini seçin.

## <a name="in-this-section"></a>Bu bölümde

[Visual Studio projelerinin ayarlarını paylaşma veya yeniden kullanma](create-reusable-property-configurations.md)<br/>
Paylaşılabilecek veya yeniden kullanılabilecek özel yapı ayarları ile bir. props dosyası oluşturma.

[Proje özelliği devralma](project-property-inheritance.md)<br/>
Yapı işlemindeki. props,. targets,. vcxproj dosyaları ve ortam değişkenleri için değerlendirme sırasını açıklar.

[Proje dosyasını değiştirmeden özellikleri ve hedefleri değiştirme](modify-project-properties-without-changing-project-file.md)<br/>
Proje dosyasını değiştirmek zorunda kalmadan geçici derleme ayarları oluşturma. 

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio Projeleri - C++](creating-and-managing-visual-cpp-projects.md)<br/>
[.vcxproj ve .props dosya yapısı](reference/vcxproj-file-structure.md)<br/>
[Özellik sayfası XML dosyaları](reference/property-page-xml-files.md)<br/>

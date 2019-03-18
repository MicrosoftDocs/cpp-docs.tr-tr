---
title: C++ derleyicisi ayarlayın ve derleme Visual Studio özellikleri
description: Visual Studio IDE, C++ Derleyici ve bağlayıcı seçenekleri ve diğer derleme ayarlarını değiştirmek için kullanın.
ms.date: 12/10/2018
helpviewer_keywords:
- project properties [C++], modifying
- properties [C++]
- Visual C++ projects, properties
- projects [C++], properties
ms.assetid: 9b0d6f8b-7d4e-4e61-aa75-7d14944816cd
ms.openlocfilehash: 55adb6dc91919bda9c2827a89e5de536667085c1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824115"
---
# <a name="set-compiler-and-build-properties"></a>Derleyici ayarlayın ve derleme özellikleri

IDE'de bir proje oluşturmak için gereken tüm bilgileri olarak kullanıma sunulan *özellikleri*. Bu bilgiler, uygulama adı, (örneğin, DLL, LIB, EXE) uzantısı, derleyici seçenekleri, bağlayıcı seçenekleri, hata ayıklayıcı ayarları, özel derleme adımlarını ve diğer pek çok şey içerir. Genellikle, kullandığınız *özellik sayfaları* ( **proje &#124; özellikleri**) görüntüleyebilir ve bu özellikleri değiştirebilirsiniz. Özellik sayfaları erişmek için kendi seçtikleri **Proje > \<proje adı > Özellikleri** ana menü ya da'nde proje düğümüne sağ tıklayın **Çözüm Gezgini** ve **Özellikleri**.

## <a name="default-properties"></a>Varsayılan Özellikler

Bir proje oluşturduğunuzda, sistem çeşitli özellikleri için değerleri atar. Varsayılan değerleri türüne bağlı olarak biraz farklılık gösterir Uygulama Sihirbazı'nda proje ve hangi seçeneklerin seçin. Örneğin, bir ATL projesi MIDL dosyalarla ilgili özellikler var, ancak bunlar eksik bir temel bir konsol uygulamasında. Varsayılan özellikleri genel özellik sayfaları bölmesinde gösterilir:

![Visual C&#43; &#43; Proje Varsayılanları](media/visual-c---project-defaults.png "Visual C++ Proje Varsayılanları")

## <a name="applying-properties-to-build-configurations-and-target-platforms"></a>Yapı yapılandırmalarını ve Hedef platformlar için uygulama özellikleri

Uygulama adı gibi bazı özellikler tüm yapı farklılıkları, hedef platform veya hata ayıklama veya sürüm derleme olmasından bağımsız olarak geçerlidir. Ancak çoğu özellikleri yapılandırma bağımlıdır. Bu durum, programın çalışması üzerinde belirli platformdan ve doğru kodu oluşturmak için kullanmak için hangi belirli bir derleyici seçenekleri bilmek derleyici sahip olmasıdır. Bu nedenle, bir özelliği ayarlamak, hangi yapılandırma ve platform yeni değer uygulanmasını dikkat edilmesi gereken önemli. Yalnızca hata ayıklama Win32 derlemeler için uygulamanız gerekir veya hata ayıklama ARM için uygulamalıdır ve hata ayıklama x64? Örneğin, **iyileştirme** , varsayılan olarak ayarlanırsa **hızını en üst düzeye (/ O2)** sürüm yapılandırmasında, ancak hata ayıklama yapılandırmasında devre dışı.

Özellik sayfaları, her zaman görebilir ve gerekli değiştirirseniz, hangi yapılandırma ve platform bir özellik değeri uygulanacak şekilde tasarlanmıştır. Aşağıdaki çizim, üst listesi kutulara özellik sayfalarını yapılandırma ve platform bilgilerini gösterir. Zaman **iyileştirme** özelliği burada ayarlanmışsa, gerçekleşen etkin bir yapılandırma olmaya kırmızı oklarla gösterildiği gibi yalnızca hata ayıklama Win32 derlemelere uygulanır.

![Visual C&#43; &#43; özellik sayfaları gösteren etkin yapılandırma](media/visual-c---property-pages-showing-active-configuration.png "Visual C++ özellik sayfaları gösteren etkin yapılandırma")

Aynı proje özellik sayfası aşağıda gösterilmektedir, ancak sürüme yapılandırma değiştirildi. İyileştirme özelliği için farklı bir değer unutmayın. Ayrıca, etkin yapılandırma yine de hata ayıklama olduğunu unutmayın. Burada herhangi bir yapılandırma için özellikleri ayarlayabilirsiniz; etkin olması gerekmez.

![Visual C&#43; &#43; özellik sayfaları gösteren yayın yapılandırma](media/visual-c---property-pages-showing-release-config.png "Visual C++ özellik sayfaları gösteren yayın yapılandırma")

## <a name="target-platforms"></a>Hedef platformlar

*Hedef platform* cihaz ve/veya yürütülebilir dosyayı çalıştıracak bir işletim sistemi türünü ifade eder. Birden fazla platform için bir proje oluşturabilirsiniz. Proje türü üzerinde C++ projeleri için kullanılabilir hedef platformlara bağlıdır; içerir ancak sınırlı Win32, x64, ARM, Android ve iOS.     **X86** görebileceğiniz hedef platform **Configuration Manager** aynıdır **Win32** yerel C++ projelerinde. Win32 32-bit Windows anlamına gelir ve **x64** 64 bit Windows anlamına gelir. Bu iki platform hakkında daha fazla bilgi için bkz: [çalışan 32-bit uygulamaları](/windows/desktop/WinProg64/running-32-bit-applications).

**Herhangi bir CPU** hedef platform değeri, görebileceğiniz **Configuration Manager** yerel C++ projeleri;'üzerinde hiçbir etkisi C + için ilgili +/ CLI ve diğer .NET türleri proje. Daha fazla bilgi için [/CLRIMAGETYPE (CLR, türü görüntü belirtin)](reference/clrimagetype-specify-type-of-clr-image.md).


Hata ayıklama derlemesi için özellikleri ayarlama hakkında daha fazla bilgi için bkz:

- [C++ hata ayıklama yapılandırması proje ayarları](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration)
- [Hata Ayıklayıcısı Ayarları ve Hazırlığı](/visualstudio/debugger/debugger-settings-and-preparation)
- [Hata ayıklama hazırlığı: Visual C++ proje türleri](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)
- [Visual Studio hata ayıklayıcısında simge (.pdb) ve kaynak dosyaları belirtme](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger)

## <a name="c-compiler-and-linker-options"></a>C++ Derleyici ve bağlayıcı seçenekleri

C++ Derleyici ve bağlayıcı seçenekleri altında bulunur **C/C++** ve **bağlayıcı** düğümleri sol bölmede **yapılandırma özellikleri**. Bu, doğrudan için derleyici geçirilen komut satırı seçenekleri çevir. Belirli bir seçenek hakkında belgeleri okumak için Orta bölme ve ENTER tuşuna seçeneğini **F1**. Veya tüm seçenekleri için belgelere göz atabilirsiniz [MSVC derleyici seçenekleri](reference/compiler-options.md) ve [MSVC bağlayıcı seçenekleri](reference/linker-options.md). 

**Özellik sayfaları** iletişim kutusu yalnızca geçerli projeye ilgili özellik sayfalarını gösterir. Örneğin, projede bir .idl dosyası yoksa, MIDL özellik sayfası görüntülenmez. Her özellik sayfaları'ayarı hakkında daha fazla bilgi için bkz. [özellik sayfaları (C++)](reference/property-pages-visual-cpp.md). 

## <a name="directory-and-path-values"></a>Dizin ve yol değerleri

MSBuild derleme zamanı sabitleri belirli dize değerini dizinleri ve yolları dahil etmek için "makroları" adlı kullanımını destekler. Bu özellik sayfalarındaki başvurun ve bunları kullanarak değiştirme Burada sunulan [Özellik Düzenleyici](#property_editor). 

Bir Visual C++ projesinin özellik sayfaları aşağıdaki resimde gösterilmektedir. Sol bölmede, **VC ++ dizinleri** *kural* seçildiğinde ve sağ bölmede, bu kuralla ilişkili özellikleri listeler. `$(...)` Değerleri çağrılır *makroları*. A *makrosu* Visual Studio ya da MSBuild sistemi tarafından tanımlanan bir değer ya da kullanıcı tanımlı bir değer başvurabilirsiniz bir derleme zamanı sabit değeri. Dizin yolları gibi sabit kodlu değerler yerine makroları kullanarak, makineler arasında ve Visual Studio sürümleri arasında özellik ayarlarını daha kolay paylaşabilir ve proje ayarlarınızın doğru içinde rol daha iyi oynamasını sağlayabilirsiniz [ özellik devralma](project-property-inheritance.md). 

![Proje özellik sayfaları](media/project_property_pages_vc.png "Project_Property_Pages_VC")

Tüm kullanılabilir makroların değerlerini görüntülemek için özellik Düzenleyicisi'ni kullanabilirsiniz. Makrolar açıklanmıştır [özellik sayfası makroları](#bkmkPropertiesVersusMacros) bu makalenin devamındaki bölümüne.)

### <a name="predefined-macros"></a>Önceden tanımlanmış makrolar

*Genel makrolar*<br/>
Bir proje yapılandırmasındaki tüm öğelere uygulanır. Söz dizimine sahip `$(name)`. Genel makro, örneğidir `$(VCInstallDir)`, Visual Studio yüklemenizin kök dizinini depolayan. Genel makro karşılık gelen bir `PropertyGroup` MSBuild içinde.

*öğe makroları*<br/>
Söz dizimine sahip `%(name)`. Bir dosya için öğe makrosu yalnızca o dosya için geçerlidir. — Örneğin, kullanabileceğiniz `%(AdditionalIncludeDirectories)` belirtmek için yalnızca belirli bir dosya için geçerli dizinleri dahil et. Bu öğe makrosu türü için karşılık gelen bir `ItemGroup` msbuild'de meta verileri. Bir proje yapılandırması bağlamında kullanıldığında, öğe makrosu belirli bir türdeki tüm dosyalar için geçerli olur. Örneğin, C/C++ **önişlemci tanımları** Yapılandırma özelliği gerçekleştirebileceğiniz bir `%(PreprocessorDefinitions)` öğe makrosu, projedeki tüm .cpp dosyaları için geçerlidir. Bu öğe makrosu türü için karşılık gelen bir `ItemDefinitionGroup` msbuild'de meta verileri. Daha fazla bilgi için [öğesi tanımları](/visualstudio/msbuild/item-definitions).

### <a name="user-defined-macros"></a>Kullanıcı tanımlı makrolar

Oluşturabileceğiniz *kullanıcı tanımlı makrolar* proje yapılarında değişkenler olarak kullanılacak. Örneğin, bir özel yapı adımına veya özel yapı aracına değer sağlayan kullanıcı tanımlı bir makro oluşturabilirsiniz. Kullanıcı tanımlı makro bir ad/değer çiftidir. Bir proje dosyasında kullanmak **$(**<em>adı</em>**)** değere erişmek için bir gösterimi.

Kullanıcı tanımlı makrolar bir özellik sayfasında depolanır. Projenize bir özellik sayfası içermiyorsa altındaki adımları izleyerek bir tane oluşturabilirsiniz [paylaşımı veya resuse Visual Studio C++ proje ayarlarını](#bkmkPropertySheets).

#### <a name="to-create-a-user-defined-macro"></a>Kullanıcı tanımlı makro oluşturmak için

1. İçinde **özellik Yöneticisi** penceresinde (menü çubuğunda, **görünümü**, **özellik Yöneticisi**), bir özellik sayfası (adı .user ile biter) için kısayol menüsünü açın ve ardından Özellikleri. **Özellik sayfaları** bu özellik sayfası iletişim kutusu açılır.

1. İletişim kutusunun sol bölmesinde seçin **kullanıcı makroları**. Sağ bölmede seçin **makro Ekle** açmak için düğmeyi **kullanıcı makrosu Ekle** iletişim kutusu.

1. İletişim kutusunda, makro için bir ad ve değer belirtin. İsteğe bağlı olarak **Bu makroyu yapı ortamında bir ortam değişkeni olarak ayarla** onay kutusu.

## <a name="property_editor">Özellik Düzenleyicisi</a>

Belirli dize özelliklerini değiştirmek ve makroları değer olarak seçmek için Özellik Düzenleyicisi'ni kullanabilirsiniz. Özellik Düzenleyicisi'ne erişmek için, özellik sayfasında bir özellik seçin ve sonra sağdaki aşağı ok düğmesini seçin. Aşağı açılan listede varsa  **\<Düzenle >**, bu özellik için özellik Düzenleyicisi'ni görüntülemek için seçin.

![Özellik&#95;Düzenleyicisi&#95;açılan](media/property_editor_dropdown.png "Property_Editor_Dropdown")

Özellik Düzenleyicisi'nde seçtiğiniz **makroları** uygun makroları ve geçerli değerlerini görüntülemek için düğme. Özellik Düzenleyicisi için aşağıdaki çizimde **ek içerik dizinleri** sonra özellik **makroları** düğmesi seçildikten. Zaman **üstten veya proje varsayılanlarından devral** onay kutusu seçildiğinde ve yeni bir değer eklediğinizde, devralınmakta olan tüm değerlere eklenir. Onay kutusunun işaretini kaldırırsanız, yeni değeriniz devralınan değerlerin yerini alır. Çoğu durumda, onay kutusunu seçili bırakın.

![Özellik Düzenleyicisi, Visual C&#43;&#43;](media/propertyeditorvc.png "PropertyEditorVC")

## <a name="add-an-include-directory-to-the-set-of-default-directories"></a>Varsayılan dizinler kümesine bir ekleme dizini ekleme

Bir projeye ekleme dizini eklediğinizde, tüm varsayılan dizinleri geçersiz kılmamak önemlidir. Örneğin yeni yolu sona eklenecek bir dizin eklemenin doğru yolu olan "C:\MyNewIncludeDir\"ve sonra **$(ıncludepath)** makrosunu özellik değerinin.

## <a name="quickly-browse-and-search-all-properties"></a>Hızlıca göz atmak ve tüm özelliklerini arayın

**Tüm seçenekleri** özellik sayfası (altında **yapılandırma özellikleri &#124; C/C++** düğümünde **özellik sayfaları** iletişim kutusu) göz atmak ve aramak için hızlı bir yol sağlar. Geçerli bağlamda kullanılabilen özellikleri. Özel bir arama kutusu ve sonuçlara filtre uygulamanıza yardımcı olacak basit bir sözdizimi vardır:

Önek yok:<br/>
Yalnızca özellik adlarında arayın (büyük/küçük harf duyarsız alt dize).

'/' veya '-' :<br/>
Yalnızca derleyici anahtarlarında arayın (büyük/küçük harf duyarsız önek)

v:<br/>
Yalnızca değerlerde arayın (büyük/küçük harf duyarsız alt dize).

## <a name="set-environment-variables-for-a-build"></a>Bir yapı için ortam değişkenlerini ayarlama

MSVC derleyicisi (cl.exe) özellikle LIB, LIBPATH, PATH ve INCLUDE belirli ortam değişkenlerini tanır. Ayarlanan özellikler IDE ile yapı kurarken [VC ++ Directories Property Page](reference/vcpp-directories-property-page.md) özellik sayfası, bu ortam değişkenlerini ayarlamak için kullanılır. LIB, LIBPATH ve INCLUDE değerleri zaten ayarlanmışsa (örneğin, bir Geliştirici Komutu İstemi ile), bunlar karşılık gelen MSBuild özelliklerinin değerleriyle değiştirilir. Yapı daha sonra, VC++ Dizinleri yürütülebilir dizinler özelliğinin değerini PATH öğesinin başına ekler. Bir kullanıcı tarafından tanımlanan ortam değişkeni a ve ardından ifadesini içeren kutuyu işaretleyerek kullanıcı tanımlı bir makro ayarlayabilirsiniz **Bu makroyu yapı ortamında bir ortam değişkeni olarak ayarla**.

## <a name="set-environment-variables-for-a-debugging-session"></a>Hata ayıklama oturumu için ortam değişkenlerini ayarlama

Sol bölmede projelerin **özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri** seçip **hata ayıklama**.

Sağ bölmede değişiklik **ortam** veya **ortamı Birleştir** proje ayarları ve ardından **Tamam** düğmesi.

## <a name="in-this-section"></a>Bu bölümde

[Paylaşımı veya resuse Visual Studio Proje ayarları](create-reusable-property-configurations.md)<br/>
Nasıl paylaşılabilir özel yapı ayarları veya resused .props dosyası oluşturun.

[Proje özellik devralma](project-property-inheritance.md)<br/>
.Props .targets, .vcxproj dosyaları ve yapı işleminde ortam değişkenlerini Değerlendirme sırasını tanımlar.

[Özellikler ve hedefler proje dosyası değiştirmeden](modify-project-properties-without-changing-project-file.md)<br/>
Bir proje dosyasını değiştirmek zorunda kalmadan geçici derleme ayarlarının nasılş oluşturulacağı. 

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio projeleri - C++](creating-and-managing-visual-cpp-projects.md)<br/>
[.vcxproj ve .props dosya yapısı](reference/vcxproj-file-structure.md)<br/>
[Özellik sayfası XML dosyaları](reference/property-page-xml-files.md)<br/>

---
title: Working with Project Properties | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- project properties [C++], modifying
- properties [C++]
- Visual C++ projects, properties
- projects [C++], properties
ms.assetid: 9b0d6f8b-7d4e-4e61-aa75-7d14944816cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9961eaa6529773e8d21d9c953242d1656a6a443
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211669"
---
# <a name="working-with-project-properties"></a>Proje Özellikleriyle Çalışma

IDE'de bir proje oluşturmak için gereken tüm bilgileri olarak kullanıma sunulan *özellikleri*. Bu bilgiler, uygulama adı, (örneğin, DLL, LIB, EXE) uzantısı, derleyici seçenekleri, bağlayıcı seçenekleri, hata ayıklayıcı ayarları, özel derleme adımlarını ve diğer pek çok şey içerir. Genellikle, kullandığınız *özellik sayfaları* ( **proje &#124; özellikleri**) görüntüleyebilir ve bu özellikleri değiştirebilirsiniz.

Bir proje oluşturduğunuzda, sistem çeşitli özellikleri için değerleri atar. Varsayılan değerleri türüne bağlı olarak biraz farklılık gösterir Uygulama Sihirbazı'nda proje ve hangi seçeneklerin seçin. Örneğin, bir ATL projesi MIDL dosyalarla ilgili özellikler var, ancak bunlar eksik bir temel bir konsol uygulamasında. Varsayılan özellikleri genel özellik sayfaları bölmesinde gösterilir:

![Visual C&#43; &#43; Proje Varsayılanları](../ide/media/visual-c---project-defaults.png "Visual C++ Proje Varsayılanları")

Uygulama adı gibi bazı özellikler tüm yapı farklılıkları, hedef platform veya hata ayıklama veya sürüm derleme olmasından bağımsız olarak geçerlidir. Ancak çoğu özellikleri yapılandırma bağımlıdır. Bu durum, programın çalışması üzerinde belirli platformdan ve doğru kodu oluşturmak için kullanmak için hangi belirli bir derleyici seçenekleri bilmek derleyici sahip olmasıdır. Bu nedenle, bir özelliği ayarlamak, hangi yapılandırma ve platform yeni değer uygulanmasını dikkat edilmesi gereken önemli. Yalnızca hata ayıklama Win32 derlemeler için uygulamanız gerekir veya hata ayıklama ARM için uygulamalıdır ve hata ayıklama x64? Örneğin, **iyileştirme** , varsayılan olarak ayarlanırsa **hızını en üst düzeye (/ O2)** sürüm yapılandırmasında, ancak hata ayıklama yapılandırmasında devre dışı.

Özellik sayfaları, her zaman görebilir ve gerekli değiştirirseniz, hangi yapılandırma ve platform bir özellik değeri uygulanacak şekilde tasarlanmıştır. Aşağıdaki çizim, üst listesi kutulara özellik sayfalarını yapılandırma ve platform bilgilerini gösterir. Zaman **iyileştirme** özelliği burada ayarlanmışsa, gerçekleşen etkin bir yapılandırma olmaya kırmızı oklarla gösterildiği gibi yalnızca hata ayıklama Win32 derlemelere uygulanır.

![Visual C&#43; &#43; özellik sayfaları gösteren etkin yapılandırma](../ide/media/visual-c---property-pages-showing-active-configuration.png "Visual C++ özellik sayfaları gösteren etkin yapılandırma")

Aynı proje özellik sayfası aşağıda gösterilmektedir, ancak sürüme yapılandırma değiştirildi. İyileştirme özelliği için farklı bir değer unutmayın. Ayrıca, etkin yapılandırma yine de hata ayıklama olduğunu unutmayın. Burada herhangi bir yapılandırma için özellikleri ayarlayabilirsiniz; etkin olması gerekmez.

![Visual C&#43; &#43; özellik sayfaları gösteren yayın yapılandırma](../ide/media/visual-c---property-pages-showing-release-config.png "Visual C++ özellik sayfaları gösteren yayın yapılandırma")

Proje sistemi dosya biçimlerini ve projeleri oluşturmak için kurallar tanımlar Msbuild'i temel alır. MSBuild çoklu yapılandırmalar ve platformlar için oluşturma karmaşıklığını çoğunu yönetir ancak biraz nasıl çalıştığı konusunda anlaşılması gerekir. Özel yapılandırmalar tanımlayın veya yeniden kullanılabilir özellik kümeleri paylaşmak ve birden çok projelerine içeri oluşturmak istiyorsanız bu özellikle önemlidir.

Proje özellikleri, proje dosyası (*.vcxproj) içinde doğrudan ya da proje dosyası içeri aktarmalar ve hangi varsayılan değerler sağlamanız diğer .xml veya .props dosyalarında depolanır. Daha önce gösterildiği gibi aynı özelliği olan aynı yapılandırmanın farklı dosyalar farklı bir değer atanabilir. Bir proje oluşturduğunuzda, MSBuild altyapısına proje dosyası ve içeri aktarılan tüm dosyaları (aşağıda açıklanmıştır) iyi tanımlanmış bir sırayla değerlendirir. Her dosya değerlendirilir gibi bu dosyada tanımlanan tüm özellik değerlerini mevcut değerler geçersiz kılınır. Belirtilmeyen herhangi bir değeri, daha önce değerlendirilen dosyalarından devralınır. Özellik sayfaları ile bir özelliğini ayarladığınızda, bu nedenle, aynı zamanda için ayarladığınız yere dikkat etmeniz önemlidir. Bir .props dosyası içinde "X" bir özelliği ayarlamak, ancak özelliği proje dosyasında "Y" olarak ayarlanmış, "Y" özelliği ile proje oluşturacaksınız. Aynı özellik bir .cpp dosyası gibi bir proje öğesi "Z" olarak ayarlanır, MSBuild altyapısına "Z" değerini kullanın. Daha fazla bilgi için [özellik devralma](#bkmkPropertyInheritance) bu makalenin ilerleyen bölümlerinde.

## <a name="build-configurations"></a>Derleme yapılandırmaları

Bir yapılandırma yalnızca bir rastgele bir ad verilir özellikleri grubudur. Visual Studio hata ayıklama ve yayın yapılandırmaları sağlar ve her bir hata ayıklama derlemesi veya yayın yapısı için uygun şekilde çeşitli özelliklerini ayarlar. Kullanabileceğiniz **Configuration Manager** özel yapılandırmaları derleme belirli bir özellik için Grup Özellikleri için kullanışlı bir yol tanımlamak için. Özellik Yöneticisi özellikleri ile Gelişmiş iş için kullanılır, ancak özellik yapılandırmalarını görselleştirmenize yardımcı olur çünkü biz bunu burada tanıtır. Buradan erişim **görünümü &#124; özellik Yöneticisi** veya **görünümü &#124; diğer Windows &#124; özellik Yöneticisi** ayarlarınıza bağlı olarak. Bu projede düğümleri her yapılandırma/platform çifti için vardır. Her biri bu düğümler altında özellik sayfaları (.props dosyaları) Bu yapılandırma için bazı belirli özellikleri ayarlamak için düğümlerdir.

![Özellik Yöneticisi](../ide/media/property-manager.png "özellik Yöneticisi")

Genel özellik sayfaları (bkz. Yukarıdaki çizimde) bölmesine gidin "Ayarlı değil" yerine "Kullanımı Unicode" için karakter kümesi özelliğini ve'a tıklayın, **Tamam**, özellik Yöneticisi gösterir hiçbir **Unicodedesteği** özellik sayfası için geçerli yapılandırma, ancak yine de olacaktır var. diğer yapılandırmalar için.

Özellik Yöneticisi ve özellik sayfaları hakkında daha fazla bilgi için bkz: [yeniden kullanılabilir özellik yapılandırmalarını oluşturma](#bkmkPropertySheets) bu makalenin ilerleyen bölümlerinde.

> [!TIP]
> .User dosyasını eski bir özelliktir ve doğru şekilde yapılandırma/platform göre gruplandırılmış bir özellikler tutulabilmesi için sildiğini öneririz.

## <a name="target-platforms"></a>Hedef platformlar

*Hedef platform* cihaz ve/veya yürütülebilir dosyayı çalıştıracak bir işletim sistemi türünü ifade eder. Birden fazla platform için bir proje oluşturabilirsiniz. Proje türü üzerinde C++ projeleri için kullanılabilir hedef platformlara bağlıdır; içerir ancak sınırlı Win32, x64, ARM, Android ve iOS.     **X86** görebileceğiniz hedef platform **Configuration Manager** aynıdır **Win32** yerel C++ projelerinde. Win32 32-bit Windows anlamına gelir ve **x64** 64 bit Windows anlamına gelir. Bu iki platform hakkında daha fazla bilgi için bkz: [çalışan 32-bit uygulamaları](/windows/desktop/WinProg64/running-32-bit-applications).

**Herhangi bir CPU** hedef platform değeri, görebileceğiniz **Configuration Manager** yerel C++ projeleri;'üzerinde hiçbir etkisi C + için ilgili +/ CLI ve diğer .NET türleri proje. Daha fazla bilgi için [/CLRIMAGETYPE (CLR, türü görüntü belirtin)](../build/reference/clrimagetype-specify-type-of-clr-image.md).

## <a name="property-pages"></a>Özellik sayfaları

Daha önce belirtildiği gibi Visual C++ proje sistemi dayanır [MSBuild](/visualstudio/msbuild/msbuild-properties) ve değerleri depolanır .props ve .targets dosyaları XML proje dosyasında varsayılan. Visual Studio 2015 için bu dosyalar bulunur **\Program dosyaları (x86)\MSBuild\Microsoft.Cpp\v4.0\V140**. Bu dosyalar bulunan Visual Studio 2017 için  **\\Program dosyaları (x86)\\Microsoft Visual Studio\\2017\\_edition_\\Common7\\ IDE\\VC\\VCTargets**burada _edition_ olan Visual Studio sürümü yüklü. Özellikleri, ayrıca kendi projenize ekleyebilirsiniz. herhangi özel .props dosyalarında depolanır. OLMAYAN dosyaları el ile düzenlemeniz ve bunun yerine özellik sayfaları IDE'de, özellikle de MSBuild çok iyi bir anlayışa sahip olduğunuz sürece, Devralmada rol oynayan tüm özelliklerini değiştirmek için kullanmanızı öneririz.

Bir Visual C++ projesinin özellik sayfaları aşağıdaki resimde gösterilmektedir. Sol bölmede, **VC ++ dizinleri** *kural* seçildiğinde ve sağ bölmede, bu kuralla ilişkili özellikleri listeler. `$(...)` Değerleri ne yazık ki adlı *makroları*. Bunlar *değil* C/C++ makroları ancak yalnızca derleme zamanı sabitler. Makrolar açıklanmıştır [özellik sayfası makroları](#bkmkPropertiesVersusMacros) bu makalenin devamındaki bölümüne.)

![Proje özellik sayfaları](../ide/media/project_property_pages_vc.png "Project_Property_Pages_VC")

> [!WARNING]
> **Ortak özellikler** yapılandırmaları Visual Studio'nun önceki sürümlerinde kaldırılmıştır. Bir projeye bir başvuru eklemek için artık kullandığınız **Başvuru Ekle** iletişim kutusunda yönetilen diller olduğu gibi. Bkz: [bir projedeki başvuruları yönetme](/visualstudio/ide/managing-references-in-a-project).

#### <a name="to-set-a-property-for-a-project"></a>Projeye ilişkin bir özelliği ayarlamak için

1. Çoğu senaryo için proje düzeyinde bir özel özellik sayfası oluşturulmadan özellikleri ayarlayabilirsiniz. Ana menüsünde **proje &#124; özellikleri**, veya'nde proje düğümüne sağ **Çözüm Gezgini** ve **özellikleri**.

2. Kullanım **yapılandırma** ve **Platform** liste kutularından özelliği grupları değişikliklerinizi uygulanacağını belirtin iletişim kutusunun üst kısmındaki. Çoğu durumda **tüm platformlar** ve **yapılandırmalarında** doğru seçimdir. Çoklu Seçim yalnızca bazı yapılandırmalar için özellikleri ayarlamak için bunları **özellik Yöneticisi**ve ardından kısayol menüsünü açın ve seçin **özellikleri**.

**Özellik sayfaları** iletişim kutusu yalnızca geçerli projeye uygulanan özellik sayfalarını gösterir. Örneğin, projede bir .idl dosyası yoksa, MIDL özellik sayfası görüntülenmez.

Özellik sayfası özelliğinde vurguladığınızda basabilirsiniz **F1** karşılık gelen derleyici veya bağlayıcı anahtarı hakkında daha fazla bilgi için başvuru konusu gidin.

Bu konu başlıklarında tüm özellik sayfalarını hakkında daha fazla bilgi bulabilirsiniz:

- [Genel Özellik Sayfası (Proje)](../ide/general-property-page-project.md)

- [Genel Özellik Sayfası (Dosya)](../ide/general-property-page-file.md)

- [Komut Satırı özellik sayfaları](../ide/command-line-property-pages.md)

- [C++ Hata Ayıklama Yapılandırması Proje Ayarları](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration)

- [NMake özellik sayfası](../ide/nmake-property-page.md)

- [Bağlayıcı Özellik Sayfaları](../ide/linker-property-pages.md)

- [Kaynaklar Özellik Sayfaları](../ide/resources-property-pages.md)

- [MIDL Özellik Sayfaları](../ide/midl-property-pages.md)

- [Web Başvuruları Özellik Sayfası](../ide/web-references-property-page.md)

- [XML Verileri Oluşturma Aracı özellik sayfası](../ide/xml-data-generator-tool-property-page.md)

## <a name="to-quickly-browse-and-search-all-properties"></a>Hızlıca göz atmak ve tüm özellikleri aramak için

**Tüm seçenekleri** özellik sayfası (altında **yapılandırma özellikleri &#124; C/C++** düğümünde **özellik sayfaları** iletişim kutusu) göz atmak ve aramak için hızlı bir yol sağlar. Geçerli bağlamda kullanılabilen özellikleri. Özel bir arama kutusu ve sonuçlara filtre uygulamanıza yardımcı olacak basit bir sözdizimi vardır:

Önek yok:<br/>
Yalnızca özellik adlarında arayın (büyük/küçük harf duyarsız alt dize).

'/' veya '-' :<br/>
Yalnızca derleyici anahtarlarında arayın (büyük/küçük harf duyarsız önek)

v:<br/>
Yalnızca değerlerde arayın (büyük/küçük harf duyarsız alt dize).

##  <a name="bkmkPropertiesVersusMacros"></a> Özellik sayfası makroları

A *makrosu* Visual Studio ya da MSBuild sistemi tarafından tanımlanan bir değer ya da kullanıcı tanımlı bir değer başvurabilirsiniz bir derleme zamanı sabit değeri. Dizin yolları gibi sabit kodlu değerler yerine makroları kullanarak, makineler arasında ve Visual Studio sürümleri arasında özellik ayarlarını daha kolay paylaşabilir ve proje ayarlarınızın özellik devralmada doğru şekilde rol oynamasını sağlayabilirsiniz. Tüm kullanılabilir makroların değerlerini görüntülemek için özellik Düzenleyicisi'ni kullanabilirsiniz.

### <a name="predefined-macros"></a>Önceden tanımlanmış makrolar

*Genel makrolar*<br/>
Bir proje yapılandırmasındaki tüm öğelere uygulanır. Söz dizimine sahip `$(name)`. Genel makro, örneğidir `$(VCInstallDir)`, Visual Studio yüklemenizin kök dizinini depolayan. Genel makro karşılık gelen bir `PropertyGroup` MSBuild içinde.

*öğe makroları*<br/>
Söz dizimine sahip `%(name)`. Bir dosya için öğe makrosu yalnızca o dosya için geçerlidir. — Örneğin, kullanabileceğiniz `%(AdditionalIncludeDirectories)` belirtmek için yalnızca belirli bir dosya için geçerli dizinleri dahil et. Bu öğe makrosu türü için karşılık gelen bir `ItemGroup` msbuild'de meta verileri. Bir proje yapılandırması bağlamında kullanıldığında, öğe makrosu belirli bir türdeki tüm dosyalar için geçerli olur. Örneğin, C/C++ **önişlemci tanımları** Yapılandırma özelliği gerçekleştirebileceğiniz bir `%(PreprocessorDefinitions)` öğe makrosu, projedeki tüm .cpp dosyaları için geçerlidir. Bu öğe makrosu türü için karşılık gelen bir `ItemDefinitionGroup` msbuild'de meta verileri. Daha fazla bilgi için [öğesi tanımları](/visualstudio/msbuild/item-definitions).

### <a name="user-defined-macros"></a>Kullanıcı tanımlı makrolar

Oluşturabileceğiniz *kullanıcı tanımlı makrolar* proje yapılarında değişkenler olarak kullanılacak. Örneğin, bir özel yapı adımına veya özel yapı aracına değer sağlayan kullanıcı tanımlı bir makro oluşturabilirsiniz. Kullanıcı tanımlı makro bir ad/değer çiftidir. Bir proje dosyasında kullanmak **$(**<em>adı</em>**)** değere erişmek için bir gösterimi.

Kullanıcı tanımlı makrolar bir özellik sayfasında depolanır. Projenize bir özellik sayfası içermiyorsa altındaki adımları izleyerek bir tane oluşturabilirsiniz [yeniden kullanılabilir özellik yapılandırmalarını oluşturma](#bkmkPropertySheets).

##### <a name="to-create-a-user-defined-macro"></a>Kullanıcı tanımlı makro oluşturmak için

1.  İçinde **özellik Yöneticisi** penceresinde (menü çubuğunda, **görünümü**, **özellik Yöneticisi**), bir özellik sayfası (adı .user ile biter) için kısayol menüsünü açın ve ardından Özellikleri. **Özellik sayfaları** bu özellik sayfası iletişim kutusu açılır.

2.  İletişim kutusunun sol bölmesinde seçin **kullanıcı makroları**. Sağ bölmede seçin **makro Ekle** açmak için düğmeyi **kullanıcı makrosu Ekle** iletişim kutusu.

3.  İletişim kutusunda, makro için bir ad ve değer belirtin. İsteğe bağlı olarak **Bu makroyu yapı ortamında bir ortam değişkeni olarak ayarla** onay kutusu.

## <a name="property-editor"></a>Özellik Düzenleyicisi

Belirli dize özelliklerini değiştirmek ve makroları değer olarak seçmek için Özellik Düzenleyicisi'ni kullanabilirsiniz. Özellik Düzenleyicisi'ne erişmek için, özellik sayfasında bir özellik seçin ve sonra sağdaki aşağı ok düğmesini seçin. Aşağı açılan listede varsa  **\<Düzenle >**, bu özellik için özellik Düzenleyicisi'ni görüntülemek için seçin.

![Özellik&#95;Düzenleyicisi&#95;açılan](../ide/media/property_editor_dropdown.png "Property_Editor_Dropdown")

Özellik Düzenleyicisi'nde seçtiğiniz **makroları** uygun makroları ve geçerli değerlerini görüntülemek için düğme. Özellik Düzenleyicisi için aşağıdaki çizimde **ek içerik dizinleri** sonra özellik **makroları** düğmesi seçildikten. Zaman **üstten veya proje varsayılanlarından devral** onay kutusu seçildiğinde ve yeni bir değer eklediğinizde, devralınmakta olan tüm değerlere eklenir. Onay kutusunun işaretini kaldırırsanız, yeni değeriniz devralınan değerlerin yerini alır. Çoğu durumda, onay kutusunu seçili bırakın.

![Özellik Düzenleyicisi, Visual C&#43;&#43;](../ide/media/propertyeditorvc.png "PropertyEditorVC")

##  <a name="bkmkPropertySheets"></a> Yeniden kullanılabilir özellik yapılandırmalarını oluşturma

Kullanıcı başına ve bilgisayar başına esasına göre "genel" özellikleri ayarlayabilseniz de, artık bunu yapmanızı önermiyoruz. Bunun yerine kullanmanızı öneriyoruz **özellik Yöneticisi** oluşturmak için bir *özellik sayfası* her tür yeniden kullanabilir veya diğer kişilerle paylaşmak mümkün olmasını istediğiniz proje ayarlarını depolamak için. Özellik sayfaları, diğer proje türleri için özellik ayarlarının yanlışlıkla değiştirilmesi olasılığını da azaltır. Özellik sayfaları daha ayrıntılı olarak ele alınmıştır [yeniden kullanılabilir özellik yapılandırmalarını oluşturma](#bkmkPropertySheets).

> [!IMPORTANT]
> **.user dosyaları ve sorunlu olmalarının**
>
> Visual Studio'nun önceki sürümlerinde, .kullanıcı dosya adı uzantısı ve bulunan genel özellik sayfalarını kullanılan \<kullanıcı profili > \AppData\Local\Microsoft\MSBuild\v4.0\ klasör. Bu dosyalar, proje yapılandırmalarına ilişkin özellikleri kullanıcı başına ve bilgisayar başına temelinde ayarladığından artık bu dosyaları önermiyoruz. Bu tür "genel" ayarlar, özellikle de yapı bilgisayarınızda birden fazla platformu hedef aldığınızda yapıları engelleyebilir. Örneğin, hem MFC projeniz hem de Windows Phone projeniz varsa, .user özellikleri bunlardan biri için geçersiz olur. Yeniden kullanılabilir özellik sayfaları daha esnek ve daha güçlüdür.
>
> .user dosyaları halen Visual Studio tarafından yüklenmesine ve özellik devralımında rol oynamasına karşın, bu dosyalar varsayılan olarak boştur. En iyi nde bunların başvurusunu silmektir **özellik Yöneticisi** projelerinizin kullanıcıya bağımsız olarak çalıştığından emin olmak için bilgisayar başına ayarları bu bir SCC (kaynak kodu, doğru davranışı sağlamak açısından önemlidir Ortam Denetimi).

Görüntülenecek **özellik Yöneticisi**, menü çubuğunda, **görünümü**, **diğer Windows**, **özellik Yöneticisi**.

Birden çok projeye uygulamak istediğiniz özellikleri ortak ve sık kullanılan bir dizi varsa, kullanabileceğiniz **özellik Yöneticisi** yeniden kullanılabilir Yakalanacak *özellik sayfası* olan kural olarak, dosya bir .props dosya adı uzantısı. Özelliklerini sıfırdan ayarlamanıza gerek kalmaması için sayfayı (veya sayfaları) yeni projelere uygulayabilirsiniz. Erişim için **özellik Yöneticisi**, menü çubuğunda, **görünümü**, **özellik Yöneticisi**.

![Özellik Yöneticisi kısayol menüsünü](../ide/media/sharingnew.png "SharingNew")

Her yapılandırma düğümü altında bu yapılandırma için uygulanan her bir özellik sayfası için düğümleri görürsünüz. Sistem projesi oluşturduğunuzda, Uygulama Sihirbazı'nda belirlediğiniz seçeneklere dayanan bir değerler kümesi özellik sayfaları ekler. Herhangi bir düğüme sağ tıklayın ve bu düğüme uygulanan özellikleri görmek için Özellikler'i seçin. Tüm özellik sayfalarının projenin "ana" özellik sayfası (ms.cpp.props) otomatik olarak içeri aktarılır ve özellik Yöneticisi'nde göründükleri sırayla değerlendirilir. Değerlendirme sırasını değiştirmek için bunları taşıyabilirsiniz. Daha sonra hesaplanan özellik sayfalarını sayfalarda daha önce hesaplanan değerler geçersiz kılınır.

Seçerseniz **yeni proje özelliği Sayfası Ekle** ve seçin, örneğin, MyProps.props özellik sayfasını, bir özellik sayfası iletişim kutusu görünür. Bunun MyProps özellik sayfası için geçerli olduğuna dikkat edin; yaptığınız herhangi bir değişiklik proje dosyasına (.vcxproj) değil de sayfaya yazılır.

Aynı özellik doğrudan .vcxproj dosyasında ayarlanmışsa, özellik sayfasındaki özellikler geçersiz kılınır.

Bir özellik sayfasını gerektiği sıklıkta içeri aktarabilirsiniz. Bir çözümdeki birden çok proje, aynı özellik sayfasından ayarları devralabilir ve bir projenin birden fazla sayfası olabilir. Özellik sayfasının kendisi, başka bir özellik sayfasından ayarları devralabilir.

Birden çok yapılandırma için tek bir özellik sayfası da oluşturabilirsiniz. Bunu yapmak için her bir yapılandırma için bir özellik sayfası oluşturun, bunlardan biri için kısayol menüsünü açın, seçin **varolan özellik sayfası Ekle**ve ardından diğer sayfaları ekleyin. Ancak, tek bir ortak özellik sayfası kullanırsanız, ayarladığınız bir özelliğin sayfanın geçerli olduğu tüm yapılandırmalar için ayarlandığını ve IDE'nin, belirli bir özellik sayfasından hangi projelerin veya diğer özellik sayfalarının devraldığını göstermediğini unutmayın.

Birçok projesi olacak büyük çözümlerde, çözüm düzeyinde bir özellik sayfası oluşturulması yararlı olabilir. Çözüme bir proje eklediğinizde, kullanın **özellik Yöneticisi** o özellik sayfasını projeye eklemek için. Proje düzeyinde gerek duyulursa, projeye özgü değerleri ayarlamak için yeni bir özellik sayfası ekleyebilirsiniz.

> [!IMPORTANT]
> .props dosyası bir proje öğesi olarak oluşturulmadığından, varsayılan olarak kaynak denetiminde yer almaz. Dosyayı kaynak denetimine dahil etmek istiyorsanız bir çözüm öğesi olarak el ile ekleyebilirsiniz.

#### <a name="to-create-a-property-sheet"></a>Bir özellik sayfası oluşturmak için

1. Menü çubuğunda, **görünümü**, **özellik Yöneticisi**. **Özellik Yöneticisi** açılır.

2. Özellik sayfasının kapsamını tanımlamak için, geçerli olduğu öğeyi seçin. Bu, belirli bir yapılandırma veya başka bir özellik sayfası olabilir. Bu öğe için kısayol menüsünü açın ve ardından **yeni proje özelliği Sayfası Ekle**. Bir ad ve konum belirtin.

3. İçinde **özellik Yöneticisi**, yeni özellik sayfasını açın ve sonra eklemek istediğiniz özellikleri ayarlayın.

##  <a name="bkmkPropertyInheritance"></a> Özellik devralma

Proje özellikleri katmanlıdır. Her katman önceki katmanın değerlerini devralır, ancak özelliğin açıkça ayarlanması devralınan değeri geçersiz kılabilir. Temel devralma ağacı şöyledir:

1. MSBuild CPP Araç Takımı'ndaki varsayılan ayarlar (.vcxproj dosyası tarafından içeri aktarılan ..\Program Files\MSBuild\Microsoft.Cpp\v4.0\Microsoft.Cpp.Default.props.)

2. Özellik sayfaları

3. .vcxproj dosyası (Varsayılan ve özellik sayfası ayarlarını geçersiz kılabilir.)

4. Öğelere ait meta veriler

> [!TIP]
> Özellik sayfasında, bir özelliği `bold` geçerli bağlamda tanımlanır. Normal yazı tipindeki özellik devralınan özelliktir.

Proje dosyası (.vcxproj), yapı zamanında diğer özellik sayfalarını içeri aktarır. Tüm özellik sayfaları içeri aktarıldıktan sonra proje dosyası değerlendirilir ve herhangi bir özellik değerinin son tanımı kullanılan tanım olur. Bazen, belirli bir özellik değerinin nasıl devralındığını belirlemek için genişletilmiş dosyayı görüntülemek yararlıdır. Genişletilmiş sürümü görüntülemek için, Visual Studio komut isteminde aşağıdaki komutu girin. (Yer tutucu dosya adlarını, kullanmak istediğiniz dosya adlarıyla değiştirin.)

**MSBuild /pp:** *temp* **.txt** *myapp* **.vcxproj**

MSBuild'i iyi bilmiyorsanız, genişletilmiş proje dosyaları büyük ve anlaşılması zor olabilir. Bir proje dosyasının temel yapısı şöyledir:

1. IDE'de gösterilmeyen temel proje özellikleri.

2. Araç takımından bağımsız bazı temel özellikleri tanımlayan Microsoft.cpp.default.props öğesinin içeri aktarımı.

3. Genel yapılandırma özellikleri (olarak gösterilen **PlatformToolset** ve **proje** varsayılan özellikleri **yapılandırma genel** sayfası. Bu özellikler, sonraki adımda hangi araç takımının ve iç özellik sayfalarının Microsoft.cpp.props öğesine aktarılacağını belirler.

4. Çoğu proje varsayılanını ayarlayan Microsoft.cpp.props öğesinin içeri aktarımı.

5. .user dosyaları da dahil olmak üzere tüm özellik sayfalarının içeri aktarımı. Bu özellik sayfaları dışında her şeyi geçersiz kılabilir **PlatformToolset** ve **proje** varsayılan özellikleri.

6. Kalan diğer proje yapılandırma özellikleri. Bu değerler özellik sayfalarında ayarlanmış değerleri geçersiz kılabilir.

7. Meta verileriyle birlikte öğeler (dosyalar). Bunlar, diğer özellikler ve içeri aktarımlardan önce olsa bile, MSBuild değerlendirme kurallarında her zaman son sözdür.

Daha fazla bilgi için [MSBuild özellikleri](/visualstudio/msbuild/msbuild-properties).

## <a name="adding-an-include-directory-to-the-set-of-default-directories"></a>Varsayılan dizinler kümesine bir ekleme dizini ekleme

Bir projeye ekleme dizini eklediğinizde, tüm varsayılan dizinleri geçersiz kılmamak önemlidir. Örneğin yeni yolu sona eklenecek bir dizin eklemenin doğru yolu olan "C:\MyNewIncludeDir\"ve sonra **$(ıncludepath)** makrosunu özellik değerinin.

## <a name="setting-environment-variables-for-a-build"></a>Bir yapı için ortam değişkenlerini ayarlama

Visual C++ derleyicisi (cl.exe) özellikle LIB, LIBPATH, PATH ve INCLUDE olmak üzere belirli ortam değişkenlerini tanır. Ayarlanan özellikler IDE ile yapı kurarken [VC ++ Directories Property Page](../ide/vcpp-directories-property-page.md) özellik sayfası, bu ortam değişkenlerini ayarlamak için kullanılır. LIB, LIBPATH ve INCLUDE değerleri zaten ayarlanmışsa (örneğin, bir Geliştirici Komutu İstemi ile), bunlar karşılık gelen MSBuild özelliklerinin değerleriyle değiştirilir. Yapı daha sonra, VC++ Dizinleri yürütülebilir dizinler özelliğinin değerini PATH öğesinin başına ekler. Bir kullanıcı tarafından tanımlanan ortam değişkeni a ve ardından ifadesini içeren kutuyu işaretleyerek kullanıcı tanımlı bir makro ayarlayabilirsiniz **Bu makroyu yapı ortamında bir ortam değişkeni olarak ayarla**.

## <a name="setting-environment-variables-for-a-debugging-session"></a>Hata ayıklama oturumu için ortam değişkenlerini ayarlama

Sol bölmede projelerin **özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri** seçip **hata ayıklama**.

Sağ bölmede değişiklik **ortam** veya **ortamı Birleştir** proje ayarları ve ardından **Tamam** düğmesi.

## <a name="modifying-properties-and-targets-without-changing-the-project-file"></a>Özellikler ve hedefler, proje dosyası değiştirmeden değiştirme

Proje dosyası değiştirmeden proje özellikleri ve hedefler MSBuild komut isteminden geçersiz kılabilirsiniz. Bazı özellikler geçici olarak ya da zaman zaman uygulamak istediğinizde bu kullanışlıdır. Bu, MSBuild biraz bilgi varsayar. Daha fazla bilgi için [MSBUild](https://docs.microsoft.com/en-us/visualstudio/msbuild/msbuild).

> [!IMPORTANT]
> .Props veya .targets dosyasını oluşturmak için XML Düzenleyicisi'nde Visual Studio ya da herhangi bir metin Düzenleyicisi'ni kullanabilirsiniz. Kullanmayın **özellik Yöneticisi** Bu senaryoda çünkü proje dosyasına özelliklerini ekler.

*Proje özelliklerini geçersiz kılmak için:*

1. Geçersiz kılmak istediğiniz özellikleri belirten bir .props dosyası oluşturun.

1. Komut isteminden: ForceImportBeforeCppTargets="C:\sources\my_props.props Ayarla"

*Proje hedefleri geçersiz kılmak için:*

1. Kendi uygulama veya belirli bir hedefe bir .targets dosyasında oluşturun

2. Komut isteminden: ForceImportAfterCppTargets Ayarla "C:\sources\my_target.targets" =

Ayrıca, iki seçenekten birini msbuild komut satırında/p: seçeneğini kullanarak ayarlayabilirsiniz:

```cmd
> msbuild myproject.sln /p:ForceImportBeforeCppTargets="C:\sources\my_props.props"
> msbuild myproject.sln /p:ForceImportAfterCppTargets="C:\sources\my_target.targets"
```

Özellikler ve bu şekilde hedefleri geçersiz kılma, Çözümdeki tüm .vcxproj dosyaları aşağıdaki içeri aktarmaları ekleme eşdeğerdir:

```cmd
<Import Project=="C:\sources\my_props.props" />
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
<Import Project==" C:\sources\my_target.targets"" />
```

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ proje oluşturma ve yönetme](../ide/creating-and-managing-visual-cpp-projects.md)<br/>
[.vcxproj ve .props dosya yapısı](vcxproj-file-structure.md)<br/>
[Özellik sayfası XML dosyaları](property-page-xml-files.md)<br/>

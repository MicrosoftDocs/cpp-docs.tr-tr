---
title: Proje özellikleriyle çalışma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 3c33a18ff0d492ef3a870a342c9d8ff292007748
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="working-with-project-properties"></a>Proje Özellikleriyle Çalışma
IDE içinde bir proje oluşturmak için gereken tüm bilgileri olarak sunulan *özellikleri*. Bu bilgiler, uygulama adı, (örneğin, DLL, LIB, EXE) uzantısı, derleyici seçenekleri, bağlayıcı seçenekleri, hata ayıklayıcı ayarları, özel derleme adımları ve diğer pek çok şeyi içerir. Genellikle, kullandığınız *özellik sayfaları* ( **proje &#124; özellikleri**) görüntülemek ve bu özellikleri değiştirmek için. 
  
 Bir proje oluşturduğunuzda, sistem çeşitli özellikleri için değer atar. Varsayılanları türü bağlı olarak biraz farklılık Uygulama Sihirbazı'nda proje ve ne seçeneklerini seçin. Örneğin, ATL projesinde MIDL dosyalarıyla ilgili özellikleri vardır, ancak bunlar yok temel konsol uygulamasındaki. Özellik sayfaları genel bölmesinde varsayılan özellikleri gösterilmektedir:  
  
 ![Visual C&#43; &#43; Proje Varsayılanları](../ide/media/visual-c---project-defaults.png "Visual C++ Proje Varsayılanları")  
  
 Uygulama adı gibi bazı özellikleri hedef platform veya hata ayıklama veya yayın derlemesi olmasından bağımsız olarak tüm yapı değişimler için geçerlidir. Ancak özelliklerinin çoğu yapılandırma bağımlıdır. Hangi belirli platform program çalışır ve doğru kodu oluşturmak için kullanılacak belirli hangi derleyici seçenekleri bilmek derleyici sahip olmasıdır. Bu nedenle, bir özellik ayarladığınızda, hangi yapılandırma ve yeni değer uygulanması gereken platform dikkat etmek önemlidir. Yalnızca Win32 hata ayıklama derlemeleri uygulamalıdır ya da hata ayıklama ARM uygulamalıdır ve hata ayıklama x64? Örneğin, **en iyi duruma getirme** özelliği, varsayılan olarak ayarlanmış **en üst düzeye hızı (/ O2)** bir sürüm yapılandırmasında, ancak hata ayıklama yapılandırmasını da devre dışı.  
  
 Özellik sayfaları, her zaman görebilir ve gerekirse değiştirirseniz, hangi yapılandırması ve platformu bir özellik değeri uygulanması gereken şekilde tasarlanmıştır. Aşağıdaki çizimde yapılandırma ve platform bilgilerini özellik sayfalarıyla üst liste kutuları gösterir. Zaman **en iyi duruma getirme** özelliği burada ayarlanmışsa, gerçekleşen etkin bir yapılandırma olmaya kırmızı oklarla gösterildiği gibi yalnızca Win32 hata ayıklama derlemeleri uygulanır.  
  
 ![Visual C&#43; &#43; özellik sayfaları gösteren etkin yapılandırma](../ide/media/visual-c---property-pages-showing-active-configuration.png "Visual C++ özellik sayfaları gösteren etkin yapılandırma")  
  
 Aynı proje özellik sayfası aşağıda gösterilmektedir, ancak yapılandırması yayın olarak değiştirildi. En iyi duruma getirme özelliği için farklı bir değer unutmayın. Ayrıca hata ayıklama etkin yapılandırma hala olduğuna dikkat edin. Burada herhangi bir yapılandırma için özellikleri ayarlayabilirsiniz; etkin olması gerekmez.  
  
 ![Visual C&#43; &#43; özellik sayfaları gösteren yayın config](../ide/media/visual-c---property-pages-showing-release-config.png "Visual C++ özellik sayfaları gösteren yayın yapılandırma")  
  
 Dosya biçimlerini ve herhangi bir türde projeleri oluşturmak için kurallar tanımlar MSBuild proje sistemi dayanır. MSBuild birden çok yapılandırmalar ve platformlar için yapı karmaşıklığını çoğunu yönetir ancak nasıl çalıştığı hakkında biraz anlamanız gerekir. Özel yapılandırmalar tanımlamak veya paylaşan ve birden çok projelerine içeri özelliklerinin yeniden kullanılabilir kümeleri oluşturmak istiyorsanız, bu özellikle önemlidir.  
  
 Proje özellikleri doğrudan proje dosyasında (*.vcxproj) ya da proje dosyası içeri aktarmalar ve hangi varsayılan değerler sağlamanızı diğer .xml veya .props dosyalarında depolanır. Daha önce gösterildiği gibi aynı yapılandırması için aynı özelliği farklı dosyaları farklı bir değer atanabilir. Bir projeyi derlerken MSBuild altyapısı proje dosyası ve içe aktarılan tüm dosyaları (aşağıda açıklanmıştır) iyi tanımlanmış bir sırada değerlendirir. Her dosya değerlendirilir gibi bu dosyasında tanımlanan tüm özellik değerlerini varolan değerlerini geçersiz kılar. Belirtilmemiş herhangi bir değeri önceki değerlendirilen dosyalarından devralınır. Özellik sayfaları özelliğiyle ayarladığınızda, bu nedenle, da burada ayarladığınız için dikkat önemlidir. .Props dosyasında "X" özelliğini ayarlama, ancak proje dosyasında ayarlanan özelliği "Y", "Y" özelliğini projesi oluşturacaksınız. Aynı özellik için bir proje öğesi "Z".cpp dosyası gibi ayarlanırsa, MSBuild altyapısı "Z" değerini kullanır. Daha fazla bilgi için bkz: [özellik devralma](#bkmkPropertyInheritance) bu makalenin ilerisinde yer.  
  
## <a name="build-configurations"></a>Derleme yapılandırmaları  
 Bir yapılandırma yalnızca bir rastgele bir ad verilen özellikler grubudur. Visual Studio hata ayıklama ve yayın yapılandırmaları sağlar ve her bir hata ayıklama derlemesi veya yayın derlemesi için uygun şekilde çeşitli özellikleri ayarlar. Kullanabileceğiniz **Configuration Manager** özel yapılandırmalar yapı belirli bir özellik için Grup Özellikleri için kolay bir yol tanımlamak için. Özellik Yöneticisi Gelişmiş Özellikler çalışmak için kullanılır, ancak özellik yapılandırmaları görselleştirmenize yardımcı olduğu için biz bunu burada tanıtır. Buradan erişim **Görünüm &#124; özellik Yöneticisi** veya **Görünüm &#124; diğer pencereler &#124; özellik Yöneticisi** ayarlarınızı bağlı olarak. Her yapılandırma/platform çifti için düğümleri projede içeriyor. Her bu düğümü altında bu yapılandırma için bazı belirli özellikleri ayarlamak özellik sayfaları (.props dosyaları) için düğümleri olan.  
  
 ![Özellik Yöneticisi](../ide/media/property-manager.png "özellik Yöneticisi")  
  
 Özellik sayfaları (bkz. Yukarıdaki) genel bölmesine gidin karakter kümesi özelliği "Ayarlı değil" yerine "Kullanım Unicode" olarak ayarlayın ve'ı tıklatın, **Tamam**, özellik Yöneticisi gösterir hiçbir **Unicodedesteği** geçerli yapılandırma, ancak özellik sayfasını diğer yapılandırmaları için orada çıkarılsın.  
  
 Özellik Yöneticisi ve özellik sayfaları hakkında daha fazla bilgi için bkz: [yeniden kullanılabilir özellik yapılandırmaları oluşturma](#bkmkPropertySheets) bu makalenin ilerisinde yer.  
  
> [!TIP]
>  .Kullanıcı dosyanın eski bir özelliktir ve doğru şekilde yapılandırma/platforma göre gruplandırılmış özellikleri tutmak için sildiğini öneririz.  
  
## <a name="target-platforms"></a>Hedef platformlar  
 *Hedef platformu* cihaz ve/veya yürütülebilir dosyayı çalıştırmak işletim sistemi türünü gösterir. Birden çok platform için bir proje oluşturabilirsiniz. C++ projeleri için kullanılabilir hedef platformlar proje türüne bağlıdır; içerir ancak x64, Win32 için sınırlı değildir ARM, Android ve iOS.     **X86** görebileceğiniz hedef platformu **Configuration Manager** aynıdır **Win32** yerel C++ projelerine. Win32 32-bit Windows anlamına gelir ve **x64** 64-bit Windows anlamına gelir. Bu iki platform hakkında daha fazla bilgi için bkz: [çalıştıran 32-bit uygulamalar](https://msdn.microsoft.com/library/windows/desktop/aa384249\(v=vs.85\).aspx).  
  
 **Herhangi bir CPU** hedef görebileceğiniz platform değeri **Configuration Manager** yerel C++ projeleri üzerinde; hiçbir etkisi olmaz C + ilgili +/ CLI ve diğer .NET türleri proje. Daha fazla bilgi için bkz: [/CLRIMAGETYPE (belirtin, CLR Resim türünde)](../build/reference/clrimagetype-specify-type-of-clr-image.md).  
  
## <a name="property-pages"></a>Özellik sayfaları  
 Daha önce belirtildiği gibi Visual C++ proje sistemi dayanır [MSBuild](/visualstudio/msbuild/msbuild-properties) ve değerler depolanır .props ve .targets dosyaları XML proje dosyasında varsayılan. Bu dosyalar bulunur Visual Studio 2015 için **\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\V140**. Bu dosyalar bulunur Visual Studio 2017  **\\Program Files (x86)\\Microsoft Visual Studio\\2017\\_edition_\\Common7\\ IDE\\VC\\VCTargets**, burada _edition_ olan yüklü Visual Studio sürümü. Özellikleri de kendi projenize ekleme olasılığınız herhangi özel .props dosyalarında saklanır. Yüksek oranda, değil Bu dosyaları el ile düzenleyin ve bunun yerine özellik sayfaları IDE içinde özellikle olanlar MSBuild çok iyi bir anlayış olmadığı sürece, devralma katılmak tüm özelliklerini değiştirmek için kullanmanızı öneririz.  
  
 Bir Visual C++ projesinin özellik sayfaları aşağıdaki resimde gösterilmektedir. Sol bölmede, **VC ++ dizinleri *** kural* seçili ve sağ bölmede bu kuralla ilişkili özellikleri listeler. `$(...)` Değerleri ne yazık ki adlı *makroları*. Bunlar *değil* C/C++ makroları ancak yalnızca derleme zamanı sabitleri. Makrolar içinde ele alınmıştır [özellik sayfası makroları](#bkmkPropertiesVersusMacros) bölümünde bu makalenin sonraki bölümlerinde.)  
  
 ![Proje özellik sayfalarını](../ide/media/project_property_pages_vc.png "Project_Property_Pages_VC")  
  
> [!WARNING]
>  **Ortak özellikleri** , Visual Studio'nun önceki sürümleri yapılandırmalarında kaldırıldı. Projesine bir başvuru eklemek için şimdi kullandığınız **Başvuru Ekle** yönetilen dilleri için olduğu gibi aynı şekilde iletişim. Bkz: [bir projedeki başvuruları yönetme](/visualstudio/ide/managing-references-in-a-project).  
  
#### <a name="to-set-a-property-for-a-project"></a>Projeye ilişkin bir özelliği ayarlamak için  
  
1.  Çoğu senaryoda, bir özel özellik sayfası oluşturmadan proje düzeyinde özellikleri ayarlayabilirsiniz. Ana menüde seçin **proje &#124; özellikleri**, veya'nde proje düğümüne sağ tıklayın **Çözüm Gezgini** ve **özellikleri**.  
  
2.  Kullanım **yapılandırma** ve **Platform** liste kutuları değişikliklerinizi hangi özellik gruplarına uygulanacağını belirlemek için iletişim kutusunun üstündeki. Çoğu durumda **tüm platformlar** ve **tüm yapılandırmaları** doğru seçimdir. Yalnızca bazı yapılandırmalar için çoklu seçim özelliklerini ayarlamak için bunları **özellik Yöneticisi**ve ardından kısayol menüsünü açın ve seçin **özellikleri**.  
  
 **Özellik sayfaları** geçerli projeye geçerli özellik sayfaları iletişim kutusu gösterir. Örneğin, projede bir .idl dosyası yoksa, MIDL özellik sayfası görüntülenmez.  
  
 Özellik sayfası özelliğinde vurgulamak olduğunda basabilirsiniz **F1** karşılık gelen derleyici veya bağlayıcı anahtar hakkında daha fazla bilgi için başvuru konusuna gidin.  
  
 Bu konularda, her özellik sayfası hakkında daha fazla bilgi bulabilirsiniz:  
  
-   [Genel Özellik Sayfası (Proje)](../ide/general-property-page-project.md)  
  
-   [Genel Özellik Sayfası (Dosya)](../ide/general-property-page-file.md)  
  
-   [Komut Satırı özellik sayfaları](../ide/command-line-property-pages.md)  
  
-   [C++ hata ayıklama yapılandırması proje ayarları](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration)  
  
-   [NMake özellik sayfası](../ide/nmake-property-page.md)  
  
-   [Bağlayıcı Özellik Sayfaları](../ide/linker-property-pages.md)  
  
-   [Kaynaklar Özellik Sayfaları](../ide/resources-property-pages.md)  
  
-   [MIDL Özellik Sayfaları](../ide/midl-property-pages.md)  
  
-   [Web Başvuruları Özellik Sayfası](../ide/web-references-property-page.md)  
  
-   [XML Verileri Oluşturma Aracı özellik sayfası](../ide/xml-data-generator-tool-property-page.md)  
  
## <a name="to-quickly-browse-and-search-all-properties"></a>Hızlı bir şekilde göz atmak ve tüm özellikleri aramak için  
 **Tüm seçenekleri** özellik sayfası (altında **yapılandırma özellikleri &#124; C/C++** düğümünde **özellik sayfaları** iletişim kutusu) göz atın ve arama yapmak için hızlı bir yolunu sağlar Geçerli bağlamda kullanılabilen özellikleri. Özel bir arama kutusu ve sonuçlara filtre uygulamanıza yardımcı olacak basit bir sözdizimi vardır:  
  
 Önek yok:  
 Yalnızca özellik adlarında arayın (büyük/küçük harf duyarsız alt dize).  
  
 '/' veya '-' :  
 Yalnızca derleyici anahtarlarında arayın (büyük/küçük harf duyarsız önek)  
  
 v:  
 Yalnızca değerlerde arayın (büyük/küçük harf duyarsız alt dize).  
  
##  <a name="bkmkPropertiesVersusMacros"></a> Özellik sayfası makroları  
 A *makrosu* Visual Studio veya MSBuild sistem tarafından tanımlanan bir değer veya kullanıcı tanımlı bir değer başvurabilir bir derleme zamanı sabit değer. Dizin yolları gibi sabit kodlu değerler yerine makroları kullanarak, makineler arasında ve Visual Studio sürümleri arasında özellik ayarlarını daha kolay paylaşabilir ve proje ayarlarınızın özellik devralmada doğru şekilde rol oynamasını sağlayabilirsiniz. Özellik Düzenleyici, tüm kullanılabilir makroları değerlerini görüntülemek için kullanabilirsiniz.  
  
### <a name="predefined-macros"></a>Önceden tanımlı makrolar  
 genel makrolar  
 Bir proje yapılandırmasındaki tüm öğelere uygulanır. Sözdizimine sahip `$(name)`. Genel makrosu örneğidir `$(VCInstallDir)`, Visual Studio yüklemenizin kök dizininin depolar. Genel makrosu karşılık gelen bir `PropertyGroup` msbuild'de.  
  
 öğe makroları  
 Sözdizimine sahip `%(name)`. Bir dosya için bir öğe makrosu yalnızca bu dosya için geçerlidir. — Örneğin, kullanabileceğiniz `%(AdditionalIncludeDirectories)` belirtmek için yalnızca belirli bir dosya için geçerli yönergeleri dahil etme. Bu tür bir öğe makrosu karşılık gelen bir `ItemGroup` MSBuild meta veriler. Bir proje yapılandırması bağlamında kullanıldığında, öğe makrosu belirli bir türdeki tüm dosyalar için geçerli olur. Örneğin, C/C++ **önişlemci tanımları** Yapılandırma özelliği gerçekleştirebileceğiniz bir `%(PreprocessorDefinitions)` projedeki tüm .cpp dosyalarını uygulandığı öğe makrosu. Bu tür bir öğe makrosu karşılık gelen bir `ItemDefinitionGroup` MSBuild meta veriler. Daha fazla bilgi için bkz: [öğe tanımları](/visualstudio/msbuild/item-definitions).  
  
### <a name="user-defined-macros"></a>Kullanıcı tanımlı makrolar  
 Oluşturabileceğiniz *kullanıcı tanımlı makrolar* proje derlemelerde değişkenleri olarak kullanılacak. Örneğin, bir özel yapı adımına veya özel yapı aracına değer sağlayan kullanıcı tanımlı bir makro oluşturabilirsiniz. Kullanıcı tanımlı makro bir ad/değer çiftidir. Bir proje dosyasında kullanmak **$(***adı***)** değeri erişmek için gösterimi.  
  
 Kullanıcı tanımlı makrolar bir özellik sayfasında depolanır. Projenizi bir özellik sayfası zaten içermiyorsa, bir altındaki adımları izleyerek oluşturabilirsiniz [yeniden kullanılabilir özellik yapılandırmaları oluşturma](#bkmkPropertySheets).  
  
##### <a name="to-create-a-user-defined-macro"></a>Kullanıcı tanımlı makro oluşturmak için  
  
1.  İçinde **özellik Yöneticisi** penceresi (menü çubuğunda seçin **Görünüm**, **özellik Yöneticisi**), bir özellik sayfası (kendi adı sona eriyor .kullanıcı) için kısayol menüsünü açın ve ardından seçin Özellikler. **Özellik sayfaları** bu özellik sayfası için iletişim kutusunu açar.  
  
2.  İletişim kutusunun sol bölmesinde seçin **kullanıcı makroları**. Sağ bölmede seçin **eklemek makrosu** açmak için düğmeye **kullanıcı makrosu Ekle** iletişim kutusu.  
  
3.  İletişim kutusunda, makro için bir ad ve değer belirtin. İsteğe bağlı olarak, seçin **bir ortam değişkeni yapı ortamında bu makrosu yap** onay kutusu.  
  
## <a name="property-editor"></a>Özellik Düzenleyicisi  
 Belirli dize özelliklerini değiştirmek ve makroları değer olarak seçmek için Özellik Düzenleyicisi'ni kullanabilirsiniz. Özellik Düzenleyicisi'ne erişmek için, özellik sayfasında bir özellik seçin ve sonra sağdaki aşağı ok düğmesini seçin. Aşağı açılan listede varsa  **\<Düzenle >**, bu özellik için Özellik Düzenleyici görüntülemek için seçin.  
  
 ![Özellik&#95;Düzenleyicisi&#95;açılır](../ide/media/property_editor_dropdown.png "Property_Editor_Dropdown")  
  
 Özellik Düzenleyicisi'nde, seçtiğiniz **makroları** düğmesi kullanılabilir makroları ve geçerli değerlerini görüntülemek için. Özellik Düzenleyici için aşağıda gösterilmiştir **ek içeren dizinler** sonra özelliği **makroları** düğmesi seçildi. Zaman **üst ya da Proje Varsayılanları nesneden devral** onay kutusu seçilidir ve yeni bir değer eklemek için şu anda devralınan tüm değerleri eklenir. Onay kutusunun işaretini kaldırırsanız, yeni değeriniz devralınan değerlerin yerini alır. Çoğu durumda, onay kutusunu seçili bırakın.  
  
 ![Özellik Düzenleyici, Visual C&#43;&#43;](../ide/media/propertyeditorvc.png "PropertyEditorVC")  
  
##  <a name="bkmkPropertySheets"></a> Yeniden kullanılabilir özellik yapılandırmaları oluşturma  
 Kullanıcı başına ve bilgisayar başına esasına göre "genel" özellikleri ayarlayabilseniz de, artık bunu yapmanızı önermiyoruz. Bunun yerine, kullanmanızı öneririz **özellik Yöneticisi** oluşturmak için bir *özellik sayfası* her tür yeniden veya diğer kişilerle paylaşmak istediğiniz proje ayarlarını depolamak için. Özellik sayfaları, diğer proje türleri için özellik ayarlarının yanlışlıkla değiştirilmesi olasılığını da azaltır. Özellik sayfaları daha ayrıntılı olarak ele alınmıştır [yeniden kullanılabilir özellik yapılandırmaları oluşturma](#bkmkPropertySheets).  
  
> [!IMPORTANT]
>  **.kullanıcı dosyaları ve neden sorunlu**  
>   
>  Visual Studio'nun önceki sürümlerinde kullanılan .kullanıcı dosya adı uzantısı ve bulunan genel özellik sayfalarını \<USERPROFILE > \AppData\Local\Microsoft\MSBuild\v4.0\ klasör. Bu dosyalar, proje yapılandırmalarına ilişkin özellikleri kullanıcı başına ve bilgisayar başına temelinde ayarladığından artık bu dosyaları önermiyoruz. Bu tür "genel" ayarlar, özellikle de yapı bilgisayarınızda birden fazla platformu hedef aldığınızda yapıları engelleyebilir. Örneğin, hem MFC projeniz hem de Windows Phone projeniz varsa, .user özellikleri bunlardan biri için geçersiz olur. Yeniden kullanılabilir özellik sayfaları daha esnek ve daha güçlüdür.  
>   
>  .user dosyaları halen Visual Studio tarafından yüklenmesine ve özellik devralımında rol oynamasına karşın, bu dosyalar varsayılan olarak boştur. Bunları referansı silmek için en iyi uygulamadır **özellik Yöneticisi** projelerinizi tüm kullanıcı başına bağımsız olarak çalışması emin olmak için bilgisayar başına ayarlar bu SCC (kaynak kodu doğru davranışı sağlamak önemlidir Denetim) ortamı.  
  
 Görüntülenecek **özellik Yöneticisi**, menü çubuğunda seçin **Görünüm**, **diğer pencereler**, **özellik Yöneticisi**.  
  
 Ortak bir sık kullanılan birden çok proje için uygulamak istediğiniz özellikler kümesini varsa, kullanabileceğiniz **özellik Yöneticisi** içinde yeniden kullanılabilir yakalamak için *özellik sayfası* olan kural tarafından dosya .props dosya adı uzantısı. Özelliklerini sıfırdan ayarlamanıza gerek kalmaması için sayfayı (veya sayfaları) yeni projelere uygulayabilirsiniz. Erişim için **özellik Yöneticisi**, menü çubuğunda seçin **Görünüm**, **özellik Yöneticisi**.  
  
 ![Özellik Yöneticisi kısayol menüsünü](../ide/media/sharingnew.png "SharingNew")  
  
 Her yapılandırma düğümü altındaki düğümleri bu yapılandırma için geçerli her özellik sayfası için bkz. Sistem projesi oluşturduğunuzda, Uygulama Sihirbazı'nda belirlediğiniz seçeneklere göre değerlerini ayarlayan özellik sayfaları ekler. Herhangi bir düğüme sağ tıklayın ve bu düğüme uygulanan özellikleri görmek için Özellikler'i seçin. Tüm özellik sayfalarını projenin "ana" özellik sayfasına (ms.cpp.props) otomatik olarak içe aktarılır ve özellik Yöneticisi'nde göründükleri sırada değerlendirilir. Değerlendirme sırasını değiştirmek için bunları taşıyabilirsiniz. Daha sonra değerlendirilir özellik sayfalarını sayfaları önceden hesaplanan değerler geçersiz kılar.  
  
 Seçerseniz **yeni proje özellik sayfası ekleme** ve seçin, örneğin, MyProps.props özellik sayfasını, bir özellik sayfası iletişim kutusu görünür. Bunun MyProps özellik sayfası için geçerli olduğuna dikkat edin; yaptığınız herhangi bir değişiklik proje dosyasına (.vcxproj) değil de sayfaya yazılır.  
  
 Aynı özellik doğrudan .vcxproj dosyasında ayarlanmışsa, özellik sayfasındaki özellikler geçersiz kılınır.  
  
 Bir özellik sayfasını gerektiği sıklıkta içeri aktarabilirsiniz. Bir çözümdeki birden çok proje, aynı özellik sayfasından ayarları devralabilir ve bir projenin birden fazla sayfası olabilir. Özellik sayfasının kendisi, başka bir özellik sayfasından ayarları devralabilir.  
  
 Birden çok yapılandırma için tek bir özellik sayfası da oluşturabilirsiniz. Bunu yapmak için her yapılandırma için bir özellik sayfası oluşturma, bunlardan biri için kısayol menüsünü açın, seçin **var olan özellik sayfası ekleme**ve ardından diğer sayfaları ekleyin. Ancak, tek bir ortak özellik sayfası kullanırsanız, ayarladığınız bir özelliğin sayfanın geçerli olduğu tüm yapılandırmalar için ayarlandığını ve IDE'nin, belirli bir özellik sayfasından hangi projelerin veya diğer özellik sayfalarının devraldığını göstermediğini unutmayın.  
  
 Birçok projesi olacak büyük çözümlerde, çözüm düzeyinde bir özellik sayfası oluşturulması yararlı olabilir. Bir proje çözüme eklediğinizde kullanmak **özellik Yöneticisi** bu özellik sayfası projeye eklemek için. Proje düzeyinde gerek duyulursa, projeye özgü değerleri ayarlamak için yeni bir özellik sayfası ekleyebilirsiniz.  
  
> [!IMPORTANT]
>  .props dosyası bir proje öğesi olarak oluşturulmadığından, varsayılan olarak kaynak denetiminde yer almaz. Dosyayı kaynak denetimine dahil etmek istiyorsanız bir çözüm öğesi olarak el ile ekleyebilirsiniz.  
  
#### <a name="to-create-a-property-sheet"></a>Bir özellik sayfası oluşturmak için  
  
1.  Menü çubuğunda seçin **Görünüm**, **özellik Yöneticisi**. **Özellik Yöneticisi** açar.  
  
2.  Özellik sayfasının kapsamını tanımlamak için, geçerli olduğu öğeyi seçin. Bu, belirli bir yapılandırma veya başka bir özellik sayfası olabilir. Bu öğe için kısayol menüsünü açın ve ardından **yeni proje özellik sayfası ekleme**. Bir ad ve konum belirtin.  
  
3.  İçinde **özellik Yöneticisi**, yeni özellik sayfasını açın ve dahil etmek istediğiniz özellikleri ayarlayın.  
  
##  <a name="bkmkPropertyInheritance"></a> Özellik devralma  
 Proje özellikleri katmanlıdır. Her katman önceki katmanın değerlerini devralır, ancak özelliğin açıkça ayarlanması devralınan değeri geçersiz kılabilir. Temel devralma ağacı şöyledir:  
  
1.  MSBuild CPP Araç Takımı'ndaki varsayılan ayarlar (.vcxproj dosyası tarafından içeri aktarılan ..\Program Files\MSBuild\Microsoft.Cpp\v4.0\Microsoft.Cpp.Default.props.)  
  
2.  Özellik sayfaları  
  
3.  .vcxproj dosyası (Varsayılan ve özellik sayfası ayarlarını geçersiz kılabilir.)  
  
4.  Öğelere ait meta veriler  
  
> [!TIP]
>  Bir özelliği bir özellik sayfasında `bold` geçerli bağlamda tanımlanır. Normal yazı tipindeki özellik devralınan özelliktir.  
  
 Proje dosyası (.vcxproj), yapı zamanında diğer özellik sayfalarını içeri aktarır. Tüm özellik sayfaları içeri aktarıldıktan sonra proje dosyası değerlendirilir ve herhangi bir özellik değerinin son tanımı kullanılan tanım olur. Bazen, belirli bir özellik değerinin nasıl devralındığını belirlemek için genişletilmiş dosyayı görüntülemek yararlıdır. Genişletilmiş sürümü görüntülemek için, Visual Studio komut isteminde aşağıdaki komutu girin. (Yer tutucu dosya adlarını, kullanmak istediğiniz dosya adlarıyla değiştirin.)  
  
 **MSBuild /pp:** *temp* **.txt** *Uygulamam* **.vcxproj**  
  
 MSBuild'i iyi bilmiyorsanız, genişletilmiş proje dosyaları büyük ve anlaşılması zor olabilir. Bir proje dosyasının temel yapısı şöyledir:  
  
1.  IDE'de gösterilmeyen temel proje özellikleri.  
  
2.  Araç takımından bağımsız bazı temel özellikleri tanımlayan Microsoft.cpp.default.props öğesinin içeri aktarımı.  
  
3.  Genel yapılandırma özellikleri (olarak sunulan **PlatformToolset** ve **proje** özellikleri varsayılan **yapılandırma genel** sayfası. Bu özellikler, sonraki adımda hangi araç takımının ve iç özellik sayfalarının Microsoft.cpp.props öğesine aktarılacağını belirler.  
  
4.  Çoğu proje varsayılanını ayarlayan Microsoft.cpp.props öğesinin içeri aktarımı.  
  
5.  .user dosyaları da dahil olmak üzere tüm özellik sayfalarının içeri aktarımı. Bu özellik sayfalarını dışında her şeyi kılabilirsiniz **PlatformToolset** ve **proje** varsayılan özellikleri.  
  
6.  Kalan diğer proje yapılandırma özellikleri. Bu değerler özellik sayfalarında ayarlanmış değerleri geçersiz kılabilir.  
  
7.  Meta verileriyle birlikte öğeler (dosyalar). Bunlar, diğer özellikler ve içeri aktarımlardan önce olsa bile, MSBuild değerlendirme kurallarında her zaman son sözdür.  
  
 Daha fazla bilgi için bkz: [MSBuild özellikleri](/visualstudio/msbuild/msbuild-properties).  
  
## <a name="adding-an-include-directory-to-the-set-of-default-directories"></a>Varsayılan dizinler kümesine bir ekleme dizini ekleme  
 Bir projeye ekleme dizini eklediğinizde, tüm varsayılan dizinleri geçersiz kılmamak önemlidir. Yeni yol örneğin eklemek için bir dizin eklemek için doğru bir şekilde olan "C:\MyNewIncludeDir\"ve ardından Ekle'yi **$(IncludePath)** makrosu özellik değerinde.  
  
## <a name="setting-environment-variables-for-a-build"></a>Bir yapı için ortam değişkenlerini ayarlama  
 Visual C++ derleyicisi (cl.exe) özellikle LIB, LIBPATH, PATH ve INCLUDE olmak üzere belirli ortam değişkenlerini tanır. IDE ayarlanır özellikleri ile oluşturduğunuzda [VC ++ dizinleri özellik sayfası](../ide/vcpp-directories-property-page.md) özellik sayfası, bu ortam değişkenleri ayarlamak için kullanılır. LIB, LIBPATH ve INCLUDE değerleri zaten ayarlanmışsa (örneğin, bir Geliştirici Komutu İstemi ile), bunlar karşılık gelen MSBuild özelliklerinin değerleriyle değiştirilir. Yapı daha sonra, VC++ Dizinleri yürütülebilir dizinler özelliğinin değerini PATH öğesinin başına ekler. Kullanıcı tanımlı ortam değişkeni bir kullanıcı tarafından tanımlanan makrosu ve belirten kutuyu işaretleyerek oluşturulan ayarlayabileceğiniz **bir ortam değişkeni yapı ortamında bu makrosu yap**.  
  
## <a name="setting-environment-variables-for-a-debugging-session"></a>Hata ayıklama oturumu için ortam değişkenlerini ayarlama  
 Projenin sol bölmesinde **özellik sayfaları** iletişim kutusunda, genişletin **yapılandırma özellikleri** ve ardından **hata ayıklama**. 
  
 Sağ bölmede, değişiklik **ortam** veya **birleştirme ortamı** proje ayarlarını ve ardından **Tamam** düğmesi.  

## <a name="modifying-properties-and-targets-without-changing-the-project-file"></a>Proje dosyası değiştirmeden özellikleri ve hedefleri değiştirme
Proje dosyası değiştirmeden proje özelliklerini ve hedefleri MSBuild komut isteminden geçersiz kılabilirsiniz. Bazı özellikler geçici olarak ya da zaman zaman uygulamak istediğinizde kullanışlıdır. MSBuild bazı bilgisine varsayar. Daha fazla bilgi için bkz: [MSBUild](https://docs.microsoft.com/en-us/visualstudio/msbuild/msbuild).

> [!IMPORTANT]
> Visual Studio ya da herhangi bir metin düzenleyicisi XML düzenleyicisinde .props veya .targets dosyası oluşturmak için kullanabilirsiniz. Kullanmayan **özellik Yöneticisi** Bu senaryoda çünkü proje dosyası özellikleri ekler.

*Proje özelliklerini geçersiz kılmak için:*
- Geçersiz kılmak istediğiniz özelliklerini belirten bir .props dosyası oluşturun. 
- Komut isteminde: ForceImportBeforeCppTargets="C:\sources\my_props.props Ayarla"
 
*Proje hedefleri geçersiz kılmak için:*
1) Kendi uygulama veya belirli bir hedefe bir .targets dosyasında oluşturma
2) Komut isteminde: ForceImportAfterCppTargets ayarlama "C:\sources\my_target.targets" =
 
P: seçeneğini kullanarak msbuild komut satırında her iki seçenek de ayarlayabilirsiniz:

```cmd
> msbuild myproject.sln /p:ForceImportBeforeCppTargets="C:\sources\my_props.props" 
> msbuild myproject.sln /p:ForceImportAfterCppTargets="C:\sources\my_target.targets" 
```  

Özellikleri ve bu şekilde hedefleri geçersiz kılma, Çözümdeki tüm .vcxproj dosyalara aşağıdaki içeri aktarmaları ekleme ile eşdeğerdir:

```cmd 
<Import Project=="C:\sources\my_props.props" />
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
<Import Project==" C:\sources\my_target.targets"" />
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ projeleri oluşturma ve yönetme](../ide/creating-and-managing-visual-cpp-projects.md) [.vcxproj ve .props dosya yapısı](vcxproj-file-structure.md) [özellik sayfası XML dosyaları](property-page-xml-files.md)
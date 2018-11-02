---
title: Özellik Sayfaları (Visual C++)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.NotAProp.Edit
helpviewer_keywords:
- project-file macro
- project properties [C++], default values
- user-defined values
- project properties [C++], setting
- macros, project-file
- property pages, project settings
- Visual C++ projects, properties
- build macro
- user-defined macros
ms.assetid: 13ffe3ea-1bc3-4bee-be5e-053a8a99cce4
ms.openlocfilehash: 4058f6574dcaa6d383295b63bfd27c5c1a0056aa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526457"
---
# <a name="property-pages-visual-c"></a>Özellik Sayfaları (Visual C++)

Özellik sayfaları kullanarak Visual Studio projeleri için ayarları belirtebilirsiniz. Açmak için **özellik sayfaları** iletişim kutusu için bir Visual Studio Proje **proje** menüsünde seçin **özellikleri**.

Böylece bunlar geçerli proje ayarları tüm yapılandırmaları derleme veya her derleme yapılandırması için farklı proje özellikleri belirtebilirsiniz belirtebilirsiniz. Örneğin, yayın yapılandırması için belirli ayarları ve diğer hata ayıklama yapılandırması ayarlarını belirtebilirsiniz.

Tüm kullanılabilir sayfaları mutlaka görüntülenen **özellik sayfaları** iletişim kutusu. Görüntülenecek sayfaları proje dosya türlerinde bağlıdır.

Daha fazla bilgi için [Working with Project Properties](../ide/working-with-project-properties.md).

Windows olmayan projeler için bkz: [Linux C++ özellik Sayfa başvurusu](../linux/prop-pages-linux.md)<!-- or [C++ Cross Platform Property Page Reference](../linux/prop-pages-linux.md)-->.

## <a name="default-properties-vs-modified-properties"></a>Varsayılan özellikleri vs. Değiştirilen Özellikler

Kullanırken **yeni proje** iletişim kutusu, Visual Studio bir proje oluşturmak için Proje Özellikleri'ni başlatmak için belirtilen proje şablonu kullanır. Bu nedenle, şablonda özellik değerleri, bu proje türü için varsayılan değerler olarak düşünülebilir. Diğer proje türleri, özellikleri farklı varsayılan değerlerine sahip olabilir.

Proje özellik değeri değişiklik kalın yazı tipinde görünür. Aşağıdaki nedenlerle bir proje özelliği değiştirilebilir:

- Proje şablonunda belirtilen olandan farklı özellik değerini gerektirdiği için Uygulama Sihirbazı'nı özelliğini değiştirir.

- Farklı bir özellik değeri belirtin **yeni proje** iletişim kutusu.

- Bir proje özelliği sayfasında farklı özellik değerini belirtin.

> [!TIP]
> Projenizi derlemek için MSBuild'ı kullanan özellik değerleri son kümesini görmek için bu komut satırını kullanarak üretebilir önişlemci çıktısını dosyasını inceleyin: **MSBuild / önişle:** *preprocessor_output_ filename*<sub>iyileştirilmiş</sub> *project_filename*<sub>iyileştirilmiş</sub>

## <a name="resetting-properties"></a>Sıfırlama özellikleri

Görüntülediğinizde **özellik sayfaları** iletişim kutusu için bir proje ve proje düğümü seçildiğinde, **Çözüm Gezgini**, birçok özelliği için seçtiğiniz **üst veya proje devralır Varsayılanları** değeri veya değiştirdiğinizde başka bir yolu.

Görüntülediğinizde **özellik sayfaları** bir proje ve bir dosya için iletişim kutusu seçiliyse **Çözüm Gezgini**, birçok özelliği için seçtiğiniz **üstten veya proje varsayılanlarındanDevral** değeri veya değiştirdiğinizde başka bir yolu. Ancak, proje proje varsayılan değerlerden farklı özellik değerlerine sahip çok sayıda dosya içeriyorsa, projeyi oluşturmak için daha uzun sürer.

> [!TIP]
> Yenilemek için **özellik sayfaları** böylece en son seçimlerini görüntüler Seç iletişim kutusu **Uygula**.

Çoğu Proje Varsayılanları sistem (platform) varsayılanlardır. Özellikleri güncelleştirdiğinizde, uygulanan stil sayfaları bazı Proje Varsayılanları türetilmesi **Proje Varsayılanları** bölümünü **genel** proje için yapılandırma özellikleri sayfası. Daha fazla bilgi için [genel özellik sayfası (Proje)](../ide/general-property-page-project.md).

## <a name="specifying-user-defined-values"></a>Kullanıcı tanımlı değerleri belirtme

Belirli özellikleri için değer tanımlamanız gerekir. Kullanıcı tanımlı bir değer, bir veya daha fazla alfasayısal karakter ya da proje dosyası makrosu adları içerebilir. Bu özelliklerin bazıları yalnızca bir kullanıcı tanımlı değeri alabilir, ancak diğer birden çok değer noktalı virgülle ayrılmış bir listesini alabilir.

Özelliği özellik adının sağ sütunda birden çok kullanıcı tanımlı değerler alabiliyorsa bir özellik veya bir liste için kullanıcı tanımlı bir değer belirtmek için aşağıdaki eylemlerden birini gerçekleştirin:

- Değeri veya değerler listesini yazın.

- Aşağı açılan oku seçin. Varsa **Düzenle** kullanılabilir seçin ve metin kutusunda, değeri veya değerler listesini yazın. Bir liste belirtmek için alternatif bir yolu metin kutusundaki ayrı bir satırda her değer yazmaktır. Özellik sayfasında, değerleri noktalı virgülle ayrılmış bir liste olarak görüntülenir.

   Bir proje dosyası makrosu bir değer olarak eklenecek seçin **makroları** ve makro adı çift tıklatın.

- Aşağı açılan oku seçin. Varsa **Gözat** kullanılabilir seçin ve ardından bir veya daha fazla değer seçin.

Birden çok değerli bir özellik için **üstten veya proje varsayılanlarından devral** seçeneği, sütununda özellik adının sağındaki açılan oku seçin ve ardından kullanılabilir **Düzenle**. Varsayılan olarak, seçenek seçilidir.

Özellik sayfası yalnızca ayarları başka bir düzeyinden devralınan birden çok değerli bir özellik için geçerli düzeyde görüntülendiğine dikkat edin. Örneğin, bir dosya seçilirse **Çözüm Gezgini** ve C/C++ seçin **önişlemci tanımları** özelliği, dosya düzeyinde tanımları görüntülenir ancak devralınan proje düzeyi tanımları görüntülenmez. Geçerli düzey hem devralınan değerleri görüntüleyin, sütununda özellik adının sağındaki açılan oku seçin ve ardından **Düzenle**. Kullanırsanız [Visual C++ proje modeli](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine), bu da nesneler için bir efekti dosyaları ve projeler, davranıştır. Dosya düzeyinde bir özellik değerleri için sorguladığınızda, diğer bir deyişle, değerleri için aynı özellik proje düzeyinde almazsınız. Ayrıca, proje düzeyinde açıkça özelliğinin değerlerini almanız gerekir. Ayrıca, devralınan bazı özellik değerlerini programlı olarak erişilebilir değil bir stil sayfasındaki gelebilir.

## <a name="in-this-section"></a>Bu Bölümde

[Gelişmiş, bildirim aracı, yapılandırma özellikleri, \<Projectname > özellik sayfaları iletişim kutusu](../ide/advanced-manifest-tool.md)

[Komut Satırı özellik sayfaları](../ide/command-line-property-pages.md)

[Özel Derleme Adımı Özellik Sayfası: Genel](../ide/custom-build-step-property-page-general.md)

[Başvuru ekleme](../ide/adding-references-in-visual-cpp-projects.md)

[Genel Özellik Sayfası (Dosya)](../ide/general-property-page-file.md)

[Genel Özellik Sayfası (Proje)](../ide/general-property-page-project.md)

[Genel, bildirim aracı, yapılandırma özellikleri, \<Projectname > özellik sayfaları iletişim kutusu](../ide/general-manifest-tool-configuration-properties.md)

[HLSL Özellik Sayfaları](../ide/hlsl-property-pages.md)

[HLSL Özellik Sayfaları: Gelişmiş](../ide/hlsl-property-pages-advanced.md)

[HLSL Özellik Sayfaları: Genel](../ide/hlsl-property-pages-general.md)

[HLSL Özellik Sayfaları: Çıktı Dosyaları](../ide/hlsl-property-pages-output-files.md)

[Girdi ve çıktı, bildirim aracı, yapılandırma özellikleri, \<Projectname > özellik sayfaları iletişim kutusu](../ide/input-and-output-manifest-tool.md)

[Yalıtılmış COM, bildirim aracı, yapılandırma özellikleri, \<Projectname > özellik sayfaları iletişim kutusu](../ide/isolated-com-manifest-tool.md)

[Bağlayıcı Özellik Sayfaları](../ide/linker-property-pages.md)

[Yönetilen Kaynaklar özellik sayfası](../ide/managed-resources-property-page.md)

[Bildirim Aracı özellik sayfaları](../ide/manifest-tool-property-pages.md)

[MIDL Özellik Sayfaları](../ide/midl-property-pages.md)

[MIDL Özellik Sayfaları: Gelişmiş](../ide/midl-property-pages-advanced.md)

[MIDL Özellik Sayfaları: Genel](../ide/midl-property-pages-general.md)

[MIDL Özellik Sayfaları: Çıktı](../ide/midl-property-pages-output.md)

[NMake özellik sayfası](../ide/nmake-property-page.md)

[Kaynaklar Özellik Sayfaları](../ide/resources-property-pages.md)

[VC++ Dizinleri Özellik Sayfası](../ide/vcpp-directories-property-page.md)

[Web Başvuruları Özellik Sayfası](../ide/web-references-property-page.md)

[XML Verileri Oluşturma Aracı özellik sayfası](../ide/xml-data-generator-tool-property-page.md)

[XML Belgesi Oluşturma Aracı Özellik Sayfaları](../ide/xml-document-generator-tool-property-pages.md)

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl Yapılır: Proje Bağımlılıklarını Oluşturma ve Kaldırma](/visualstudio/ide/how-to-create-and-remove-project-dependencies)<br>
[Nasıl Yapılır: Yapılandırmaları Oluşturma ve Düzenleme](/visualstudio/ide/how-to-create-and-edit-configurations)

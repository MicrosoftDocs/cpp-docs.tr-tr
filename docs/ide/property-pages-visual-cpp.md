---
title: "Özellik sayfaları (Visual C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.NotAProp.Edit
dev_langs: C++
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
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b0c342148266dff9551d2705f8095250daf2b096
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="property-pages-visual-c"></a>Özellik Sayfaları (Visual C++)

Özellik sayfaları kullanarak Visual Studio projeleri için ayarları belirtebilirsiniz. Açmak için **özellik sayfaları** iletişim kutusu için bir Visual Studio Proje **proje** menüsünde seçin **özellikleri**.

Bunlar geçerli olacak şekilde proje ayarları tüm yapılandırmaları oluşturmak ya da her yapı yapılandırması için farklı proje özelliklerini belirtebilirsiniz belirtebilirsiniz. Örneğin, belirli yayın yapılandırma ayarlarını ve hata ayıklama yapılandırması için diğer ayarları belirtebilirsiniz.

Tüm kullanılabilir sayfalar mutlaka görüntülenen **özellik sayfaları** iletişim kutusu. Görüntülenecek sayfaları proje dosya türlerinde bağlıdır.

Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).

Windows olmayan projeleri için bkz: [Linux C++ özellik sayfası başvurusu](../linux/prop-pages-linux.md)<!-- or [C++ Cross Platform Property Page Reference](../linux/prop-pages-linux.md)-->.

## <a name="default-properties-vs-modified-properties"></a>Varsayılan Özellikler vs. Değiştirilmiş Özellikler

Kullandığınızda **yeni proje** Visual Studio bir proje oluşturmak için iletişim kutusu, proje özelliklerini başlatmak için belirtilen proje şablonu kullanır. Bu nedenle, şablon özellik değerlerinde, bu proje türü için varsayılan değerler olarak düşünülebilir. Diğer proje türleri özellikleri farklı varsayılan değerlere sahip.

Bu değişiklik yapılırsa bir proje özellik değeri kalın olarak görünür. Proje özelliği şu nedenlerden dolayı değiştirilebilir:

- Proje şablonda belirtilen olandan farklı özellik değerini gerektirdiği için Uygulama Sihirbazı'nı özelliğini değiştirir.

- Farklı özellik değeri belirttiğiniz **yeni proje** iletişim kutusu.

- Bir proje özellik sayfasında farklı özellik değerini belirtin.

> [!TIP]
> Projenizi derleme için MSBuild kullanır özellik değerlerini son kümesini görmek için bu komut satırını kullanarak üretebilir önişlemci çıktısı dosyasını inceleyin: **MSBuild / önişle:** *preprocessor_output_ Dosya adı*<sub>kabul</sub> *project_filename*<sub>iptal et</sub>

## <a name="resetting-properties"></a>Özellikler sıfırlama

Görüntülediğinizde **özellik sayfaları** iletişim kutusu için bir proje ve proje düğümüne seçildiğinde, **Çözüm Gezgini**, birçok özelliği için seçtiğiniz **üst veya proje devralır Varsayılanları** değeri veya değiştirdiğinizde başka bir yolu.

Görüntülediğinizde **özellik sayfaları** iletişim kutusu için bir proje ve bir dosyaya seçildiğinde, **Çözüm Gezgini**, birçok özelliği için seçtiğiniz **üst ya da proje varsayılanadlardandevral** değeri veya değiştirdiğinizde başka bir yolu. Ancak, proje proje varsayılan değerlerinden farklı özellik değerlerine sahip çok sayıda dosya içeriyorsa, projeyi oluşturmak için daha uzun sürer.

> [!TIP]
> Yenilemek için **özellik sayfaları** böylece son seçimlerini görüntüler Seç iletişim kutusu **Uygula**.

Çoğu Proje Varsayılanları sistem (platform) varsayılan değerler. Bazı Proje Varsayılanları özelliklerinde güncelleştirdiğinizde, uygulanan stil sayfaları türetilen **Proje Varsayılanları** bölümünü **genel** projesi için yapılandırma özellikleri sayfası. Daha fazla bilgi için bkz: [genel özellik sayfası (Proje)](../ide/general-property-page-project.md).

## <a name="specifying-user-defined-values"></a>Kullanıcı tanımlı değerleri belirtme

Belirli özellikler için değer tanımlamanız gerekir. Kullanıcı tanımlı bir değer, bir veya daha fazla alfasayısal karakterler veya proje dosyası makrosu adları içerebilir. Bu özelliklerden bazıları yalnızca bir kullanıcı tanımlı değeri alabilir, ancak diğer birden çok değerleri noktalı virgülle ayrılmış bir listesini alabilir.

Özellik, birden çok kullanıcı tanımlı değerler, özellik adının sağındaki sütununda alabilir, bir özellik veya bir liste için kullanıcı tanımlı bir değer belirtmek için aşağıdaki eylemlerden birini gerçekleştirin:

- Değeri veya değerler listesini yazın.

- Aşağı açılan okunu seçin. Varsa **Düzenle** kullanılabilir, onu seçin ve sonra metin kutusuna değeri veya değerler listesini yazın. Bir liste belirtmek için alternatif bir yolu her değer ayrı bir satırda metin kutusuna yazmaktır. Özellik sayfasında, değerleri noktalı virgülle ayrılmış liste olarak görüntülenir.

   Proje dosyası makrosu değeri olarak eklemek için seçin **makroları** ve makrosu adına çift tıklayın.

- Aşağı açılan okunu seçin. Varsa **Gözat** kullanılabilir, onu seçin ve ardından bir veya daha fazla değer seçin.

Birden çok değerli bir özellik için **üst ya da proje varsayılan adlardan devral** seçeneği, sütun özellik adının sağındaki açılan oku seçin ve ardından kullanılabilir **Düzenle**. Varsayılan seçenek seçilidir.

Özellik sayfası yalnızca ayarları başka bir düzeyinden devralınan birden çok değerli bir özellik için geçerli düzeyde görüntülendiğine dikkat edin. Örneğin, bir dosya seçilirse **Çözüm Gezgini** ve C/C++ seçin **önişlemci tanımları** özelliği, dosya düzeyinde tanımları görüntülenir, ancak proje düzeyi tanımları devralınan görüntülenmez. Hem geçerli düzeyinde hem de devralınan değerleri görüntülemek için sütun özellik adının sağındaki açılan oku seçin ve ardından **Düzenle**. Kullanırsanız [Visual C++ proje modeli](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine), bu davranış ayrıca dosyaları ve projeler nesneler için etkili kaynaklanır. Dosya düzeyinde bir özelliğe değerleri için sorguladığınızda, diğer bir deyişle, değerleri için aynı özellik proje düzeyinde almazsınız. Proje düzeyinde özellik değerlerini açıkça almanız gerekir. Ayrıca, bazı devralınan özelliğin değerleri, bir program aracılığıyla erişilebilir değil ve stil sayfası içinden gelebilir.

## <a name="in-this-section"></a>Bu Bölümde

[Bildirim aracı, yapılandırma özellikleri, Gelişmiş \<Projectname > özellik sayfaları iletişim kutusu](../ide/advanced-manifest-tool.md)

[Komut Satırı özellik sayfaları](../ide/command-line-property-pages.md)

[Özel Derleme Adımı Özellik Sayfası: Genel](../ide/custom-build-step-property-page-general.md)

[Başvuruları ekleme](../ide/adding-references-in-visual-cpp-projects.md)

[Genel Özellik Sayfası (Dosya)](../ide/general-property-page-file.md)

[Genel Özellik Sayfası (Proje)](../ide/general-property-page-project.md)

[Genel, bildirim aracı, yapılandırma özellikleri \<Projectname > özellik sayfaları iletişim kutusu](../ide/general-manifest-tool-configuration-properties.md)

[HLSL Özellik Sayfaları](../ide/hlsl-property-pages.md)

[HLSL Özellik Sayfaları: Gelişmiş](../ide/hlsl-property-pages-advanced.md)

[HLSL Özellik Sayfaları: Genel](../ide/hlsl-property-pages-general.md)

[HLSL Özellik Sayfaları: Çıktı Dosyaları](../ide/hlsl-property-pages-output-files.md)

[Giriş ve çıkış, bildirim aracı, yapılandırma özellikleri \<Projectname > özellik sayfaları iletişim kutusu](../ide/input-and-output-manifest-tool.md)

[COM, bildirim aracı, yapılandırma özellikleri yalıtılmış \<Projectname > özellik sayfaları iletişim kutusu](../ide/isolated-com-manifest-tool.md)

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

[Nasıl Yapılır: Proje Bağımlılıklarını Oluşturma ve Kaldırma](/visualstudio/ide/how-to-create-and-remove-project-dependencies)  
[Nasıl Yapılır: Yapılandırmaları Oluşturma ve Düzenleme](/visualstudio/ide/how-to-create-and-edit-configurations)  

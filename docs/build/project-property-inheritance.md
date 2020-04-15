---
title: Visual Studio projelerinde mülkiyet mirası - C++
description: Yerel (MSBuild) Visual Studio C++ projelerinde özellik devralma nasıl çalışır?
ms.date: 02/21/2020
helpviewer_keywords:
- C++ projects, property inheritance
ms.openlocfilehash: 4740c479c6cc7c877fd72b7828a8e4811826de6c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328472"
---
# <a name="property-inheritance-in-visual-studio-projects"></a>Visual Studio projelerinde mülkiyet mirası

Visual Studio yerel proje sistemi MSBuild dayanmaktadır. MSBuild, her türlü proje oluşturmak için dosya biçimlerini ve kuralları tanımlar. Birden çok yapılandırma ve platform için oluşturma karmaşıklığının çoğunu yönetir. Nasıl çalıştığını anlamak için yararlı bulacaksınız. Özel yapılandırmalar tanımlamak istiyorsanız, bu özellikle önemlidir. Veya, birden çok projede paylaşabileceğiniz ve içe aktarabileceğiniz yeniden kullanılabilir özellik kümeleri oluşturmak için.

## <a name="the-vcxproj-file-props-files-and-targets-files"></a>.vcxproj dosyası, .props dosyaları ve .targets dosyaları

Proje özellikleri doğrudan proje dosyasında (*`.vcxproj`*) veya *`.targets`* *`.props`* proje dosyasının içe aktardığı ve varsayılan değerleri sağlayan dosyalarda depolanır. Visual Studio 2015 için bu dosyalar *`\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\V140`*. Visual Studio 2017 için bu dosyalar *`\Program Files (x86)\Microsoft Visual Studio\2017\<edition>\Common7\IDE\VC\VCTargets`* Visual *`<edition>`* Studio sürümü nerede yüklü olarak bulunmaktadır. Visual Studio 2019'da *`\Program Files (x86)\Microsoft Visual Studio\2019\<edition>\MSBuild\Microsoft\VC\v160`* bu dosyalar . Özellikler, kendi projenize *`.props`* ekleyebileceğiniz özel dosyalarda da depolanır. Bu dosyaları el ile birlikte vermemenizi şiddetle öneririz. Bunun yerine, MSBuild hakkında derin bir kanlama sahip değilseniz, başta devralmaya katılanlar olmak üzere tüm özellikleri değiştirmek için IDE'deki özellik sayfalarını kullanın.

Daha önce gösterildiği gibi, aynı yapılandırma için aynı özellik bu farklı dosyalarda farklı bir değer atanabilir. Bir proje oluşturduğunuzda, MSBuild altyapısı proje dosyasını ve tüm içe aktarılan dosyaları iyi tanımlanmış bir sırada değerlendirir (aşağıda açıklanmıştır). Her dosya değerlendirildikçe, bu dosyada tanımlanan özellik değerleri varolan değerleri geçersiz kılar. Belirtilmeyen değerler, daha önce değerlendirilen dosyalardan devralınır. Özellik sayfaları olan bir özelliği ayarladığınızda, özelliği nerede ayarladığınıza da dikkat etmek önemlidir. Bir özelliği bir *`.props`* dosyada "X" olarak ayarlarsanız, ancak özellik proje dosyasında "Y" olarak ayarlanırsa, proje "Y" olarak ayarlanmış özellik ile birlikte oluşturur. Aynı özellik dosya gibi bir *`.cpp`* proje öğesiüzerinde "Z" olarak ayarlanmışsa, MSBuild altyapısı "Z" değerini kullanır.

Temel devralma ağacı şöyledir:

1. MSBuild CPP Araç Setinden varsayılan ayarlar (... \Program Files\MSBuild\Microsoft.Cpp\v4.0\Microsoft.Cpp.Default.props, *`.vcxproj`* dosya tarafından içe aktarılır.)

1. Özellik sayfaları

1. *`.vcxproj`* Dosya. (Varsayılan ve özellik sayfası ayarlarını geçersiz kılabilir.)

1. Öğelere ait meta veriler

> [!TIP]
> Özellik sayfasında, **kalın** renkteki bir özellik geçerli bağlamda tanımlanır. Normal yazı tipindeki özellik devralınan özelliktir.

## <a name="view-an-expanded-project-file-with-all-imported-values"></a>Tüm içe aktarılan değerlerle genişletilmiş proje dosyalarını görüntüleme

Bazen, belirli bir özellik değerinin nasıl devralındığını belirlemek için genişletilmiş dosyayı görüntülemek yararlıdır. Genişletilmiş sürümü görüntülemek için, Visual Studio komut isteminde aşağıdaki komutu girin. (Yer tutucu dosya adlarını, kullanmak istediğiniz dosya adlarıyla değiştirin.)

> **msbuild /pp:**_temp_**.txt** _myapp_**.vcxproj**

MSBuild'e aşina değilseniz genişletilmiş proje dosyaları büyük ve anlaşılması zor olabilir. Bir proje dosyasının temel yapısı şöyledir:

1. IDE'de açıkolmayan temel proje özellikleri.

1. Bazı *`Microsoft.cpp.default.props`* temel, araç kümesinden bağımsız özellikleri tanımlayan, alma.

1. Genel Yapılandırma özellikleri **(Configuration Genel** sayfasında **PlatformToolset** ve **Project** varsayılan özellikleri olarak açıktadır. Bu özellikler, bir sonraki adımda hangi araç *`Microsoft.cpp.props`* kümesi nin ve içsel özellik sayfalarının içe aktarıldını belirler.

1. Proje *`Microsoft.cpp.props`* varsayılanlarının çoğunu ayarlayan , içe aktarma.

1. Dosyalar da dahil olmak *`.user`* üzere tüm özellik sayfalarını içe aktarın. Bu özellik sayfaları **PlatformToolset** ve **Project** varsayılan özellikleri dışında her şeyi geçersiz kılabilir.

1. Proje yapılandırma özelliklerinin geri kalanı. Bu değerler özellik sayfalarında ayarlanmış değerleri geçersiz kılabilir.

1. Meta verileriyle birlikte öğeler (dosyalar). Bu öğeler, diğer özellikler ve içeri almalardan önce meydana gelse ler bile, MSBuild değerlendirme kurallarında her zaman son sözcüktür.

Daha fazla bilgi için [MSBuild Özellikleri'ne](/visualstudio/msbuild/msbuild-properties)bakın.

## <a name="build-configurations"></a>Derleme yapılandırmaları

Yapılandırma, ad verilen rasgele bir özellik grubudur. Visual Studio Hata Ayıklama ve Sürüm yapılandırmaları sağlar. Her biri hata ayıklama yapısı veya sürüm yapısı için uygun şekilde çeşitli özellikler ayarlar. Özel yapılandırmaları tanımlamak için **Configuration Manager'ı** kullanabilirsiniz. Belirli bir yapı lezzeti için özellikleri gruplandırmanın kullanışlı bir yoludur.

Yapı yapılandırmaları hakkında daha iyi bir fikir almak için **Property Manager'ı**açın. Ayarlarınıza bağlı olarak, Diğer Windows > Property **Manager'ı > >** veya **Diğer Windows > Özellik Yöneticisi'> ni görüntüle**seçeneğini seçerek açabilirsiniz. **Özellik Yöneticisi'nin** projedeki her yapılandırma ve platform çifti için düğümleri vardır. Bu düğümlerin her birinin altında, bu yapılandırma*`.props`* için bazı özel özellikler ayarlayan özellik sayfaları (dosyalar) düğümleri bulunur.

![Özellik Yöneticisi](media/property-manager.png "Özellik Yöneticisi")

Örneğin, Özellik Sayfalarındaki Genel bölmeye gidebilirsiniz. Karakter Kümesi özelliğini "Unicode'u Kullan" yerine "Ayarlanmamış" olarak değiştirin ve ardından **Tamam'ı**tıklatın. Özellik Yöneticisi artık **Unicode Destek** özellik sayfası göstermiyor. Geçerli yapılandırma için kaldırılır, ancak diğer yapılandırmalar için hala oradadır.

Emlak Yöneticisi ve özellik sayfaları hakkında daha fazla bilgi için [Visual Studio C++ proje ayarlarını paylaş veya yeniden kullanın.](create-reusable-property-configurations.md)

> [!TIP]
> Dosya *`.user`* eski bir özelliktir. Özellikleri yapılandırmaya ve platforma göre doğru şekilde gruplandırmak için silmenizi öneririz.

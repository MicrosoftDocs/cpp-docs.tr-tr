---
title: Visual Studio projelerinde Özellik devralma-C++
description: Özellik devralma özelliği yerel (MSBuild) Visual Studio C++ projelerinde nasıl kullanılır.
ms.date: 02/21/2020
helpviewer_keywords:
- C++ projects, property inheritance
ms.openlocfilehash: 17b23426f70bb2d306491e538d30cffc0f202362
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919221"
---
# <a name="property-inheritance-in-visual-studio-projects"></a>Visual Studio projelerinde Özellik devralma

Visual Studio Native proje sistemi MSBuild 'i temel alır. MSBuild, her türlü proje oluşturmak için dosya biçimlerini ve kuralları tanımlar. Birden çok yapılandırma ve platform için oluşturmanın karmaşıklığının çoğunu yönetir. Nasıl çalıştığını anlamak için yararlı bulacaksınız. Özel yapılandırma tanımlamak istiyorsanız bu özellikle önemlidir. Veya birden çok projeye paylaşabileceğiniz ve içeri aktarabileceğiniz yeniden kullanılabilir özellik kümeleri oluşturmak için.

## <a name="the-vcxproj-file-props-files-and-targets-files"></a>. Vcxproj dosyası,. props dosyaları ve. targets dosyaları

::: moniker range="msvc-140"

Proje Özellikleri birkaç dosyada depolanır. Bazıları doğrudan *`.vcxproj`* Proje dosyasında depolanır. Diğerleri *`.targets`* *`.props`* , proje dosyasının içe aktardığı ve varsayılan değerleri tedarik eden diğer veya dosyalardan gelir. Visual Studio 2015 proje dosyalarını, temel dizin altında yerel ayara özgü bir klasörde bulabilirsiniz *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\v140`* .

::: moniker-end

::: moniker range="msvc-150"

Proje Özellikleri birkaç dosyada depolanır. Bazıları doğrudan *`.vcxproj`* Proje dosyasında depolanır. Diğerleri *`.targets`* *`.props`* , proje dosyasının içe aktardığı ve varsayılan değerleri tedarik eden diğer veya dosyalardan gelir. Visual Studio 2017 proje dosyalarını, temel dizin altında yerel ayara özgü bir klasörde bulabilirsiniz *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\`* .

::: moniker-end

::: moniker range=">=msvc-160"

Proje Özellikleri birkaç dosyada depolanır. Bazıları doğrudan *`.vcxproj`* Proje dosyasında depolanır. Diğerleri *`.targets`* *`.props`* , proje dosyasının içe aktardığı ve varsayılan değerleri tedarik eden diğer veya dosyalardan gelir. Visual Studio proje dosyalarını, temel dizin altında yerel ayara özgü bir klasörde bulabilirsiniz *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>`* . , `<version>` Visual Studio 'nun sürümüne özeldir. *`v160`* Visual Studio 2019 içindir.

::: moniker-end

Özellikler ayrıca *`.props`* kendi projenize ekleyebileceğiniz herhangi bir özel dosyada depolanır. Bu dosyaları el *ile düzenlememenizi* kesinlikle öneririz. Bunun yerine, MSBuild ve dosyaları ayrıntılı bir şekilde anlayamadığınız müddetçe, özellikle de Devralmada yer alan tüm özellikleri değiştirmek için IDE 'deki özellik sayfalarını kullanın *`.vcxproj`* .

Daha önce gösterildiği gibi, aynı yapılandırma için aynı özelliğe bu farklı dosyalarda farklı bir değer atanabilir. Bir proje oluşturduğunuzda, MSBuild motoru proje dosyasını ve içeri aktarılan tüm dosyaları daha sonra açıklanmış bir sırayla değerlendirir. Her dosya değerlendirildiğinde, bu dosyada tanımlanan özellik değerleri varolan değerleri geçersiz kılar. Belirtilmemiş tüm değerler daha önce değerlendirilen dosyalardan devralınır. Özellik sayfaları ile bir özelliği ayarladığınızda, bunu ayarladığınız yere dikkat etmeniz de önemlidir. Bir dosya içinde bir özelliği "X" olarak ayarlarsanız *`.props`* , ancak özellik proje dosyasında "y" olarak ayarlanırsa proje, özelliği "y" olarak ayarlanmış olarak derler. Aynı özellik bir proje öğesinde, örneğin bir dosya gibi "Z" olarak ayarlanırsa *`.cpp`* , MSBuild altyapısı "z" değerini kullanacaktır.

Temel devralma ağacı şöyledir:

1. MSBuild CPP araç takımının varsayılan ayarları ( *`Microsoft.Cpp.Default.props`* dosya tarafından içeri aktarılan taban dizinindeki dosya *`.vcxproj`* .)

1. Özellik sayfaları

1. *`.vcxproj`* dosyasýný. (Bu dosya varsayılan ve özellik sayfası ayarlarını geçersiz kılabilir.)

1. Öğelere ait meta veriler

> [!TIP]
> Özellik sayfasında, **kalın** olan bir özellik geçerli bağlamda tanımlanır. Normal yazı tipindeki özellik devralınan özelliktir.

## <a name="view-an-expanded-project-file-with-all-imported-values"></a>Tüm içeri aktarılan değerlerle genişletilmiş bir proje dosyasını görüntüleme

Bazen, belirli bir özellik değerinin nasıl devralındığını belirlemek için genişletilmiş dosyayı görüntülemek yararlıdır. Genişletilmiş sürümü görüntülemek için, Visual Studio komut isteminde aşağıdaki komutu girin. (Yer tutucu dosya adlarını, kullanmak istediğiniz dosya adlarıyla değiştirin.)

> **MSBuild/PP:**_Temp_**. txt** _MyApp_**. vcxproj**

MSBuild hakkında bilgi sahibi olmadığınız takdirde genişletilmiş proje dosyaları büyük ve anlaşılması zor olabilir. Bir proje dosyasının temel yapısı şöyledir:

1. IDE 'de gösterilmeyen temel proje özellikleri.

1. *`Microsoft.cpp.default.props`* Bazı temel, araç takımı bağımsız özelliklerini tanımlayan öğesinin içeri aktarma işlemi.

1. **Yapılandırma genel** sayfasında **platform araç takımı** ve **Proje** varsayılan özellikleri olarak gösterilen genel yapılandırma özellikleri. Bu özellikler, sonraki adımda hangi araç takımının ve iç özellik sayfalarının içeri aktarılacağını belirlenir *`Microsoft.cpp.props`* .

1. ' Nin *`Microsoft.cpp.props`* , proje varsayılanlarını büyük bir kısmını ayarlayan içeri aktarma.

1. Dosyalar dahil olmak üzere tüm özellik sayfalarını içeri aktarma *`.user`* . Bu özellik sayfaları **Platformaraç takımı** ve **Proje** varsayılan özellikleri dışında her şeyi geçersiz kılabilir.

1. Proje yapılandırma özelliklerinin geri kalanı. Bu değerler özellik sayfalarında ayarlanmış değerleri geçersiz kılabilir.

1. Meta verileriyle birlikte öğeler (dosyalar). Bu öğeler, diğer özelliklerden ve içeri aktarmalardan önce gerçekleşseler de, her zaman MSBuild değerlendirme kuralları 'ndaki son sözcüklerdir.

Daha fazla bilgi için bkz. [MSBuild özellikleri](/visualstudio/msbuild/msbuild-properties).

## <a name="build-configurations"></a>Derleme yapılandırmaları

Yapılandırma, yalnızca bir ad verilen rastgele bir özellik grubudur. Visual Studio hata ayıklama ve sürüm yapılandırması sağlar. Her bir hata ayıklama derlemesi veya yayın derlemesi için çeşitli özellikleri uygun şekilde ayarlar. Özel yapılandırma tanımlamak için **Configuration Manager** kullanabilirsiniz. Bu, belirli bir yapı türü için özellikleri gruplamak için kullanışlı bir yoldur.

Yapı yapılandırmalarının daha iyi bir fikir edinmek için **Özellik Yöneticisi** açın. Ayarlarınıza bağlı olarak **görünüm > Özellik Yöneticisi** veya **> diğer Windows > Özellik Yöneticisi** seçeneklerini belirleyerek açabilirsiniz. **Özellik Yöneticisi** , projedeki her yapılandırma ve platform çifti için düğümler içerir. Bu düğümlerin her biri, ilgili *`.props`* yapılandırma için bazı belirli özellikleri ayarlamış Özellik sayfaları (dosyalar) düğümlerdir.

![Özellik Yöneticisi](media/property-manager.png "Özellik Yöneticisi")

Örneğin, özellik sayfalarındaki genel bölmesine gidebilirsiniz. "Unicode kullan" yerine karakter kümesi özelliğini "ayarlanmadı" olarak değiştirin ve ardından **Tamam** ' a tıklayın. Özellik Yöneticisi artık **Unicode desteği** özellik sayfasını gösterir. Bu, geçerli yapılandırma için kaldırılmıştır, ancak hala diğer yapılandırmalar için de bulunur.

Özellik Yöneticisi ve özellik sayfaları hakkında daha fazla bilgi için bkz. [Visual Studio C++ proje ayarlarını paylaşma veya yeniden kullanma](create-reusable-property-configurations.md).

> [!TIP]
> *`.user`* Dosya eski bir özelliktir. Özellikleri yapılandırma ve platforma göre doğru şekilde gruplanmış tutmak için bunu silmenizi öneririz.

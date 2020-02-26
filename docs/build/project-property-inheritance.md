---
title: Visual Studio projelerinde Özellik devralma-C++
description: Özellik devralma özelliği yerel (MSBuild) Visual Studio C++ projelerinde nasıl kullanılır.
ms.date: 02/21/2020
helpviewer_keywords:
- C++ projects, property inheritance
ms.openlocfilehash: 2032ab63c7d278a080742dba8d8d0c6c3ed7a094
ms.sourcegitcommit: 9a63e9b36d5e7fb13eab15c2c35bedad4fb03ade
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2020
ms.locfileid: "77600027"
---
# <a name="property-inheritance-in-visual-studio-projects"></a>Visual Studio projelerinde Özellik devralma

Visual Studio Native proje sistemi MSBuild 'i temel alır. MSBuild, her türlü proje oluşturmak için dosya biçimlerini ve kuralları tanımlar. Birden çok yapılandırma ve platform için oluşturmanın karmaşıklığının çoğunu yönetir. Nasıl çalıştığını anlamak için yararlı bulacaksınız. Özel yapılandırma tanımlamak istiyorsanız bu özellikle önemlidir. Veya birden çok projeye paylaşabileceğiniz ve içeri aktarabileceğiniz yeniden kullanılabilir özellik kümeleri oluşturmak için.

## <a name="the-vcxproj-file-props-files-and-targets-files"></a>. Vcxproj dosyası,. props dosyaları ve. targets dosyaları

Proje özellikleri doğrudan proje dosyasında ( *`.vcxproj`* ) veya diğer *`.targets`* ya da proje dosyasının içeri aktardığı ve varsayılan değerleri tedarik eden *`.props`* dosyalarında depolanır. Visual Studio 2015 için bu dosyalar *`\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\V140`* içinde bulunur. Visual Studio 2017 için bu dosyalar, *`<edition>`* Visual Studio Edition 'ın yüklü olduğu *`\Program Files (x86)\Microsoft Visual Studio\2017\<edition>\Common7\IDE\VC\VCTargets`* ' de bulunur. Visual Studio 2019 ' de bu dosyalar *`\Program Files (x86)\Microsoft Visual Studio\2019\<edition>\MSBuild\Microsoft\VC\v160`* ' de bulunur. Özellikler ayrıca kendi projenize ekleyebileceğiniz özel *`.props`* dosyalarında da depolanır. Bu dosyaları el ile düzenlememenizi kesinlikle öneririz. Bunun yerine, MSBuild 'in derinlemesine bir şekilde anlaşılmadığı müddetçe, özellikle Devralmada yer alan tüm özellikleri değiştirmek için IDE 'deki özellik sayfalarını kullanın.

Daha önce gösterildiği gibi, aynı yapılandırma için aynı özelliğe bu farklı dosyalarda farklı bir değer atanabilir. Bir proje oluşturduğunuzda, MSBuild motoru proje dosyasını ve tüm içeri aktarılan dosyaları iyi tanımlanmış bir sırayla değerlendirir (aşağıda açıklanmıştır). Her dosya değerlendirildiğinde, bu dosyada tanımlanan özellik değerleri varolan değerleri geçersiz kılar. Belirtilmemiş tüm değerler daha önce değerlendirilen dosyalardan devralınır. Özellik sayfaları ile bir özelliği ayarladığınızda, bunu ayarladığınız yere dikkat etmeniz de önemlidir. Bir *`.props`* dosyasında bir özelliği "X" olarak ayarlarsanız, ancak özellik proje dosyasında "y" olarak ayarlanırsa, proje özelliği "y" olarak ayarlanmış olarak oluşturulur. Aynı özellik bir proje öğesinde ( *`.cpp`* dosyası gibi) "z" olarak ayarlanırsa, MSBuild altyapısı "z" değerini kullanacaktır.

Temel devralma ağacı şöyledir:

1. MSBuild CPP araç takımının varsayılan ayarları (.. *`.vcxproj`* dosyası tarafından içeri aktarılan \Program Files\MSBuild\Microsoft.Cpp\v4.0\Microsoft.cpp.default.props..)

1. Özellik sayfaları

1. *`.vcxproj`* dosyası. (Varsayılan ve özellik sayfası ayarlarını geçersiz kılabilir.)

1. Öğelere ait meta veriler

> [!TIP]
> Özellik sayfasında, **kalın** olan bir özellik geçerli bağlamda tanımlanır. Normal yazı tipindeki özellik devralınan özelliktir.

## <a name="view-an-expanded-project-file-with-all-imported-values"></a>Tüm içeri aktarılan değerlerle genişletilmiş bir proje dosyasını görüntüleme

Bazen, belirli bir özellik değerinin nasıl devralındığını belirlemek için genişletilmiş dosyayı görüntülemek yararlıdır. Genişletilmiş sürümü görüntülemek için, Visual Studio komut isteminde aşağıdaki komutu girin. (Yer tutucu dosya adlarını, kullanmak istediğiniz dosya adlarıyla değiştirin.)

> **MSBuild/PP:** _Temp_ **. txt** _MyApp_ **. vcxproj**

MSBuild hakkında bilgi sahibi olmadığınız takdirde genişletilmiş proje dosyaları büyük ve anlaşılması zor olabilir. Bir proje dosyasının temel yapısı şöyledir:

1. IDE 'de gösterilmeyen temel proje özellikleri.

1. Bazı temel ve araç takımı bağımsız özelliklerini tanımlayan *`Microsoft.cpp.default.props`* içeri aktarma.

1. **Yapılandırma genel** sayfasında **platform araç takımı** ve **Proje** varsayılan özellikleri olarak gösterilen genel yapılandırma özellikleri. Bu özellikler, sonraki adımda *`Microsoft.cpp.props`* hangi araç kümesi ve iç özellik sayfalarının içeri aktarılacağını belirlenir.

1. Proje varsayılanlarını belirleyen *`Microsoft.cpp.props`* içeri aktarma.

1. *`.user`* dosyaları da dahil olmak üzere tüm özellik sayfalarını içeri aktarın. Bu özellik sayfaları **Platformaraç takımı** ve **Proje** varsayılan özellikleri dışında her şeyi geçersiz kılabilir.

1. Proje yapılandırma özelliklerinin geri kalanı. Bu değerler özellik sayfalarında ayarlanmış değerleri geçersiz kılabilir.

1. Meta verileriyle birlikte öğeler (dosyalar). Bu öğeler, diğer özelliklerden ve içeri aktarmalardan önce gerçekleşseler de, her zaman MSBuild değerlendirme kuralları 'ndaki son sözcüklerdir.

Daha fazla bilgi için bkz. [MSBuild özellikleri](/visualstudio/msbuild/msbuild-properties).

## <a name="build-configurations"></a>Derleme yapılandırmaları

Yapılandırma, yalnızca bir ad verilen rastgele bir özellik grubudur. Visual Studio hata ayıklama ve sürüm yapılandırması sağlar. Her bir hata ayıklama derlemesi veya yayın derlemesi için çeşitli özellikleri uygun şekilde ayarlar. Özel yapılandırma tanımlamak için **Configuration Manager** kullanabilirsiniz. Bu, belirli bir yapı türü için özellikleri gruplamak için kullanışlı bir yoldur.

Yapı yapılandırmalarının daha iyi bir fikir edinmek için **Özellik Yöneticisi**açın. Ayarlarınıza bağlı olarak **görünüm > Özellik Yöneticisi** veya **> diğer Windows > Özellik Yöneticisi**seçeneklerini belirleyerek açabilirsiniz. **Özellik Yöneticisi** , projedeki her yapılandırma ve platform çifti için düğümler içerir. Bu düğümlerin her biri, bu yapılandırma için bazı belirli özellikleri ayarlamış olan özellik sayfaları ( *`.props`* dosyaları) düğümlerdir.

![Özellik Yöneticisi](media/property-manager.png "Özellik Yöneticisi")

Örneğin, özellik sayfalarındaki genel bölmesine gidebilirsiniz. "Unicode kullan" yerine karakter kümesi özelliğini "ayarlanmadı" olarak değiştirin ve ardından **Tamam**' a tıklayın. Özellik Yöneticisi artık **Unicode desteği** özellik sayfasını gösterir. Bu, geçerli yapılandırma için kaldırılmıştır, ancak hala diğer yapılandırmalar için de bulunur.

Özellik Yöneticisi ve özellik sayfaları hakkında daha fazla bilgi için bkz. [Visual Studio C++ proje ayarlarını paylaşma veya yeniden kullanma](create-reusable-property-configurations.md).

> [!TIP]
> *`.user`* dosyası eski bir özelliktir. Özellikleri yapılandırma ve platforma göre doğru şekilde gruplanmış tutmak için bunu silmenizi öneririz.

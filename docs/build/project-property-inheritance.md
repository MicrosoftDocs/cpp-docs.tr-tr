---
title: Visual Studio projelerindeki - C++ özellik devralma
ms.date: 05/16/2019
helpviewer_keywords:
- C++ projects, property inheritance
ms.openlocfilehash: 472700226ffc1f265f6fab84dbd44fca651b3c87
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837399"
---
# <a name="property-inheritance-in-visual-studio-projects"></a>Visual Studio projelerinde özellik devralma

Visual Studio Proje sistemi dosya biçimlerini ve projeleri oluşturmak için kurallar tanımlar Msbuild'i temel alır. MSBuild çoklu yapılandırmalar ve platformlar için oluşturma karmaşıklığını çoğunu yönetir ancak biraz nasıl çalıştığı konusunda anlaşılması gerekir. Özel yapılandırmalar tanımlayın veya yeniden kullanılabilir özellik kümeleri paylaşmak ve birden çok projelerine içeri oluşturmak istiyorsanız bu özellikle önemlidir.

## <a name="the-vcxproj-file-props-files-and-targets-files"></a>.Vcxproj dosyası, .props dosyaları ve .targets dosyaları

Proje özellikleri, proje dosyası (*.vcxproj) içinde doğrudan ya da proje dosyası içeri aktarmalar ve hangi varsayılan değerler sağlamanız diğer .targets veya .props dosyalarında depolanır. Visual Studio 2015 için bu dosyalar bulunur **\Program dosyaları (x86)\MSBuild\Microsoft.Cpp\v4.0\V140**. Visual Studio 2017 veya Visual Studio 2019 için bu dosyalar bulunur  **\\Program dosyaları (x86)\\Microsoft Visual Studio\\&lt;2017 veya 2019 >\\_sürümü_  \\Common7\\IDE\\VC\\VCTargets**burada _edition_ olan Visual Studio sürümü yüklü. Özellikleri, ayrıca kendi projenize ekleyebilirsiniz. herhangi özel .props dosyalarında depolanır. OLMAYAN dosyaları el ile düzenlemeniz ve bunun yerine özellik sayfaları IDE'de, özellikle de MSBuild çok iyi bir anlayışa sahip olduğunuz sürece, Devralmada rol oynayan tüm özelliklerini değiştirmek için kullanmanızı öneririz.

Daha önce gösterildiği gibi bu farklı dosyalar farklı bir değer için olan aynı yapılandırmanın aynı özelliğe atanabilir. Bir proje oluşturduğunuzda, MSBuild altyapısına proje dosyası ve içeri aktarılan tüm dosyaları (aşağıda açıklanmıştır) iyi tanımlanmış bir sırayla değerlendirir. Her dosya değerlendirilir gibi bu dosyada tanımlanan tüm özellik değerlerini mevcut değerler geçersiz kılınır. Belirtilmeyen herhangi bir değeri, daha önce değerlendirilen dosyalarından devralınır. Özellik sayfaları ile bir özelliğini ayarladığınızda, bu nedenle, aynı zamanda için ayarladığınız yere dikkat etmeniz önemlidir. Bir .props dosyası içinde "X" bir özelliği ayarlamak, ancak özelliği proje dosyasında "Y" olarak ayarlanmış, "Y" özelliği ile proje oluşturacaksınız. Aynı özellik bir .cpp dosyası gibi bir proje öğesi "Z" olarak ayarlanır, MSBuild altyapısına "Z" değerini kullanın. 

Temel devralma ağacı şöyledir:

1. MSBuild CPP Araç Takımı'ndaki varsayılan ayarlar (.vcxproj dosyası tarafından içeri aktarılan ..\Program Files\MSBuild\Microsoft.Cpp\v4.0\Microsoft.Cpp.Default.props.)

2. Özellik sayfaları

3. .vcxproj dosyası (Varsayılan ve özellik sayfası ayarlarını geçersiz kılabilir.)

4. Öğelere ait meta veriler

> [!TIP]
> Özellik sayfasında, bir özelliği `bold` geçerli bağlamda tanımlanır. Normal yazı tipindeki özellik devralınan özelliktir.

## <a name="view-an-expanded-project-file-with-all-imported-values"></a>İçeri aktarılan tüm değerleri içeren bir genişletilmiş proje dosyası görüntüleyin

Bazen, belirli bir özellik değerinin nasıl devralındığını belirlemek için genişletilmiş dosyayı görüntülemek yararlıdır. Genişletilmiş sürümü görüntülemek için, Visual Studio komut isteminde aşağıdaki komutu girin. (Yer tutucu dosya adlarını, kullanmak istediğiniz dosya adlarıyla değiştirin.)

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

## <a name="build-configurations"></a>Derleme yapılandırmaları

Bir yapılandırma yalnızca bir rastgele bir ad verilir özellikleri grubudur. Visual Studio hata ayıklama ve yayın yapılandırmaları sağlar ve her bir hata ayıklama derlemesi veya yayın yapısı için uygun şekilde çeşitli özelliklerini ayarlar. Kullanabileceğiniz **Configuration Manager** özel yapılandırmaları derleme belirli bir özellik için Grup Özellikleri için kullanışlı bir yol tanımlamak için. 

Derleme yapılandırmaları hakkında daha iyi bir fikir edinmek için açık **özellik Yöneticisi** seçerek **görünümü &#124; özellik Yöneticisi** veya **görünümü &#124; diğer Windows &#124; özellik Yöneticisi**  ayarlarınıza bağlı olarak. **Özellik Yöneticisi** düğümleri her yapılandırma/platform çifti için bir projede bulunur. Her biri bu düğümler altında özellik sayfaları (.props dosyaları) Bu yapılandırma için bazı belirli özellikleri ayarlamak için düğümlerdir.

![Özellik Yöneticisi](media/property-manager.png "özellik Yöneticisi")

Özellik sayfaları genel bölmesine gidin "Ayarlı değil" yerine "Kullanımı Unicode" için karakter kümesi özelliğini ve tıklayın, **Tamam**, özellik Yöneticisi gösterir hiçbir **Unicode desteği** için özellik sayfası Geçerli yapılandırma, ancak yine de diğer yapılandırmalar için olacak.

Özellik Yöneticisi ve özellik sayfaları hakkında daha fazla bilgi için bkz: [paylaşımını veya yeniden Visual Studio C++ proje ayarları](create-reusable-property-configurations.md).

> [!TIP]
> .User dosyasını eski bir özelliktir ve doğru şekilde yapılandırma/platform göre gruplandırılmış bir özellikler tutulabilmesi için sildiğini öneririz.




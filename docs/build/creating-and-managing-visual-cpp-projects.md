---
title: Visual Studio projeleri-C++
ms.date: 10/25/2019
helpviewer_keywords:
- ATL projects, creating
- Visual Studio C++ projects, creating
- projects [C++], creating
- Visual Studio C++ projects
- ATL projects
ms.assetid: 11003cd8-9046-4630-a189-a32bf3b88047
ms.openlocfilehash: d6bfefdaa3dfc67f861cf116718f89c0e9766e47
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624474"
---
# <a name="visual-studio-projects---c"></a>Visual Studio projeleri - C++

*Visual Studio projesi* , MSBuild derleme sistemine dayalı bir projem. MSBuild, Visual Studio için yerel derleme sistemidir ve genellikle Windows 'a özgü programlar için kullanılacak en iyi derleme sistemidir. MSBuild, Visual Studio ile sıkı bir şekilde tümleşiktir, ancak bunu komut satırından da kullanabilirsiniz. Platformlar arası projeler veya açık kaynaklı kitaplıklar kullanan projeler için Visual Studio 2017 ve üzeri sürümlerde [CMake projelerini Visual Studio 'da](cmake-projects-in-visual-studio.md) kullanmanızı öneririz. MSBuild projelerini Visual Studio 'nun eski sürümlerinden yükseltme hakkında daha fazla bilgi için bkz. [Microsoft C++ taşıma ve Yükseltme Kılavuzu](../porting/visual-cpp-porting-and-upgrading-guide.md).

## <a name="create-a-project"></a>Proje oluşturma

::: moniker range="vs-2019"

C++ **Dosya** > **Yeni** > **Proje**' yi seçerek ve sonra **dili** olarak C++ayarlayarak projeler oluşturabilirsiniz. Sonuçlar listesinde, **Platform** veya **proje türünü** ayarlayarak ve arama kutusuna anahtar sözcükleri yazarak filtreleyebileceğiniz proje şablonlarının listesini görürsünüz. 

   ![Visual Studio 2019 proje şablonları](../build/media/vs2019-choose-console-app.png "Visual Studio 2019 yeni proje Iletişim kutusu")

::: moniker-end

::: moniker range="vs-2017"

**Dosya** > **Yeni** > **Proje**' yi seçip sol bölmedeki görsel C++ ' i seçerek projeler oluşturabilirsiniz C++ . Orta bölmede proje şablonlarının bir listesini görürsünüz:

   ![Proje şablonları](../overview/media/vs2017-new-project.png "Visual Studio 2017 yeni proje Iletişim kutusu")

::: moniker-end

Visual Studio 'da yer alan tüm varsayılan proje şablonları hakkında daha fazla bilgi için bkz [ C++ . Visual Studio 'da proje şablonları](reference/visual-cpp-project-types.md). Kendi proje şablonlarınızı oluşturabilirsiniz. Daha fazla bilgi için bkz. [nasıl yapılır: proje şablonları oluşturma](/visualstudio/ide/how-to-create-project-templates).

Bir proje oluşturduktan sonra, [Çözüm Gezgini](/visualstudio/ide/solutions-and-projects-in-visual-studio) penceresinde görünür:

   ![Çözüm Gezgini](media/mathlibrary-solution-explorer-153.png)

Yeni bir proje oluşturduğunuzda, bir çözüm dosyası (. sln) de oluşturulur. Çözüme sağ tıklayıp **Çözüm Gezgini**ek projeler ekleyebilirsiniz. Çözüm dosyası, birden fazla ilişkili projeniz olduğunda ancak bundan çok daha fazlasını gerçekleştirmediğiniz durumlarda derleme bağımlılıklarını koordine etmek için kullanılır. Tüm derleyici seçenekleri proje düzeyinde ayarlanır.

## <a name="add-items"></a>Öğe Ekle

**Çözüm Gezgini** ' de projeye sağ tıklayıp **Yeni > Ekle** veya **var olan > Ekle**seçeneğini belirleyerek projenize kaynak kodu dosyaları, simgeler veya diğer öğeleri ekleyin.

## <a name="add-third-party-libraries"></a>Üçüncü taraf kitaplıklarını ekleme

Üçüncü taraf kitaplıklar eklemek için [vcpkg](vcpkg.md) paket yöneticisini kullanın. Herhangi bir Visual Studio projesinden başvuru yaparken bu kitaplığa yönelik yolları ayarlamak için Visual Studio Tümleştirme adımını çalıştırın. 

## <a name="set-compiler-options-and-other-build-properties"></a>Derleyici seçeneklerini ve diğer derleme özelliklerini ayarlama

Bir projenin yapı ayarlarını yapılandırmak için, **Çözüm Gezgini** içinde projeye sağ tıklayın ve **Özellikler**' i seçin. Daha fazla bilgi için bkz [. C++ Visual Studio 'da derleyici ve derleme özelliklerini ayarlama](working-with-project-properties.md).

## <a name="compile-and-run"></a>Derle ve Çalıştır

Yeni projeyi derlemek ve çalıştırmak için **F5** 'e basın veya ana araç çubuğunda yeşil ok ile *hata ayıklama açılan* listesine tıklayın. *Yapılandırma açılan kutusu* , *hata ayıklama* veya *yayın* derlemesi (veya başka bir özel yapılandırma) gerçekleştirmeyi tercih ettiğiniz yerdir.

Yeni bir proje hata olmadan derlenir. Kendi kodunuzu eklerken zaman zaman bir hata verebilir veya bir uyarı tetikleyebilirsiniz. Bir hata, yapılandırmanın tamamlanmasını engelliyor; uyarı yok. Tüm hatalar ve uyarılar, projeyi oluştururken hem Çıkış Penceresi hem de Hata Listesi görünür. 

   ![Çıkış penceresi ve hata listesi](../overview/media/vs2017-output-error-list.png)

Hata Listesi, vurgulanan hatada **F1** tuşuna basarak belge konusuna gidebilirsiniz.

## <a name="in-this-section"></a>Bu Bölümde

[Visual Studio’da C++ derleyicisi ve derleme özelliklerini ayarlama](working-with-project-properties.md)<br/>
Proje ayarlarınızı belirtmek için özellik sayfalarını ve özellik sayfalarını kullanma.

[Derleme zamanında kitaplıklara ve bileşenlere başvurma](adding-references-in-visual-cpp-projects.md)<br/>
Bir projeye LIBS, dll 'Ler, COM ve .NET bileşenleri ekleme.
 
[Proje Çıkış Dosyalarını Düzenleme](how-to-organize-project-output-files-for-builds.md)<br/>
Yapı sürecinde oluşturulan yürütülebilir dosyaların konumunu özelleştirme.

[Özel Derleme Adımları ve Derleme Olayları](understanding-custom-build-steps-and-build-events.md)<br/>
Belirtilen noktalarda yapı işlemine rastgele bir komut ekleme.

[Mevcut koddan proje oluşturma](how-to-create-a-cpp-project-from-existing-code.md)<br/>
Gevşek kaynak dosyaları koleksiyonundan yeni bir Visual Studio projesi oluşturma.

## <a name="see-also"></a>Ayrıca bkz.

[Projeler ve derleme sistemleri](projects-and-build-systems-cpp.md)<br>
[Microsoft C++ taşıma ve Yükseltme Kılavuzu](../porting/visual-cpp-porting-and-upgrading-guide.md)

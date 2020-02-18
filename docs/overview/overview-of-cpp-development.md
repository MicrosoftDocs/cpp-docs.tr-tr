---
title: Visual Studio’da C++ geliştirmeye genel bakış
description: Visual Studio IDE, kod C++ Düzenleyicisi, hata ayıklayıcı, test çerçeveleri, statik çözümleyiciler ve diğer programlama araçlarıyla Windows, Linux, Android ve iOS üzerinde geliştirmeyi destekler.
ms.date: 12/02/2019
helpviewer_keywords:
- Visual C++, development tools
author: corob-msft
ms.author: corob
ms.openlocfilehash: 4e04e189b44fe61759a9422139d856ab8a09f201
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415706"
---
# <a name="overview-of-c-development-in-visual-studio"></a>Visual Studio’da C++ geliştirmeye genel bakış

Visual Studio tümleşik geliştirme ortamının (IDE) bir parçası olarak Microsoft C++ (MSVC), diğer dillerle ortak olarak birçok pencere ve araç paylaşır. **Çözüm Gezgini**, kod Düzenleyicisi ve hata ayıklayıcı dahil çoğu, [Visual Studio IDE](/visualstudio/get-started/visual-studio-ide)altında belgelenmiştir. Genellikle, paylaşılan bir araç veya pencere diğer diller için C++ daha az farklı özellik kümesine sahiptir. Birkaç pencere veya araç yalnızca Visual Studio Professional veya Visual Studio Enterprise sürümlerde kullanılabilir.

Visual Studio IDE 'deki paylaşılan araçlara ek olarak, MSVC yerel kod geliştirme için özel olarak çeşitli araçlara sahiptir. Bu araçlar da bu makalede listelenmiştir. Visual Studio 'nun her sürümünde kullanılabilen araçların listesi için bkz [ C++ . Visual Studio sürümlerindeki araçlar ve Özellikler](visual-cpp-tools-and-features-in-visual-studio-editions.md).

## <a name="create-projects"></a>Projeleri oluşturma

*Proje* temelde bir çalıştırılabilir programda veya kitaplıkta yerleşik olarak bulunan görüntüler veya veri dosyaları gibi kaynak kod dosyaları ve kaynaklar kümesidir.

Visual Studio, IntelliSense, gözatma ve hata ayıklama için tam destekle birlikte kullanmak istediğiniz tüm proje sistemleri veya özel yapı araçları için destek sağlar:

- **MSBuild** , Visual Studio için yerel proje sistemidir. Ana menüden **dosya** > **Yeni** > **projesi** ' ni seçtiğinizde, farklı C++ uygulama türlerini hızla geliştirmeye başlamanızı sağlayan çok sayıda MSBuild *proje şablonu* görürsünüz.

   ::: moniker range="vs-2019"

   ![Yeni proje şablonları](../build/media/mathclient-project-name-2019.png "Visual Studio 2019 yeni proje Iletişim kutusu")

   ::: moniker-end

   ::: moniker range="<=vs-2017"

   ![Proje şablonları](media/vs2017-new-project.png "Visual Studio 2017 yeni proje Iletişim kutusu")

   ::: moniker-end

   Genel olarak, var olan CMake projelerini kullanmadığınız ya da başka bir proje sistemi kullandığınız müddetçe, bu şablonları yeni projeler için kullanmanız gerekir. Daha fazla bilgi için bkz. [MSBuild tabanlı projeler oluşturma ve yönetme](../build/creating-and-managing-visual-cpp-projects.md).

- **CMake** , iş yüküyle masaüstü geliştirmeyi yüklediğinizde VISUAL Studio IDE ile C++ tümleştirilmiş platformlar arası bir derleme sistemidir. CMake proje şablonunu yeni projeler için kullanabilir veya bir CMakeLists. txt dosyası içeren bir klasörü açabilirsiniz. Daha fazla bilgi için bkz. [Visual Studio 'Da CMake projeleri](../build/cmake-projects-in-visual-studio.md).

- Gevşek bir C++ dosya koleksiyonu da dahil olmak üzere diğer tüm derleme sistemleri, **Klasör aç** özelliği aracılığıyla desteklenir. Derleme programınızı çağırmak ve hata ayıklama oturumlarını yapılandırmak için basit JSON dosyaları oluşturursunuz. Daha fazla bilgi için bkz. [klasör projelerini C++açın ](../build/open-folder-projects-cpp.md).

## <a name="add-to-source-control"></a>Kaynak denetimine Ekle

Kaynak denetimi, birden çok geliştirici arasında çalışmayı koordine etmenize, sürmekte olan işleri üretim kodundan yalıtmanıza ve kaynak kodunuzu yedeklemenize olanak sağlar. Visual Studio, **Takım Gezgini** penceresi aracılığıyla Git ve [Team Foundation sürüm denetimi \(TFVC\)](/azure/devops/repos/tfvc/) destekler.

::: moniker range="vs-2019"

![Takım Gezgini](media/vs2019-team-explorer.png "Visual Studio 2017 Takım Gezgini")

::: moniker-end

::: moniker range="<=vs-2017"

![Takım Gezgini](media/vs2017-team-explorer.png "Visual Studio 2017 Takım Gezgini")

::: moniker-end

Azure 'da depoları ile git tümleştirmesi hakkında daha fazla bilgi için bkz. [Visual Studio 2017 ile kodunuzu paylaşma ve git Azure Repos](/azure/devops/repos/git/share-your-code-in-git-vs-2017). GitHub ile git tümleştirmesi hakkında daha fazla bilgi için bkz. [Visual Studio Için GitHub Uzantısı](https://visualstudio.github.com/).

## <a name="obtain-libraries"></a>Kitaplıkları Al

Üçüncü taraf kitaplıklarını almak ve yüklemek için [vcpkg](../build/vcpkg.md) paket yöneticisini kullanın. 900 ' den fazla açık kaynak kitaplığı şu anda katalogda mevcuttur.

## <a name="create-user-interfaces-with-designers"></a>Tasarımcılarla Kullanıcı arabirimleri oluşturma

Programınızın bir kullanıcı arabirimi varsa, bunu düğmeler, liste kutuları gibi denetimlerle hızlıca doldurmak için tasarımcı kullanabilirsiniz. Araç kutusu penceresinden bir denetimi sürüklediğinizde ve tasarım yüzeyine bıraktığınızda, Visual Studio işi gerçekleştirmek için gereken kaynakları ve kodu oluşturur. Ardından, görünümü ve davranışı özelleştirmek için kodu yazarsınız.

![Tasarımcı ve araç kutusu](media/vs2017-toolbox-designer.png "Visual Studio 2017 araç kutusu ve tasarımcı")

Evrensel Windows Platformu bir uygulama için Kullanıcı arabirimi tasarlama hakkında daha fazla bilgi için bkz. [Tasarım ve Kullanıcı](https://developer.microsoft.com/windows/design)arabirimi.

MFC uygulaması için Kullanıcı arabirimi oluşturma hakkında daha fazla bilgi için bkz. [MFC masaüstü uygulamaları](../mfc/mfc-desktop-applications.md). Win32 Windows programları hakkında daha fazla bilgi için bkz. [Windows Masaüstü uygulamaları](../windows/windows-desktop-applications-cpp.md).

## <a name="write-code"></a>Kod yazma

Bir proje oluşturduktan sonra, tüm proje dosyaları **Çözüm Gezgini** penceresinde görüntülenir. (Bir *çözüm* , bir veya daha fazla ilgili proje için mantıksal bir kapsayıcıdır.) **Çözüm Gezgini**' de bir. h veya. cpp dosyasına tıkladığınızda, dosya kod düzenleyicisinde açılır.

![Çözüm Gezgini ve kod Düzenleyicisi](media/vs2017-solution-explorer-code-editor.png "Visual Studio 2017 Çözüm Gezgini ve kod Düzenleyicisi")

Kod Düzenleyicisi, kaynak kodu için C++ özelleştirilmiş bir sözcük işlemcisidir. Kodu daha okunaklı ve anlaşılması daha kolay hale getirmek için BT renk kodları dil anahtar sözcükleri, yöntem ve değişken adları ve kodunuzun diğer öğeleri. Ayrıca, yeniden düzenleme kodu, farklı dosyalar arasında gezinme ve kodun nasıl yapılandırıldığını anlamak için araçlar sağlar. Daha fazla bilgi için bkz. [kod yazma ve yeniden düzenleme](../ide/writing-and-refactoring-code-cpp.md).

## <a name="add-and-edit-resources"></a>Kaynakları ekleme ve düzenleme

Bir Windows programı veya DLL genellikle iletişim kutuları, simgeler, görüntüler, yerelleştirilebilir dizeler, giriş ekranları, veritabanı bağlantı dizeleri veya herhangi bir rastgele veri gibi bazı *kaynakları*içerir. Visual Studio, kaynak ekleme ve düzenlemenin araçlarını içerir. Daha fazla bilgi için bkz. [kaynak dosyalarıyla çalışma](../windows/working-with-resource-files.md).

## <a name="build-compile-and-link"></a>Derle (Derle ve bağla)

Menü çubuğunda **yapı** > **derleme çözümünü** seçin ya da bir projeyi derlemek ve bağlamak için **CTRL + SHIFT + B** tuş birleşimini girin. Derleme hataları ve uyarıları Hata Listesi bildirilir (**CTRL +\\, E**). **Çıkış** penceresi (**alt + 2**) yapı işlemi hakkındaki bilgileri gösterir.

![Çıkış Penceresi ve Hata Listesi](media/vs2017-output-error-list.png "Visual Studio 2017 çıkış penceresi ve Hata Listesi")

Yapıları yapılandırma hakkında daha fazla bilgi için bkz. [Proje özellikleri](../build/working-with-project-properties.md) ve [projelerle çalışma ve derleme sistemleri](../build/projects-and-build-systems-cpp.md).

Ayrıca, derleyicisini (CL. exe) ve NMAKE ve LIB gibi diğer derleme ile ilgili birçok bağımsız aracı doğrudan komut satırından da kullanabilirsiniz. Daha fazla bilgi için, bkz. komut satırı ve [cC++ /bina başvurusu](../build/reference/c-cpp-building-reference.md) [üzerinde cC++ /Code oluşturma](../build/building-on-the-command-line.md) .

## <a name="debug"></a>Hata ayıklama

**F5**tuşuna basarak hata ayıklamaya başlayabilirsiniz. Yürütme, ayarlamış olduğunuz tüm kesme noktalarında duraklatılır ( **F9**tuşuna basarak). Ayrıca, tek seferde (**F10**) bir satır halinde ilerleyerek, değişkenlerin veya yazmaçların değerlerini görüntüleyebilir, hatta bazı durumlarda kodda değişiklik yapabilir ve yeniden derlemeden hata ayıklamaya devam edebilirsiniz. Aşağıdaki çizimde, bir kesme noktasında yürütmenin durdurulduğu bir hata ayıklama oturumu gösterilmektedir. Veri yapısı üyelerinin değerleri, **Izleme penceresinde**görünür.

![Hata ayıklama oturumu](media/vs2017-debug-watch.png "Visual Studio 2017 hata ayıklama oturumu")

Daha fazla bilgi için bkz. [Visual Studio 'Da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio).

## <a name="test"></a>Test etme

Visual Studio için C++Microsoft birim testi çerçevesini, ayrıca Boost. test, Google test ve ctest desteğini içerir. **Test Gezgini** penceresinden testlerinizi çalıştırın:

![Test Gezgini](media/cpp-test-explorer-passed.png "Visual Studio 2017 test Gezgini")

Daha fazla bilgi için bkz. [birim testlerini kullanarak kodu doğrulama](/visualstudio/test/unit-test-your-code) ve [Visual Studio 'da C/C++ için birim testleri yazma](/visualstudio/test/writing-unit-tests-for-c-cpp).

## <a name="analyze"></a>Çözümleme

Visual Studio, kaynak kodunuzda olası sorunları tespit eden statik kod çözümleme araçları içerir. Bu araçlar, [ C++ temel kılavuz](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md) kuralları denetleyicilerinin bir uygulamasını içerir. Daha fazla bilgi için bkz. [C/C++ Overview için kod analizi](/cpp/code-quality/code-analysis-for-c-cpp-overview).

## <a name="deploy-completed-applications"></a>Tamamlanmış uygulamaları dağıtma

Microsoft Store aracılığıyla müşterilere hem geleneksel masaüstü uygulamaları hem de UWP uygulamaları dağıtabilirsiniz. CRT dağıtımı, arka planda otomatik olarak işlenir. Daha fazla bilgi için bkz. [Windows Uygulamaları ve oyunları yayımlama](/windows/uwp/publish/).

Ayrıca, yerel C++ bir masaüstünü başka bir bilgisayara dağıtabilirsiniz. Daha fazla bilgi için bkz. [Masaüstü uygulamaları dağıtma](../windows/deploying-native-desktop-applications-visual-cpp.md).

C++/CLI programını dağıtma hakkında daha fazla bilgi için bkz. [geliştiriciler için dağıtım kılavuzu](/dotnet/framework/deployment/deployment-guide-for-developers),

## <a name="next-steps"></a>Sonraki adımlar

Bu tanıtıcı makaleler biriyle boyunca izleyerek daha fazla Visual Studio'ı keşfedin:

> [!div class="nextstepaction"]
> [Kod düzenleyicisini kullanmayı öğrenin](/visualstudio/get-started/tutorial-editor)

> [!div class="nextstepaction"]
> [Projeler ve çözümler hakkında bilgi edinin](/visualstudio/get-started/tutorial-projects-solutions)

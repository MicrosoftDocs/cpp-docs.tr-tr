---
title: Visual Studio’da C++ geliştirmeye genel bakış
description: Visual Studio IDE, kod Düzenleyicisi, hata ayıklayıcı, test çerçeveleri, statik çözümleyiciler ve diğer programlama araçlarıyla Windows, Linux, Android ve iOS 'ta C++ geliştirmeyi destekler.
ms.date: 12/02/2019
helpviewer_keywords:
- Visual C++, development tools
author: corob-msft
ms.author: corob
ms.openlocfilehash: db0a4ccbab142d01f0506b77237dbb09d43a1cf0
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924359"
---
# <a name="overview-of-c-development-in-visual-studio"></a>Visual Studio’da C++ geliştirmeye genel bakış

Visual Studio tümleşik geliştirme ortamının (IDE) bir parçası olarak, Microsoft C++ (MSVC), diğer dillerle ortak olarak birçok pencere ve araç paylaşır. **Çözüm Gezgini** , kod Düzenleyicisi ve hata ayıklayıcı dahil çoğu, [Visual Studio IDE](/visualstudio/get-started/visual-studio-ide)altında belgelenmiştir. Genellikle paylaşılan bir araç veya pencere, C++ için diğer dillere kıyasla biraz farklı bir özellik kümesine sahiptir. Birkaç pencere veya araç yalnızca Visual Studio Professional veya Visual Studio Enterprise sürümlerde kullanılabilir.

Visual Studio IDE 'deki paylaşılan araçlara ek olarak, MSVC yerel kod geliştirme için özel olarak çeşitli araçlara sahiptir. Bu araçlar da bu makalede listelenmiştir. Visual Studio 'nun her sürümünde hangi araçların kullanılabildiği bir listesi için bkz. [Visual Studio sürümlerindeki C++ araçları ve özellikleri](visual-cpp-tools-and-features-in-visual-studio-editions.md).

## <a name="create-projects"></a>Projeleri oluşturma

*Proje* temelde bir çalıştırılabilir programda veya kitaplıkta yerleşik olarak bulunan görüntüler veya veri dosyaları gibi kaynak kod dosyaları ve kaynaklar kümesidir.

Visual Studio, IntelliSense, gözatma ve hata ayıklama için tam destekle birlikte kullanmak istediğiniz tüm proje sistemleri veya özel yapı araçları için destek sağlar:

- **MSBuild** , Visual Studio için yerel proje sistemidir. Ana menüden **Dosya**  >  **Yeni**  >  **Proje** ' yi seçtiğinizde, farklı türlerde C++ uygulamaları hızla geliştirmeye başlamanızı sağlayan birçok tür MSBuild *proje şablonu* görürsünüz.

   ::: moniker range="msvc-160"

   ![Yeni proje şablonları](../build/media/mathclient-project-name-2019.png "Visual Studio 2019 yeni proje Iletişim kutusu")

   ::: moniker-end

   ::: moniker range="<=msvc-150"

   ![Proje şablonları](media/vs2017-new-project.png "Visual Studio 2017 yeni proje Iletişim kutusu")

   ::: moniker-end

   Genel olarak, var olan CMake projelerini kullanmadığınız ya da başka bir proje sistemi kullandığınız müddetçe, bu şablonları yeni projeler için kullanmanız gerekir. Daha fazla bilgi için bkz. [MSBuild tabanlı projeler oluşturma ve yönetme](../build/creating-and-managing-visual-cpp-projects.md).

- **CMake** , C++ iş yüküne sahip masaüstü geliştirmeyi yüklediğinizde VISUAL Studio IDE ile tümleştirilmiş platformlar arası bir derleme sistemidir. CMake proje şablonunu yeni projeler için kullanabilir veya yalnızca bir CMakeLists.txt dosyası içeren bir klasör açabilirsiniz. Daha fazla bilgi için bkz. [Visual Studio 'Da CMake projeleri](../build/cmake-projects-in-visual-studio.md).

- Gevşek bir dosya koleksiyonu da dahil olmak üzere diğer tüm C++ derleme sistemleri, **Klasör aç** özelliği aracılığıyla desteklenir. Derleme programınızı çağırmak ve hata ayıklama oturumlarını yapılandırmak için basit JSON dosyaları oluşturursunuz. Daha fazla bilgi için bkz. [C++ Için klasör projelerini açma](../build/open-folder-projects-cpp.md).

## <a name="add-to-source-control"></a>Kaynak denetimine Ekle

Kaynak denetimi, birden çok geliştirici arasında çalışmayı koordine etmenize, sürmekte olan işleri üretim kodundan yalıtmanıza ve kaynak kodunuzu yedeklemenize olanak sağlar. Visual Studio, git ve [Team Foundation sürüm denetimi \( TFVC \)](/azure/devops/repos/tfvc/) 'yi **Takım Gezgini** penceresi aracılığıyla destekler.

::: moniker range="msvc-160"

![Visual Studio 2019 ' de Takım Gezgini penceresinin ekran görüntüsü.](media/vs2019-team-explorer.png "Visual Studio 2017 Takım Gezgini")

::: moniker-end

::: moniker range="<=msvc-150"

![Visual Studio 2017 ' de Takım Gezgini penceresinin ekran görüntüsü.](media/vs2017-team-explorer.png "Visual Studio 2017 Takım Gezgini")

::: moniker-end

Azure 'da depoları ile git tümleştirmesi hakkında daha fazla bilgi için bkz. [Visual Studio 2017 ile kodunuzu paylaşma ve git Azure Repos](/azure/devops/repos/git/share-your-code-in-git-vs-2017). GitHub ile git tümleştirmesi hakkında daha fazla bilgi için bkz. [Visual Studio Için GitHub Uzantısı](https://visualstudio.github.com/).

## <a name="obtain-libraries"></a>Kitaplıkları Al

Üçüncü taraf kitaplıklarını almak ve yüklemek için [vcpkg](../build/vcpkg.md) paket yöneticisini kullanın. 900 ' den fazla açık kaynak kitaplığı şu anda katalogda mevcuttur.

## <a name="create-user-interfaces-with-designers"></a>Tasarımcılarla Kullanıcı arabirimleri oluşturma

Programınızın bir kullanıcı arabirimi varsa, bunu düğmeler, liste kutuları gibi denetimlerle hızlıca doldurmak için tasarımcı kullanabilirsiniz. Araç kutusu penceresinden bir denetimi sürüklediğinizde ve tasarım yüzeyine bıraktığınızda, Visual Studio işi gerçekleştirmek için gereken kaynakları ve kodu oluşturur. Ardından, görünümü ve davranışı özelleştirmek için kodu yazarsınız.

![Tasarımcı ve araç kutusu](media/vs2017-toolbox-designer.png "Visual Studio 2017 araç kutusu ve tasarımcı")

Evrensel Windows Platformu bir uygulama için Kullanıcı arabirimi tasarlama hakkında daha fazla bilgi için bkz. [Tasarım ve Kullanıcı](https://developer.microsoft.com/windows/design)arabirimi.

MFC uygulaması için Kullanıcı arabirimi oluşturma hakkında daha fazla bilgi için bkz. [MFC masaüstü uygulamaları](../mfc/mfc-desktop-applications.md). Win32 Windows programları hakkında daha fazla bilgi için bkz. [Windows Masaüstü uygulamaları](../windows/desktop-applications-visual-cpp.md).

## <a name="write-code"></a>Kod yazma

Bir proje oluşturduktan sonra, tüm proje dosyaları **Çözüm Gezgini** penceresinde görüntülenir. (Bir *çözüm* , bir veya daha fazla ilgili proje için mantıksal bir kapsayıcıdır.) **Çözüm Gezgini** ' de bir. h veya. cpp dosyasına tıkladığınızda, dosya kod düzenleyicisinde açılır.

![Çözüm Gezgini ve kod Düzenleyicisi](media/vs2017-solution-explorer-code-editor.png "Visual Studio 2017 Çözüm Gezgini ve kod Düzenleyicisi")

Kod Düzenleyicisi, C++ kaynak kodu için özelleştirilmiş bir sözcük işlemcisidir. Kodu daha okunaklı ve anlaşılması daha kolay hale getirmek için BT renk kodları dil anahtar sözcükleri, yöntem ve değişken adları ve kodunuzun diğer öğeleri. Ayrıca, yeniden düzenleme kodu, farklı dosyalar arasında gezinme ve kodun nasıl yapılandırıldığını anlamak için araçlar sağlar. Daha fazla bilgi için bkz. [kod yazma ve yeniden düzenleme](../ide/writing-and-refactoring-code-cpp.md).

## <a name="add-and-edit-resources"></a>Kaynakları ekleme ve düzenleme

Bir Windows programı veya DLL genellikle iletişim kutuları, simgeler, görüntüler, yerelleştirilebilir dizeler, giriş ekranları, veritabanı bağlantı dizeleri veya herhangi bir rastgele veri gibi bazı *kaynakları* içerir. Visual Studio, kaynak ekleme ve düzenlemenin araçlarını içerir. Daha fazla bilgi için bkz. [kaynak dosyalarıyla çalışma](../windows/working-with-resource-files.md).

## <a name="build-compile-and-link"></a>Derle (Derle ve bağla)

**Build**  >  Proje derlemek ve bağlamak için, menü çubuğunda yapı **oluşturma çözümünü** seçin veya **CTRL + SHIFT + B** tuş birleşimini girin. Derleme hataları ve uyarıları Hata Listesi bildirilir ( **CTRL + \\ , E** ). **Çıkış** penceresi ( **alt + 2** ) yapı işlemi hakkındaki bilgileri gösterir.

![Çıkış Penceresi ve Hata Listesi](media/vs2017-output-error-list.png "Visual Studio 2017 çıkış penceresi ve Hata Listesi")

Yapıları yapılandırma hakkında daha fazla bilgi için bkz. [Proje özellikleri](../build/working-with-project-properties.md) ve [projelerle çalışma ve derleme sistemleri](../build/projects-and-build-systems-cpp.md).

Ayrıca, derleyicisini (cl.exe) ve derleme ile ilgili diğer araçları ve NMAKE ve LIB gibi diğer birçok bağımsız aracı doğrudan komut satırından da kullanabilirsiniz Daha fazla bilgi için, bkz. [komut satırında c/c++ kodu derleme](../build/building-on-the-command-line.md) ve [c/c++ oluşturma başvurusu](../build/reference/c-cpp-building-reference.md).

## <a name="debug"></a>Hata ayıklama

**F5** tuşuna basarak hata ayıklamaya başlayabilirsiniz. Yürütme, ayarlamış olduğunuz tüm kesme noktalarında duraklatılır ( **F9** tuşuna basarak). Ayrıca, tek seferde ( **F10** ) bir satır halinde ilerleyerek, değişkenlerin veya yazmaçların değerlerini görüntüleyebilir, hatta bazı durumlarda kodda değişiklik yapabilir ve yeniden derlemeden hata ayıklamaya devam edebilirsiniz. Aşağıdaki çizimde, bir kesme noktasında yürütmenin durdurulduğu bir hata ayıklama oturumu gösterilmektedir. Veri yapısı üyelerinin değerleri, **Izleme penceresinde** görünür.

![Hata ayıklama oturumu](media/vs2017-debug-watch.png "Visual Studio 2017 hata ayıklama oturumu")

Daha fazla bilgi için bkz. [Visual Studio 'Da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio).

## <a name="test"></a>Test etme

Visual Studio, C++ için Microsoft birim testi çerçevesini, ayrıca Boost. test, Google Test ve CTest desteğini içerir. **Test Gezgini** penceresinden testlerinizi çalıştırın:

![Test Gezgini](media/cpp-test-explorer-passed.png "Visual Studio 2017 test Gezgini")

Daha fazla bilgi için bkz. Visual Studio 'da [birim testlerini kullanarak kodu doğrulama](/visualstudio/test/unit-test-your-code) ve [C/C++ Için birim testleri yazma](/visualstudio/test/writing-unit-tests-for-c-cpp).

## <a name="analyze"></a>Analiz

Visual Studio, kaynak kodunuzda olası sorunları tespit eden statik kod çözümleme araçları içerir. Bu araçlar [C++ temel yönergeleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md) kuralları denetleyicilerinin bir uygulamasını içerir. Daha fazla bilgi için bkz. [C/C++ Için kod analizi genel bakış](../code-quality/code-analysis-for-c-cpp-overview.md).

## <a name="deploy-completed-applications"></a>Tamamlanmış uygulamaları dağıtma

Microsoft Store aracılığıyla müşterilere hem geleneksel masaüstü uygulamaları hem de UWP uygulamaları dağıtabilirsiniz. CRT dağıtımı, arka planda otomatik olarak işlenir. Daha fazla bilgi için bkz. [Windows Uygulamaları ve oyunları yayımlama](/windows/uwp/publish/).

Ayrıca, yerel bir C++ masaüstünü başka bir bilgisayara dağıtabilirsiniz. Daha fazla bilgi için bkz. [Masaüstü uygulamaları dağıtma](../windows/deploying-native-desktop-applications-visual-cpp.md).

C++/CLı programını dağıtma hakkında daha fazla bilgi için bkz. [geliştiriciler Için dağıtım kılavuzu](/dotnet/framework/deployment/deployment-guide-for-developers),

## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki tanıtım makaleleriyle birlikte Visual Studio 'Yu daha ayrıntılı bir şekilde bulun:

> [!div class="nextstepaction"]
> [Kod düzenleyicisini kullanmayı öğrenin](/visualstudio/get-started/tutorial-editor)

> [!div class="nextstepaction"]
> [Projeler ve çözümler hakkında bilgi edinin](/visualstudio/get-started/tutorial-projects-solutions)

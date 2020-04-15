---
title: Visual Studio’da C++ geliştirmeye genel bakış
description: Visual Studio IDE, Windows, Linux, Android ve iOS'ta C++ geliştirmeyi kod düzenleyicisi, hata ayıklayıcı, test çerçeveleri, statik çözümleyiciler ve diğer programlama araçlarıyla destekler.
ms.date: 12/02/2019
helpviewer_keywords:
- Visual C++, development tools
author: corob-msft
ms.author: corob
ms.openlocfilehash: 4e04e189b44fe61759a9422139d856ab8a09f201
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "77415706"
---
# <a name="overview-of-c-development-in-visual-studio"></a>Visual Studio’da C++ geliştirmeye genel bakış

Visual Studio Tümleşik Geliştirme Ortamının (IDE) bir parçası olarak, Microsoft C++ (MSVC) diğer dillerde birçok pencere ve araçları paylaşır. **Çözüm Gezgini,** kod düzenleyicisi ve hata ayıklayıcı dahil olmak üzere bunların çoğu [Visual Studio IDE](/visualstudio/get-started/visual-studio-ide)altında belgelenmiştir. Genellikle paylaşılan bir araç veya pencere, C++ için diğer dillere göre biraz daha farklı özelliklere sahiptir. Birkaç pencere veya araç yalnızca Visual Studio Professional veya Visual Studio Enterprise sürümlerinde kullanılabilir.

Visual Studio IDE'deki paylaşılan araçlara ek olarak, MSVC'nin yerel kod geliştirme için özel olarak çeşitli araçları vardır. Bu araçlar da bu makalede listelenmiştir. Visual Studio'nun her sürümünde hangi araçların kullanılabildiği ne kadar çok şey varsa listesi için [Visual Studio Sürümlerinde C++ Araçları ve Özellikleri](visual-cpp-tools-and-features-in-visual-studio-editions.md)bölümüne bakın.

## <a name="create-projects"></a>Projeleri oluşturma

*Proje* temelde, yürütülebilir bir programveya kitaplık ta dahil olan görüntüler veya veri dosyaları gibi kaynak kodu dosyaları ve kaynakları kümesidir.

Visual Studio, IntelliSense, tarama ve hata ayıklama için tam destek le birlikte, kullanmak istediğiniz herhangi bir proje sistemi veya özel yapı araçları için destek sağlar:

- **MSBuild** Visual Studio için yerli proje sistemidir. Ana menüden > **Yeni** > **Dosya'yı** seçtiğinizde, farklı C++ uygulamaları geliştirmeye hızla başlamanızı sağlayan birçok TÜRDE MSBuild *proje şablonu* görürsünüz. **File**

   ::: moniker range="vs-2019"

   ![Yeni Proje Şablonları](../build/media/mathclient-project-name-2019.png "Visual Studio 2019 Yeni Proje Dialog")

   ::: moniker-end

   ::: moniker range="<=vs-2017"

   ![Proje Şablonları](media/vs2017-new-project.png "Visual Studio 2017 Yeni Proje Dialog")

   ::: moniker-end

   Genel olarak, varolan CMake projelerini kullanmıyorsanız veya başka bir proje sistemi kullanmıyorsanız, bu şablonları yeni projeler için kullanmanız gerekir. Daha fazla bilgi için [bkz.](../build/creating-and-managing-visual-cpp-projects.md)

- **CMake,** C++ iş yüküyle Masaüstü geliştirmeyi yüklediğinizde Visual Studio IDE'ye entegre edilmiş bir çapraz platform oluşturma sistemidir. Yeni projeler için CMake proje şablonu kullanabilir veya cmakeLists.txt dosyası olan bir klasörü açabilirsiniz. Daha fazla bilgi için [Visual Studio'daki CMake projelerine](../build/cmake-projects-in-visual-studio.md)bakın.

- Gevşek bir dosya koleksiyonu da dahil olmak üzere diğer c++ yapı **sistemi, Açık Klasör** özelliği aracılığıyla desteklenir. Yapı programınızı çağırmak ve hata ayıklama oturumlarını yapılandırmak için basit JSON dosyaları oluşturursunuz. Daha fazla bilgi için [C++ için Klasör Aç projelerine](../build/open-folder-projects-cpp.md)bakın.

## <a name="add-to-source-control"></a>Kaynak denetimine ekle

Kaynak denetimi, birden çok geliştirici arasındaki çalışmayı koordine etmenizi, devam etmekte olan çalışmaları üretim kodundan yalıtmanızı ve kaynak kodunuzu yedeklemenizi sağlar. Visual Studio, **Team Explorer** penceresinden Git ve Team Foundation Sürüm [Denetimi \(\) TFVC'yi](/azure/devops/repos/tfvc/) destekler.

::: moniker range="vs-2019"

![Takım Gezgini](media/vs2019-team-explorer.png "Visual Studio 2017 Takım Explorer")

::: moniker-end

::: moniker range="<=vs-2017"

![Takım Gezgini](media/vs2017-team-explorer.png "Visual Studio 2017 Takım Explorer")

::: moniker-end

Azure'daki repos'larla Git tümleştirmesi hakkında daha fazla bilgi için [bkz.](/azure/devops/repos/git/share-your-code-in-git-vs-2017) GitHub ile Git entegrasyonu hakkında daha fazla bilgi için [Visual Studio için GitHub Uzantısı'na](https://visualstudio.github.com/)bakın.

## <a name="obtain-libraries"></a>Kitaplıklar edinin

Üçüncü taraf kitaplıklarını elde etmek ve yüklemek için [vcpkg](../build/vcpkg.md) paket yöneticisini kullanın. Şu anda katalogda 900'den fazla açık kaynak kitaplık bulunmaktadır.

## <a name="create-user-interfaces-with-designers"></a>Tasarımcılarla kullanıcı arabirimleri oluşturma

Programınızda bir kullanıcı arabirimi varsa, düğmeler, liste kutuları ve benzeri denetimlerle hızla doldurmak için bir tasarımcı kullanabilirsiniz. Bir denetimi araç kutusu penceresinden sürükleyip tasarım yüzeyine bıraktığınızda, Visual Studio tüm denetimin çalışması için gereken kaynakları ve kodu oluşturur. Daha sonra görünüm ve davranışı özelleştirmek için kodu yazın.

![Tasarımcı ve Araç Kutusu](media/vs2017-toolbox-designer.png "Visual Studio 2017 Araç Kutusu ve Tasarımcısı")

Evrensel Windows Platformu uygulaması için kullanıcı arabirimi tasarımı hakkında daha fazla bilgi için [Tasarım ve Kullanıcı Arabirimi](https://developer.microsoft.com/windows/design)bölümüne bakın.

Bir MFC uygulaması için kullanıcı arabirimi oluşturma hakkında daha fazla bilgi için [MFC Masaüstü Uygulamaları'na](../mfc/mfc-desktop-applications.md)bakın. Win32 Windows programları hakkında daha fazla bilgi için [Windows Masaüstü Uygulamaları'na](../windows/windows-desktop-applications-cpp.md)bakın.

## <a name="write-code"></a>Kod yazma

Bir proje oluşturduktan sonra, tüm proje dosyaları **Çözüm Gezgini** penceresinde görüntülenir. *(Çözüm,* ilgili bir veya daha fazla proje için mantıksal bir kapsayıcıdır.) **Solution Explorer'da**.h veya .cpp dosyasına tıkladığınızda, dosya kod düzenleyicisinde açılır.

![Çözüm Gezgini ve kod düzenleyicisi](media/vs2017-solution-explorer-code-editor.png "Visual Studio 2017 Çözüm Explorer ve kod editörü")

Kod düzenleyicisi C++ kaynak kodu için özel bir sözcük işlemcisidir. Kodu daha okunabilir ve anlaşılması daha kolay hale getirmek için dil anahtar kelimelerini, yöntemini ve değişken adlarını ve kodunuzun diğer öğelerini renk kodlar. Ayrıca kodu yeniden düzenleme, farklı dosyalar arasında gezinme ve kodun nasıl yapılandırılacağını anlamak için araçlar sağlar. Daha fazla bilgi için [bkz.](../ide/writing-and-refactoring-code-cpp.md)

## <a name="add-and-edit-resources"></a>Kaynak ekleme ve bu kaynakları daha iyi bir şekilde dolandırın

Windows programı veya DLL genellikle iletişim, simgeler, görüntüler, yerelleştirilebilir dizeleri, sıçrama ekranları, veritabanı bağlantı dizeleri veya rasgele veriler gibi bazı *kaynaklar*içerir. Visual Studio, kaynak eklemek ve düzenlemek için araçlar içerir. Daha fazla bilgi için [kaynak dosyalarıyla çalışma](../windows/working-with-resource-files.md)bilgisine bakın.

## <a name="build-compile-and-link"></a>Yapı (derleme ve bağlantı)

Menü çubuğunda **Oluştur** > **Çözüm'ü** seçin veya bir projeyi derlemek ve bağlamak için **Ctrl+Shift+B** tuş kombinasyonunu girin. Yapı hataları ve uyarılar Hata Listesinde bildirilir (**Ctrl+\\, E**). **Çıkış** Penceresi (**Alt+2**) yapı süreci yle ilgili bilgileri gösterir.

![Çıktı Penceresi ve Hata Listesi](media/vs2017-output-error-list.png "Visual Studio 2017 Çıkış penceresi ve Hata Listesi")

Yapı yapılandırma hakkında daha fazla bilgi için bkz: Proje Özellikleri ve [Projelerle Çalışma](../build/working-with-project-properties.md) [ve sistem oluşturma.](../build/projects-and-build-systems-cpp.md)

Derleyiciyi (cl.exe) ve NMAKE ve LIB gibi diğer yapıyla ilgili bağımsız araçları doğrudan komut satırından da kullanabilirsiniz. Daha fazla bilgi için bkz: [Komut satırında C/C++ kodu oluştur](../build/building-on-the-command-line.md) ve [C/C++ Yapı Başvurusu.](../build/reference/c-cpp-building-reference.md)

## <a name="debug"></a>Hata ayıklama

**F5**tuşuna basarak hata ayıklamaya başlayabilirsiniz. Ayarlamış olduğunuz herhangi bir kesme noktasında yürütme duraklar **(F9**tuşuna basarak). Ayrıca, bir seferde kod bir satır **(F10)** üzerinden adım, değişkenlerin veya kayıtların değerlerini görüntülemek ve hatta bazı durumlarda kod değişiklikleri yapmak ve yeniden derleme olmadan hata ayıklama devam edebilirsiniz. Aşağıdaki resimde, yürütmenin kesme noktasında durdurulduğu bir hata ayıklama oturumu gösterilmektedir. Veri yapısı üyelerinin değerleri **İzleme Penceresi'nde**görünür.

![Hata ayıklama oturumu](media/vs2017-debug-watch.png "Visual Studio 2017 hata ayıklama oturumu")

Daha fazla bilgi için [Visual Studio'da Hata Ayıklama](/visualstudio/debugger/debugging-in-visual-studio)bölümüne bakın.

## <a name="test"></a>Test etme

Visual Studio, C++için Microsoft Unit Test Framework'ün yanı sıra Boost.Test, Google Test ve CTest desteğini içerir. **Test Gezgini** penceresinden testlerinizi çalıştırın:

![Test Gezgini](media/cpp-test-explorer-passed.png "Visual Studio 2017 Test Explorer")

Daha fazla bilgi için [bkz.](/visualstudio/test/unit-test-your-code) [Write unit tests for C/C++ in Visual Studio](/visualstudio/test/writing-unit-tests-for-c-cpp)

## <a name="analyze"></a>Çözümleme

Visual Studio, kaynak kodunuzdaki olası sorunları algılayabilen statik kod çözümleme araçları içerir. Bu [araçlar, C++ Temel Yönergeler](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md) kuralları denetleyicilerinin uygulanmasını içerir. Daha fazla bilgi [için C/C++ genel bakışı için Kod çözümlemesi'ne](/cpp/code-quality/code-analysis-for-c-cpp-overview)bakın.

## <a name="deploy-completed-applications"></a>Tamamlanan uygulamaları dağıtma

Microsoft Mağazası aracılığıyla hem geleneksel masaüstü uygulamalarını hem de UWP uygulamalarını müşterilere dağıtabilirsiniz. CRT'nin dağıtımı arka planda otomatik olarak işlenir. Daha fazla bilgi için windows [uygulamaları ve oyunları yayımla'](/windows/uwp/publish/)ya bakın.

Yerel bir C++ masaüstünü başka bir bilgisayara da dağıtabilirsiniz. Daha fazla bilgi için Bkz. [Masaüstü Uygulamalarını Dağıtma.](../windows/deploying-native-desktop-applications-visual-cpp.md)

C++/CLI programı dağıtma hakkında daha fazla bilgi için [Geliştiriciler için Dağıtım Kılavuzu'na](/dotnet/framework/deployment/deployment-guide-for-developers)bakın,

## <a name="next-steps"></a>Sonraki adımlar

Bu tanıtım makalelerinden biriyle birlikte görsel stüdyodaha fazla aşağıdaki keşfedin:

> [!div class="nextstepaction"]
> [Kod düzenleyicisini kullanmayı öğrenin](/visualstudio/get-started/tutorial-editor)

> [!div class="nextstepaction"]
> [Projeler ve çözümler hakkında bilgi edinin](/visualstudio/get-started/tutorial-projects-solutions)

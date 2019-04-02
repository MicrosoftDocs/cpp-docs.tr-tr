---
title: Visual Studio'da C++ geliştirme genel bakış
description: Visual Studio IDE Windows, Linux, Android ve iOS bir kod Düzenleyicisi, hata ayıklayıcı, test çerçeveleri, statik çözümleyiciler ve başka programlama araçları ile C++ geliştirme destekler.
ms.date: 03/08/2019
helpviewer_keywords:
- Visual C++, development tools
author: corob-msft
ms.author: corob
ms.openlocfilehash: 207d99419499187715cf9088652d64b79b7ba34d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787883"
---
# <a name="overview-of-c-development-in-visual-studio"></a>Visual Studio'da C++ geliştirme genel bakış

Visual Studio tümleşik geliştirme ortamı (IDE) parçası olarak, Microsoft C++ (MSVC) birçok windows ve diğer diller ortak Araçlar paylaşır. Bu da dahil olmak üzere birçok **Çözüm Gezgini**, Kod Düzenleyicisi ve hata ayıklayıcı altında belgelenen [Visual Studio IDE](/visualstudio/get-started/visual-studio-ide). Genellikle, paylaşılan bir aracı veya pencere biraz farklı bir özellik kümesi için C++ JavaScript veya .NET dilleri için vardır. Bazı windows veya araçları yalnızca Visual Studio Professional veya Visual Studio Enterprise sürümlerinde kullanılabilir.

Visual Studio IDE'de paylaşılan araçlara ek olarak, MSVC yerel kod geliştirme için özel olarak çeşitli araçları vardır. Bu araçlar, bu makalede de listelenir. Hangi Araçlar Visual Studio'nun her sürümünde bir listesi için bkz [C++ Araçları ve özellikleri Visual Studio sürümlerinde](visual-cpp-tools-and-features-in-visual-studio-editions.md).

## <a name="create-projects"></a>Projeleri oluşturma

A *proje* temel bir kaynak kodu dosyaları ve yürütülebilir bir dosyada yerleşik görüntüleri veya veri dosyaları gibi kaynakları kümesidir.

Visual Studio 2017, herhangi bir derleme sistemi veya tam IntelliSense, göz atma ve hata ayıklama desteği ile kullanmak istediğiniz özel derleme araçları için destek sağlar:

- **MSBuild** yerel yapı sistemi için Visual Studio. Seçtiğinizde, **dosya** > **yeni** > **proje** birçok farklı MSBuild'in gördüğünüz ana menüden *proje şablonları*  hızlıca farklı türde C++ uygulamalar geliştirmeye başlamanıza edinin.

   ![Proje şablonları](media/vs2017-new-project.png "Visual Studio 2017 yeni proje iletişim kutusu")

   Genel olarak, CMake veya başka bir proje sistemi kullanmak için belirli bir neden olmadığı sürece, bu şablonlardan yeni projeler için kullanmanız gerekir. Bazı projeler sahip bir *Sihirbazı* , size yeni bir proje oluşturma işleminde size adım adım. Daha fazla bilgi için [oluşturma ve yönetme MSBuild tabanlı projeler](../build/creating-and-managing-visual-cpp-projects.md).

- **CMake** platformlar arası C++ iş yükünde ile masaüstü geliştirme yüklediğinizde Visual Studio IDE'ye tümleşik sistemi yapı. Daha fazla bilgi için [Visual Studio'daki CMake projeleri](../build/cmake-projects-in-visual-studio.md).
- Aracılığıyla dosyaları gevşek koleksiyonu dahil olmak üzere tüm diğer C++ yapı sistemini, desteklenen **Klasör Aç** özelliği. Derleme programınızı çağırmak ve hata ayıklama oturumları yapılandırmak için basit JSON dosyalarını oluşturduğunuz. Daha fazla bilgi için [C++ açık klasörü projelerde](../build/open-folder-projects-cpp.md).

## <a name="add-to-source-control"></a>Kaynak denetimine Ekle

Kaynak denetimi işi birden fazla Geliştirici arasında devam eden üretim kodundan yalıtmak ve kaynak kodunuzu yedekleme sağlar. Visual Studio, Git destekler ve [Team Foundation sürüm denetimi \(TFVC\) ](/azure/devops/repos/tfvc/) aracılığıyla kendi **Takım Gezgini** penceresi.

![Takım Gezgini](media/vs2017-team-explorer.png "Visual Studio 2017 Takım Gezgini")

Azure'da depolarla Git tümleştirmesi hakkında daha fazla bilgi için bkz: [Azure depoları Git ile Visual Studio 2017 ile kodunuzu paylaşmaya](/azure/devops/repos/git/share-your-code-in-git-vs-2017). GitHub ile Git tümleştirmesi hakkında daha fazla bilgi için bkz. [Visual Studio için GitHub uzantısı](https://visualstudio.github.com/).

## <a name="create-user-interfaces-with-designers"></a>Tasarımcılar ile kullanıcı arabirimleri oluşturun

Programınız bir kullanıcı arabirimi varsa, hızlı bir şekilde bu düğmeler, liste kutuları gibi denetimleri ile vb. doldurmak için bir tasarımcı kullanabilirsiniz. Bir denetimi araç penceresinden sürükleyip tasarım yüzeyine bırakın, Visual Studio kaynakları ve her hale getirmeniz için gereken kod oluşturur. Ardından görünümünü ve davranışını özelleştirmek için kod yazabilir.

![Tasarımcı ve araç kutusu](media/vs2017-toolbox-designer.png "Tasarımcısı ve Visual Studio 2017 araç")

Bir evrensel Windows platformu uygulaması için bir kullanıcı arabirimi tasarlama hakkında daha fazla bilgi için bkz. [tasarım ve UI](https://developer.microsoft.com/windows/design).

Bir MFC uygulaması için bir kullanıcı arabirimi oluşturma hakkında daha fazla bilgi için bkz. [MFC Masaüstü uygulamaları](../mfc/mfc-desktop-applications.md). Win32 Windows programlar hakkında daha fazla bilgi için bkz: [Windows Masaüstü uygulamaları](../windows/windows-desktop-applications-cpp.md).

## <a name="write-code"></a>Kod yazma

Bir projeyi oluşturduktan sonra tüm proje dosyaları içinde görüntülenen **Çözüm Gezgini** penceresi. (A *çözüm* ilgili daha fazla proje ya da bir mantıksal bir kapsayıcıdır.) Tıkladığınızda bir .h veya .cpp dosyada **Çözüm Gezgini**, dosya Kod düzenleyicisinde açılır.

![Çözüm Gezgini ve Kod Düzenleyicisi](media/vs2017-solution-explorer-code-editor.png "Visual Studio 2017 Çözüm Gezgini ve Kod Düzenleyicisi")

Özelleştirilmiş bir sözcük işlemcisi C++ kaynak kodu için kod düzenleyicisidir. Dil anahtar sözcükleri, yöntemi ve değişken adları ve diğer öğelerin kodunu daha okunabilir ve daha kolay anlaşılır hale getirmek için kodunuzu renkli kodlarla gösterir.

Daha fazla bilgi için [yazma ve yeniden düzenleme kodunda](../ide/writing-and-refactoring-code-cpp.md).

## <a name="add-and-edit-resources"></a>Ekleme ve kaynakları düzenleme

Terim *kaynak* iletişim kutuları, simgeler, görüntü, yerelleştirilebilir dize, Karşılama ekranları, veritabanı bağlantı dizelerini veya yürütülebilir dosya olarak eklemek istediğiniz herhangi bir rastgele veri gibi öğeleri içerir.

Ekleme ve kaynakları yerel Masaüstü C++ projelerinde düzenleme hakkında daha fazla bilgi için bkz. [kaynak dosyalarıyla çalışma](../windows/working-with-resource-files.md).

## <a name="build-compile-and-link"></a>Derleme (derleme ve bağlama)

Seçin **derleme** > **Çözümü Derle** menüsünde çubuk veya derlemek ve bir proje bağlamak için Ctrl + Shift + B tuş bileşimi girin. Derleme hataları ve uyarıları hata olarak raporlanır (Ctrl +\\, E). **Çıkış** penceresi (Alt + 2), yapı işlemi hakkında bilgi gösterir.

![Çıkış penceresi ve hata listesi](media/vs2017-output-error-list.png "Visual Studio 2017 çıktı penceresi ve hata listesi") MSBuild yapılandırmaları hakkında daha fazla bilgi için bkz. [Working with Project Properties](../build/working-with-project-properties.md) ve [Projeler ve yapı sistemi](../build/projects-and-build-systems-cpp.md).

Ayrıca, derleyici (cl.exe) ve diğer birçok derlemeyle ilgili tek başına Araçlar NMAKE ve LIB gibi komut satırından doğrudan da kullanabilirsiniz. Daha fazla bilgi için [komut satırında C/C++ derleme kodu](../build/building-on-the-command-line.md) ve [C/C++ oluşturma başvurusu](../build/reference/c-cpp-building-reference.md).

## <a name="debug"></a>Hata ayıklama

Tuşuna basarak hata ayıklama Başlat **F5**. Yürütme, ayarladığınız tüm kesme noktalarında duraklatır. Ayrıca bir defada bir satır kodda adım adım, değişkenlerini veya kayıtlarını, değerlerini görüntüleyebilir ve bile bazı durumlarda, kodda değişiklik yapmak ve yeniden derleme olmadan hata ayıklamaya devam et. Aşağıdaki çizim, yürütme bir kesme noktasına durdurulur hata ayıklama oturumu gösterir. Veri yapısı üyelerinin değerlerini görülebilir **Gözcü penceresi**.

![Hata ayıklama oturumu](media/vs2017-debug-watch.png "hata ayıklama oturumu Visual Studio 2017")

Daha fazla bilgi için [Visual Studio'da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio).

## <a name="test"></a>Test

Visual Studio, hem yerel C++ ve C + için birim testi çerçevelerini içerir +/ CLI. Boost.Test, Google Test ve CTest de desteklenir. Kullanarak bu testleri **Test Gezgini** penceresi:

![Test Gezgini](media/cpp-test-explorer-passed.png "Visual Studio 2017 Test Gezgini")

Daha fazla bilgi için [doğrulama kodunu kullanarak birim testleri tarafından](/visualstudio/test/unit-test-your-code) ve [Visual Studio'da C/C++ için birim testleri yazma](/visualstudio/test/writing-unit-tests-for-c-cpp).

## <a name="analyze"></a>Çözümle

Visual Studio, kaynak kodda olası sorunları algılayabilir statik kod çözümleme araçları içerir. Bu araçlar uygulaması içerir [C++ temel yönergeleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md) kareler kuralları. Daha fazla bilgi için [Code analysis for C/C++ genel bakış](/visualstudio/code-quality/code-analysis-for-c-cpp-overview).

## <a name="deploy-completed-applications"></a>Tamamlanan uygulamalar dağıtma

Microsoft Store aracılığıyla müşterilere hem geleneksel masaüstü uygulamaları ve UWP uygulamaları dağıtabilirsiniz. CRT dağıtımını arka planda otomatik olarak gerçekleştirilir. Daha fazla bilgi için [yayımlama Windows uygulamaları ve oyunları](/windows/uwp/publish/).

De yerel C++ Masaüstü dağıtabilirsiniz başka bir bilgisayar için daha fazla bilgi için bkz. [Masaüstü uygulamaları dağıtma](../windows/deploying-native-desktop-applications-visual-cpp.md).

C + dağıtma hakkında daha fazla bilgi için +/ CLI programını bkz [geliştiriciler için Dağıtım Kılavuzu](/dotnet/framework/deployment/deployment-guide-for-developers),

## <a name="next-steps"></a>Sonraki adımlar

Bu tanıtıcı makaleler biriyle boyunca izleyerek daha fazla Visual Studio'ı keşfedin:

> [!div class="nextstepaction"]
> [Kod Düzenleyicisi'ni kullanmayı öğrenin](/visualstudio/get-started/tutorial-editor)

> [!div class="nextstepaction"]
> [Projeler ve çözümler hakkında bilgi edinin](/visualstudio/get-started/tutorial-projects-solutions)

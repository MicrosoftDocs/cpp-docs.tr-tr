---
title: IDE ve Visual C++ geliştirme araçları | Microsoft Docs
description: Visual Studio IDE Windows, Linux, Android ve iOS bir kod Düzenleyicisi, hata ayıklayıcı, test çerçeveleri, statik çözümleyiciler ve başka programlama araçları ile C++ geliştirme destekler.
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, development tools
ms.assetid: 56eabafb-1956-4f0f-bec5-29b887763559
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 31b9c0c8668ec16d84ad84627eb73a0f406eb21e
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328382"
---
# <a name="ide-and-compiler-tools-for-visual-c-development"></a>IDE ve Visual C++ geliştirme derleme araçları

Visual Studio tümleşik geliştirme ortamı (IDE) parçası olarak, Microsoft Visual C++ (MSVC) birçok windows ve diğer diller ortak Araçlar paylaşır. Bu da dahil olmak üzere birçok **Çözüm Gezgini**, Kod Düzenleyicisi ve hata ayıklayıcı altında belgelenen [Visual Studio IDE](/visualstudio/ide/visual-studio-ide). Genellikle, paylaşılan bir aracı veya pencere biraz farklı bir özellik kümesi için C++ JavaScript veya .NET dilleri için vardır. Bazı windows veya araçları yalnızca Visual Studio Professional veya Visual Studio Enterprise sürümlerinde kullanılabilir.

Visual Studio IDE'de paylaşılan araçlara ek olarak, MSVC yerel kod geliştirme için özel olarak çeşitli araçları vardır. Bu araçlar, bu makalede de listelenir. Hangi Araçlar Visual Studio'nun her sürümünde bir listesi için bkz [Visual C++ Araçları ve özellikleri Visual Studio sürümlerinde](visual-cpp-tools-and-features-in-visual-studio-editions.md).

## <a name="create-projects"></a>Projeleri oluşturma

A *proje* temel bir kaynak kodu dosyaları ve yürütülebilir bir dosyada yerleşik görüntüleri veya veri dosyaları gibi kaynakları kümesidir. 

Visual Studio 2015, MSBuild projeleri için destek sağlar. Qt veya CMake gibi diğer yapı sistemleri için Visual Studio uzantıları karşıdan yükleyebilirsiniz.

Visual Studio 2017, herhangi bir derleme sistemi veya tam IntelliSense, göz atma ve hata ayıklama desteği ile kullanmak istediğiniz özel derleme araçları için destek sağlar:

- **MSBuild** yerel yapı sistemi için Visual Studio. Seçtiğinizde, **dosya** > **yeni** > **proje** birçok farklı MSBuild'in gördüğünüz ana menüden *proje şablonları*  hızlıca farklı türde C++ uygulamalar geliştirmeye başlamanıza edinin.

   ![Proje şablonları](media/vs2017-new-project.png "Visual Studio 2017 yeni proje iletişim kutusu")

   Genel olarak, CMake veya başka bir proje sistemi kullanmak için belirli bir neden olmadığı sürece, bu şablonlardan yeni projeler için kullanmanız gerekir. Bazı projeler sahip bir *Sihirbazı* , size yeni bir proje oluşturma işleminde size adım adım. Daha fazla bilgi için [oluşturma ve yönetme MSBuild tabanlı projeler](creating-and-managing-visual-cpp-projects.md).

- **CMake** platformlar arası C++ iş yükünde ile masaüstü geliştirme yüklediğinizde Visual Studio IDE'ye tümleşik sistemi yapı. Daha fazla bilgi için [Visual C++'da CMake projeleri](cmake-tools-for-visual-cpp.md).
- Aracılığıyla dosyaları gevşek koleksiyonu dahil olmak üzere tüm diğer C++ yapı sistemini, desteklenen **Klasör Aç** özelliği. Derleme programınızı çağırmak ve hata ayıklama oturumları yapılandırmak için basit JSON dosyalarını oluşturduğunuz. Daha fazla bilgi için [Klasör Aç Visual C++ projelerinde](non-msbuild-projects.md).

## <a name="add-to-source-control"></a>Kaynak denetimine Ekle

Kaynak denetimi işi birden fazla Geliştirici arasında devam eden üretim kodundan yalıtmak ve kaynak kodunuzu yedekleme sağlar. Visual Studio, Git destekler ve [Team Foundation sürüm denetimi \(TFVC\) ](/azure/devops/repos/tfvc/) aracılığıyla kendi **Takım Gezgini** penceresi.

![Takım Gezgini](media/vs2017-team-explorer.png "Visual Studio 2017 Takım Gezgini")

Azure'da depolarla Git tümleştirmesi hakkında daha fazla bilgi için bkz: [Azure depoları Git ile Visual Studio 2017 ile kodunuzu paylaşmaya](/azure/devops/repos/git/share-your-code-in-git-vs-2017). GitHub Git tümleştirme hakkında bilgi için [Visual Studio için GitHub uzantısı](https://visualstudio.github.com/).

## <a name="create-user-interfaces-with-designers"></a>Tasarımcılar ile kullanıcı arabirimleri oluşturun

Programınız bir kullanıcı arabirimi varsa, hızlı bir şekilde bu düğmeler, liste kutuları gibi denetimleri ile vb. doldurmak için bir tasarımcı kullanabilirsiniz. Bir denetimi araç penceresinden sürükleyip tasarım yüzeyine bırakın, Visual Studio kaynakları ve her hale getirmeniz için gereken kod oluşturur. Ardından görünümünü ve davranışını özelleştirmek için kod yazabilir.

![Tasarımcı ve araç kutusu](media/vs2017-toolbox-designer.png "Tasarımcısı ve Visual Studio 2017 araç")

Bir evrensel Windows platformu uygulaması için bir kullanıcı arabirimi tasarlama hakkında daha fazla bilgi için bkz. [tasarım ve UI](https://developer.microsoft.com/windows/design).

Bir MFC uygulaması için bir kullanıcı arabirimi oluşturma hakkında daha fazla bilgi için bkz. [MFC Masaüstü uygulamaları](../mfc/mfc-desktop-applications.md). Win32 Windows programlar hakkında daha fazla bilgi için bkz: [Windows Masaüstü uygulamaları](../windows/windows-desktop-applications-cpp.md).

## <a name="write-code"></a>Kod yazma

Bir projeyi oluşturduktan sonra tüm proje dosyaları içinde görüntülenen **Çözüm Gezgini** penceresi. (A *çözüm* ilgili daha fazla proje ya da bir mantıksal bir kapsayıcıdır.) Tıkladığınızda bir .h veya .cpp dosyada **Çözüm Gezgini**, dosya Kod düzenleyicisinde açılır. 

![Çözüm Gezgini ve Kod Düzenleyicisi](media/vs2017-solution-explorer-code-editor.png "Visual Studio 2017 Çözüm Gezgini ve Kod Düzenleyicisi")

Özelleştirilmiş bir sözcük işlemcisi C++ kaynak kodu için kod düzenleyicisidir. Dil anahtar sözcükleri, yöntemi ve değişken adları ve diğer öğelerin kodunu daha okunabilir ve daha kolay anlaşılır hale getirmek için kodunuzu renkli kodlarla gösterir.

Daha fazla bilgi için [yazma ve yeniden düzenleme kodunda](writing-and-refactoring-code-cpp.md).

## <a name="add-and-edit-resources"></a>Ekleme ve kaynakları düzenleme

Terim *kaynak* iletişim kutuları, simgeler, görüntü, yerelleştirilebilir dize, Karşılama ekranları, veritabanı bağlantı dizelerini veya yürütülebilir dosya olarak eklemek istediğiniz herhangi bir rastgele veri gibi öğeleri içerir.

Ekleme ve kaynakları yerel Masaüstü C++ projelerinde düzenleme hakkında daha fazla bilgi için bkz. [kaynak dosyalarıyla çalışma](../windows/working-with-resource-files.md).

## <a name="build-compile-and-link"></a>Derleme (derleme ve bağlama)

Seçin **derleme** > **Çözümü Derle** menüsünde çubuk veya derlemek ve bir proje bağlamak için Ctrl + Shift + B tuş bileşimi girin. Derleme hataları ve uyarıları hata olarak raporlanır (Ctrl +\\, E). **Çıkış** penceresi (Alt + 2), yapı işlemi hakkında bilgi gösterir.

![Çıkış penceresi ve hata listesi](media/vs2017-output-error-list.png "Visual Studio 2017 çıktı penceresi ve hata listesi") MSBuild yapılandırmaları hakkında daha fazla bilgi için bkz. [Working with Project Properties](working-with-project-properties.md) ve [Visual Studio'da C++ projeleri derleme](building-cpp-projects-in-visual-studio.md).

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

De yerel C++ Masaüstü dağıtabilirsiniz başka bir bilgisayar için daha fazla bilgi için bkz. [Masaüstü uygulamaları dağıtma](deploying-native-desktop-applications-visual-cpp.md).

C + dağıtma hakkında daha fazla bilgi için +/ CLI programını bkz [geliştiriciler için Dağıtım Kılavuzu](/dotnet/framework/deployment/deployment-guide-for-developers),

## <a name="related-articles"></a>İlgili Makaleler

|||
|-|-|
|[Visual Studio Sürümlerinde Visual C++ Araçları ve Özellikleri](visual-cpp-tools-and-features-in-visual-studio-editions.md)|Çeşitli Visual Studio sürümlerinde hangi özelliklerin kullanılabilir gösterir.|
|[MSBuild tabanlı projeler oluşturma ve yönetme](creating-and-managing-visual-cpp-projects.md)|C++ MSBuild tabanlı projeler Visual Studio ve oluşturmak ve bunları yönetmek nasıl açıklayan diğer makalelere bağlantılar genel bir bakış sağlar.|
|[Visual C++'da CMake projeleri](cmake-tools-for-visual-cpp.md).|CMake veya diğer MSBuild olmayan projeler Visual C++'ta nasıl oluşturulduğu açıklanır.|
|[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)|C++ projeleri nasıl oluşturulduğu açıklanır.|
|[Masaüstü uygulamalarını dağıtma](deploying-native-desktop-applications-visual-cpp.md)|C++ uygulamaları ve ayrıntılı dağıtım açıklayan diğer makalelere bağlantılar dağıtımına genel bir bakış sunar.|
|[Visual C++ Taşıma ve Yükseltme Kılavuzu](../porting/visual-cpp-porting-and-upgrading-guide.md)|Visual Studio'nun önceki sürümlerinde oluşturulan C++ uygulamalarını yükseltme ve ayrıca Visual Studio dışındaki araçlarla oluşturulmuş uygulamaları geçirme hakkında ayrıntılı bilgi.|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual c++ in Visual Studio ve Visual C++ belgelerinin geri kalanı için bağlantıları anahtar özelliklerini açıklar.|

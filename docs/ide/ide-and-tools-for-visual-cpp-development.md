---
title: IDE ve Visual C++ geliştirme araçları | Microsoft Docs
ms.custom: ''
ms.date: 06/02/2018
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
ms.openlocfilehash: df30bdea71a890eed25f546a53e7f329fa330762
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2018
ms.locfileid: "43132026"
---
# <a name="ide-and-tools-for-visual-c-development"></a>Visual C++ geliştirme araçları ve IDE

Visual Studio tümleşik geliştirme ortamı (IDE) parçası olarak, Microsoft Visual C++ (MSVC) birçok windows ve diğer diller ortak Araçlar paylaşır. Bu da dahil olmak üzere birçok **Çözüm Gezgini**, Kod Düzenleyicisi ve hata ayıklayıcı altında belgelenen [Visual Studio IDE](/visualstudio/ide/visual-studio-ide). Genellikle, paylaşılan bir aracı veya pencere biraz farklı bir özellik kümesi için C++ Javascript veya .NET dilleri için vardır. Bazı windows veya araçları yalnızca Visual Studio Pro veya Visual Studio Enterprise kullanılabilir.

Visual Studio IDE'de paylaşılan araçlara ek olarak, MSVC yerel kod geliştirme için özel olarak çeşitli araçları vardır. Bu araçlar, bu makalede de listelenir. Hangi Araçlar Visual Studio'nun her sürümünde bir listesi için bkz [Visual C++ Araçları ve özellikleri Visual Studio sürümlerinde](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md).

## <a name="creating-a-solution-and-projects"></a>Çözüm ve projeleri oluşturma

A *proje* temel bir kaynak kodu dosyaları ve yürütülebilir bir dosyada yerleşik görüntüleri veya veri dosyaları gibi kaynakları kümesidir. 

Visual Studio 2015, MSBuild projeleri için destek sağlar. Qt veya CMake gibi diğer yapı sistemleri için Visual Studio uzantıları karşıdan yükleyebilirsiniz.

Visual Studio 2017, herhangi bir derleme sistemi veya tam IntelliSense, göz atma ve hata ayıklama desteği ile kullanmak istediğiniz özel derleme araçları için destek sağlar:

- MSBuild Visual Studio için yerel derleme sistemi ve genellikle Evrensel Windows Platformu (UWP) uygulamaları veya MFC veya ATL'yi kullanan eski Windows Masaüstü uygulamaları için en iyi seçenek ise C++ MSBuild tabanlı projeler hakkında daha fazla bilgi için bkz. [oluşturma ve yönetme MSBuild tabanlı projeler](creating-and-managing-visual-cpp-projects.md).
- CMake, platformlar arası derleme Masaüstü uygulama geliştirme ile C++ iş yükünü yüklediğinizde, Visual Studio IDE'ye tümleşik sistemi ' dir. Daha fazla bilgi için [Visual C++'da CMake projeleri](cmake-tools-for-visual-cpp.md).
- Dosyaları, gevşek koleksiyonu dahil olmak üzere tüm diğer C++ derleme sistemi, Klasör Aç özelliği aracılığıyla desteklenir. Derleme programınızı çağırmak ve hata ayıklama oturumları yapılandırmak için basit JSON dosyalarını oluşturduğunuz. Daha fazla bilgi için [C++ kodunuzu Visual Studio'ya taşıyın](https://blogs.msdn.microsoft.com/vcblog/2017/04/14/bring-your-cpp-code-to-visual-studio/).

### <a name="project-templates-msbuild"></a>Proje şablonları (MSBuild)

Visual Studio, MSBuild tabanlı projeler için birkaç şablon ile birlikte gelir; Bu şablonlar, başlatıcı kodunu ve çeşitli temel program türleri için gerekli olan ayarları içerir. Genellikle seçerek başlayın **dosya** > **yeni proje** proje şablonundan bir proje oluşturmak için ardından bu projeye yeni kaynak kodu dosyaları ekleyin veya sağlanan dosyalarında kodlamaya başlayın. C++ projeleri ve proje sihirbazları özgü bilgiler için bkz: [oluşturma ve yönetme, Visual C++ projeleri](../ide/creating-and-managing-visual-cpp-projects.md).

### <a name="application-wizards-msbuild"></a>Uygulama sihirbazları (MSBuild)

Visual Studio seçtiğinizde bu sihirbazlar için bazı MSBuild proje türleri sağlar **dosya** > **yeni proje**. Sihirbaz, yeni proje oluşturma işleminde size adım adım yol gösterir. Bu, birçok seçenekler ve ayarlar olan proje türleri için kullanışlıdır. Daha fazla bilgi için [oluşturma Masaüstü projeleri tarafından uygulama sihirbazlarını kullanma](../ide/creating-desktop-projects-by-using-application-wizards.md).

## <a name="creating-user-interfaces-with-designers-msbuild"></a>Kullanıcı arabirimlerinin (MSBuild) tasarımcılar ile oluşturma

Programınız bir kullanıcı arabirimi varsa, ilk görevi bu düğmeler, liste kutuları gibi denetimler ve benzeri doldurmak üzere biridir. Visual Studio, bir görsel tasarım yüzeyi ve C++ uygulaması her özellik için bir araç içerir. Oluşturmakta olduğunuz uygulamanın türü ne olursa olsun, temel aynı olur: bir denetimi araç penceresinden sürükleyip istenen konumundan tasarım yüzeyine bırakın. Arka planda, Visual Studio kaynakları ve her hale getirmeniz için gereken kod oluşturur. Ardından, görünümünü ve davranışını özelleştirin veya denetimlerin verilerle doldurulması için kodu yazın.

Bir evrensel Windows platformu uygulaması için bir kullanıcı arabirimi tasarlama hakkında daha fazla bilgi için bkz. [tasarım ve UI](https://developer.microsoft.com/en-us/windows/design).

Bir MFC uygulaması için bir kullanıcı arabirimi oluşturma hakkında daha fazla bilgi için bkz. [MFC Masaüstü uygulamaları](../mfc/mfc-desktop-applications.md). Win32 Windows programlar hakkında daha fazla bilgi için bkz: [Windows Masaüstü uygulamaları](../windows/windows-desktop-applications-cpp.md).

## <a name="writing-and-editing-code"></a>Yazma ve kod düzenleme

### <a name="semantic-colorization"></a>Semantik renklendirme

Bir projeyi oluşturduktan sonra tüm proje dosyaları içinde görüntülenen **Çözüm Gezgini** penceresi. Tıkladığınızda bir .h veya .cpp dosyada **Çözüm Gezgini**, dosya Kod düzenleyicisinde açılır. Özelleştirilmiş bir sözcük işlemcisi C++ kaynak kodu için kod düzenleyicisidir. Dil anahtar sözcükleri, yöntemi ve değişken adları ve diğer öğelerin kodunu daha okunabilir ve daha kolay anlaşılır hale getirmek için kodunuzu renkli kodlarla gösterir.

### <a name="intellisense"></a>IntelliSense

Kod Düzenleyicisi, IntelliSense birlikte bilinen bazı özellikleri de destekler. Bir yöntem gelin ve bunu temel bazı belgelerine bakın. Bir sınıf değişken adını yazdıktan sonra ve bir. veya ->, söz konusu sınıfın örnek üyeleri listesi görüntülenir. Bir sınıf adı yazarsanız ve ardından bir::, statik üye listesi görüntülenir. Bir sınıf veya yöntemin adını yazmaya başladığınızda, Kod Düzenleyicisi ' deyimini tamamlamak için öneriler sunar. Daha fazla bilgi için [IntelliSense kullanarak](/visualstudio/ide/using-intellisense).

### <a name="code-snippets"></a>Kod parçacıkları

IntelliSense kod parçacıkları, sık kullanılan oluşturmak için kullanabilirsiniz veya bir kısayol tuş vuruşu ile karmaşık kodu oluşturur. Daha fazla bilgi için [kod parçacıkları](/visualstudio/ide/code-snippets).

## <a name="navigating-code"></a>Kod gezinme

**Görünümü** menü kod dosyalarınızı geçici olarak gezinmek için birçok windows ve araçlarına erişim sağlar. Bu windows hakkında ayrıntılı bilgi için bkz: [Structure of Code görüntüleme](/visualstudio/ide/viewing-the-structure-of-code).

### <a name="solution-explorer"></a>Çözüm Gezgini

Visual Studio'nun tüm sürümleri kullanın **Çözüm Gezgini** projesindeki dosyalar arasında gezinmek için bölmesi. Sınıfları, dosyayı görüntülemek için bir .h veya .cpp dosyası simgesi genişletin. Bir sınıf üyelerini görmek için genişletin. Üye tanımı ya da uygulama dosyasına gitmek için çift tıklayın.

### <a name="class-view-and-code-definition-window"></a>Sınıf Görünümü ve kod tanımı penceresi

Kullanım **sınıf görünümü** bölmesinde kısmi sınıflar da dahil olmak üzere tüm dosyalardaki, ad alanlarını ve sınıfları görmek için. Her ad alanı veya sınıf üyeleri görebilir ve üye kaynak dosyada bu konuma gitmek için çift tıklayarak genişletebilirsiniz. Açarsanız **kod tanımı penceresi**, uygulama türü ve tanımı içinde seçtiğinizde görüntüleyebilirsiniz **sınıf görünümü**.

### <a name="object-browser"></a>Nesne Tarayıcısı

Kullanım **Nesne Tarayıcısı** Windows çalışma zamanı bileşenlerinde (.winmd dosyaları) tür bilgileri keşfetmek için .NET derlemelerini ve COM tür kitaplığı. Win32 DLL'leri ile kullanılmaz.

### <a name="go-to-definitiondeclaration"></a>Tanımı/bildirimine gidin

Kendi tanımına gitmek için tüm API adı veya üye değişkeni F12 tuşuna basın. Tanımı bir .winmd dosyasına (bir UWP veya Windows 8.x Store uygulaması) ise nesne tarayıcısında tür bilgisini seçmeniz gerekir. Ayrıca seçebilirsiniz **tanıma** veya **bildirimi Git** değişken veya türü adına sağ tıklayıp bağlam menüsünden seçeneği seçerek.

### <a name="find-all-references"></a>Tüm Başvuruları Bul

Bir kaynak kodu dosyası fare imleci bir tür veya yöntemi veya değişken adının üzerine sağ tıklayın ve seçin **tüm başvuruları Bul** türü kullanıldığı dosyası, proje veya çözümü her konum bir listesini döndürmek için. **Tüm başvuruları Bul** Akıllı ve diğer değişkenleri farklı kapsamda aynı ada sahip olsanız bile yalnızca aynı aynı değişken, bir örneğini döndürür.

## <a name="add-and-edit-resources--msbuild"></a>Ekleme ve düzenleme kaynakları (MSBuild)

Terim *kaynak* Visual Studio bağlamında Masaüstü proje iletişim kutuları, simgeler, yerelleştirilebilir dize, Karşılama ekranları, veritabanı bağlantı dizelerini ve dahil etmek istediğiniz herhangi bir rastgele veri gibi öğeleri içerir. yürütülebilir dosya.

Ekleme ve kaynakları yerel Masaüstü C++ projelerinde düzenleme hakkında daha fazla bilgi için bkz. [kaynak dosyalarıyla çalışma](../windows/working-with-resource-files.md).

## <a name="build-compile-and-link"></a>Derleme (derleme ve bağlama)

Seçin **derleme** > **Çözümü Derle** menüsünde çubuk veya derlemek ve bir proje bağlamak için Ctrl + Shift + B tuş bileşimi girin. Yürütülebilir kodu oluşturmak için Visual Studio kullanan [MSBuild](/visualstudio/msbuild/msbuild1) veya CMake veya her ortamı oluşturmak ayarladığınız aracılığıyla **Klasör Aç**. MSBuild projeleri için genel derleme seçenekleri altında ayarladığınız **Araçları** > **seçenekleri** > **projeler ve çözümler** ve özellikleri ayarlayabilirsiniz. altında belirli projelerin **proje** > **özellikleri**. Derleme hataları ve uyarıları hata olarak raporlanır (Ctrl +\\, E). MSBuild dışındaki projeleri Çözüm Gezgini'nde oluşturduğunuz JSON dosyaları ile yapılandırılır. İnovasyonunuz ne olursa olsun kullanın, sistem yapı **çıkış** penceresi (Alt + 2), yapı işlemi hakkında bilgi gösterir. MSBuild yapılandırmaları hakkında daha fazla bilgi için bkz. [Working with Project Properties](../ide/working-with-project-properties.md) ve [Visual Studio'da C++ proje oluşturma](../ide/building-cpp-projects-in-visual-studio.md).

Ayrıca, derleyici (cl.exe) ve diğer birçok derlemeyle ilgili tek başına Araçlar NMAKE ve LIB gibi komut satırından doğrudan da kullanabilirsiniz. Daha fazla bilgi için [komut satırında C/C++ derleme kodu](../build/building-on-the-command-line.md) ve [C/C++ oluşturma başvurusu](../build/reference/c-cpp-building-reference.md).

## <a name="test"></a>Test

Visual Studio, hem yerel C++ ve C + için birim test çerçevesi içerir +/ CLI. Daha fazla bilgi için [doğrulama kodunu kullanarak birim testleri tarafından](/visualstudio/test/unit-test-your-code) ve [yazma birim testleri için Microsoft birim testi çerçevesi ile C/C++ için C++](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)

## <a name="analyze"></a>Çözümle

Visual Studio statik kod çözümleme araçları için C++ uygulaması da dahil olmak üzere, içerir [C++ temel yönergeleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md) kareler kuralları. Daha fazla bilgi için [Code analysis for C/C++ genel bakış](/visualstudio/code-quality/code-analysis-for-c-cpp-overview).

## <a name="debug"></a>Hata ayıklama

Tuşuna basarak, programınızın hatalarını ayıklayabilir **F5** hata ayıklama, proje yapılandırması ayarlandığında. Hata ayıklarken kesme noktaları tuşlarına basarak ayarlayabilirsiniz **F9**, kodu adımlayın tuşuna basarak **F10**, kayıtları, belirtilen değişkenler ve değerleri görüntülemek ve hatta bazı durumlarda kodda değişiklik ve devam hata ayıklama olmadan yeniden derleniyor. Daha fazla bilgi için [Visual Studio'da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio).

## <a name="deploy-completed-applications"></a>Tamamlanan uygulamalar dağıtma

Bir UWP uygulaması Microsoft Store aracılığıyla müşterilere dağıttığınız **proje** > **Store** menü seçeneği. CRT dağıtımını arka planda otomatik olarak gerçekleştirilir. Daha fazla bilgi için [yayımlama Windows uygulamaları ve oyunları](/windows/uwp/publish/). 

C++ yerel bir masaüstü uygulamasını başka bir bilgisayara dağıttığınızda, uygulama ve uygulamanın bağlı olduğu kitaplık dosyalarını yüklemeniz gerekir. Evrensel C++ çalışma zamanı (UCRT)'ile bir uygulama dağıtmanın üç yolu vardır: merkezi dağıtım, yerel dağıtım ya da statik bağlama. Daha fazla bilgi için [Masaüstü uygulamaları dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md).

C + dağıtma hakkında daha fazla bilgi için +/ CLI programını bkz [geliştiriciler için Dağıtım Kılavuzu](/dotnet/framework/deployment/deployment-guide-for-developers),

## <a name="related-articles"></a>İlgili Makaleler

|||
|-|-|
|[Visual Studio Sürümlerinde Visual C++ Araçları ve Özellikleri](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)|Çeşitli Visual Studio sürümlerinde hangi özelliklerin kullanılabilir gösterir.|
|[MSBuild tabanlı projeler oluşturma ve yönetme](../ide/creating-and-managing-visual-cpp-projects.md)|C++ MSBuild tabanlı projeler Visual Studio ve oluşturmak ve bunları yönetmek nasıl açıklayan diğer makalelere bağlantılar genel bir bakış sağlar.|
|[Visual C++'da CMake projeleri](cmake-tools-for-visual-cpp.md).|CMake veya diğer MSBuild olmayan projeler Visual C++'ta nasıl oluşturulduğu açıklanır.|
|[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)|C++ projeleri nasıl oluşturulduğu açıklanır.|
|[Masaüstü uygulamalarını dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)|C++ uygulamaları ve ayrıntılı dağıtım açıklayan diğer makalelere bağlantılar dağıtımına genel bir bakış sunar.|
|[Visual C++ Taşıma ve Yükseltme Kılavuzu](../porting/visual-cpp-porting-and-upgrading-guide.md)|Visual Studio'nun önceki sürümlerinde oluşturulan C++ uygulamalarını yükseltme ve ayrıca Visual Studio dışındaki araçlarla oluşturulmuş uygulamaları geçirme hakkında ayrıntılı bilgi.|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual c++ in Visual Studio ve Visual C++ belgelerinin geri kalanı için bağlantıları anahtar özelliklerini açıklar.|

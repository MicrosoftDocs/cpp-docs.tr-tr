---
title: "IDE ve Visual C++ geliştirme araçları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, development tools
ms.assetid: 56eabafb-1956-4f0f-bec5-29b887763559
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b6ff3f709e5db16f06569ab3406cfef44cabf11
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="ide-and-tools-for-visual-c-development"></a>IDE ve Visual C++ geliştirme araçları

Çok sayıda windows ve diğer dilleri ortak araçları, Visual Studio tümleşik geliştirme ortamı (IDE) parçası olarak, Microsoft Visual C++ (MSVC) paylaşır. Bu da dahil olmak üzere birçok **Çözüm Gezgini**, kod düzenleyicisini ve hata ayıklayıcı altında belgelenen [Visual Studio IDE](/visualstudio/ide/visual-studio-ide). Genellikle, bir paylaşılan aracı ya da penceresini biraz farklı bir özellikler kümesi için C++ .NET dillerini veya Javascript için vardır. Bazı windows veya araçları yalnızca Visual Studio Pro veya Visual Studio Enterprise'da kullanılabilir.

Visual Studio IDE paylaşılan araçlarında yanı sıra MSVC özellikle yerel kod geliştirme için çeşitli araçlar vardır. Bu araçları Ayrıca bu makalede listelenmektedir. Hangi Araçlar her Visual Studio sürümünde bir listesi için bkz: [Visual C++ Araçları ve özelliklerinin Visual Studio sürümlerinde](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md).

## <a name="creating-a-solution-and-projects"></a>Çözüm ve proje oluşturma

A *proje* temelde kaynak kodu dosyaları ve kaynakları bir yürütülebilir dosyaya yerleşik görüntüleri veya veri dosyaları gibi kümesidir. Visual Studio 2017 herhangi bir yapı sistem veya göz atma ve hata ayıklama IntelliSense için tam destek ile kullanmak istediğiniz özel derleme araçları destekler:

- MSBuild Visual Studio için yerel yapı sistemi ve genellikle Evrensel Windows Platformu (UWP) uygulamaları veya MFC ya da ATL kullanan eski Windows Masaüstü uygulamaları için en iyi seçimdir. C++ MSBuild tabanlı projeler hakkında daha fazla bilgi için bkz: [oluşturma ve yönetme MSBuild tabanlı projeler](creating-and-managing-visual-cpp-projects.md).
- CMake bir platformlar arası derleme C++ yüküyle masaüstü geliştirme yüklediğinizde Visual Studio IDE içinde tümleşik sisteminin ' dir. Daha fazla bilgi için bkz: [CMake Visual C++ projelerinde](cmake-tools-for-visual-cpp.md).
- Dosyalar, gevşek topluluğu dahil olmak üzere diğer tüm C++ derleme sistemlere, Klasör Aç özelliği desteklenir. Yapı programınızı çağırma ve hata ayıklama oturumları yapılandırmak için basit JSON dosyaları oluşturun. Daha fazla bilgi için bkz: [C++ kodunuzu Visual Studio'ya Getir](https://blogs.msdn.microsoft.com/vcblog/2017/04/14/bring-your-cpp-code-to-visual-studio/).

### <a name="project-templates-msbuild"></a>Proje şablonları (MSBuild)

MSBuild tabanlı projeler için çeşitli şablonlar ile Visual Studio gelir; Bu şablonlar, başlatıcı kodu ve çeşitli temel program türlerini için gerekli ayarları içerir. Genellikle seçerek Başlat **dosya** > **yeni proje** bir proje şablonu bir proje oluşturmak için daha sonra bu projeye yeni kaynak kodu dosyaları ekleme veya sağlanan dosyalarında kod yazmaya başlayın. C++ projeleri ve proje sihirbazları özel bilgi için bkz: [oluşturma ve yönetme Visual C++ projeleri](../ide/creating-and-managing-visual-cpp-projects.md).

### <a name="application-wizards-msbuild"></a>Uygulama sihirbazları (MSBuild)

Visual Studio öğesini seçtiğinizde bu sihirbazlar için bazı MSBuild proje türleri sağlar **dosya** > **yeni proje**. Sihirbaz adım adım yeni proje oluşturma işleminde size kılavuzluk eder. Bu, çok sayıda seçeneklerini ve ayarlarını proje türleri için kullanışlıdır. Daha fazla bilgi için bkz: [oluşturma Masaüstü projeleri tarafından uygulama sihirbazlarını kullanma](../ide/creating-desktop-projects-by-using-application-wizards.md).

## <a name="creating-user-interfaces-with-designers-msbuild"></a>Kullanıcı arabirimleri (MSBuild) tasarımcılar ile oluşturma

Programınızın bir kullanıcı arabirimi varsa, ilk görevi bu düğmeleri, liste kutuları gibi denetimleri ile vb. doldurmak için biridir. Visual Studio, bir görsel tasarım yüzeyi ve C++ uygulaması her özellik için bir araç içerir. Oluşturduğunuz uygulama türünü olsun, temel aynı fikirdir: bir denetim araç kutusu penceresinden sürükleyip istediğiniz konuma tasarım yüzeyine bırakın. Arka planda, Visual Studio kaynaklar ve tüm çalışması için gerekli kod oluşturur. Ardından denetimlerini veri ile doldurma veya bunların görünümünü ve davranışını özelleştirmek için kod yazın.

Bir evrensel Windows Platform uygulaması için kullanıcı arabirimi tasarlama hakkında daha fazla bilgi için bkz: [tasarım ve kullanıcı Arabirimi](https://developer.microsoft.com/en-us/windows/design).

MFC uygulaması için kullanıcı arabirimi oluşturma hakkında daha fazla bilgi için bkz: [MFC Masaüstü uygulamaları](../mfc/mfc-desktop-applications.md). Win32 Windows programlar hakkında daha fazla bilgi için bkz: [Windows Masaüstü uygulamaları](../windows/windows-desktop-applications-cpp.md).

## <a name="writing-and-editing-code"></a>Yazma ve kod düzenleme

### <a name="semantic-colorization"></a>Anlam renklendirme

Bir proje oluşturduğunuzda, tüm proje dosyalarını görüntülenen **Çözüm Gezgini** penceresi. Tıkladığınızda bir .h veya .cpp dosyasında **Çözüm Gezgini**, Kod Düzenleyicisi'nde dosya açılır. Özelleştirilmiş bir sözcük işlemci C++ kaynak kodu için kod düzenleyicisidir. Dil anahtar sözcükleri, yöntemi ve değişken adları ve diğer öğelerin kodunu daha okunabilir ve anlaşılması daha kolay hale kodunuzun renkli kodlarla gösterir.

### <a name="intellisense"></a>Intellisense

Kod Düzenleyicisi birlikte IntelliSense bilinen çeşitli özellikler de destekler. Bir yöntem gelin ve bunu temel bazı belgelerine bakın. Bir sınıf değişken adını yazdıktan sonra ve bir. veya ->, bu sınıfın örnek üyelerin listesi görüntülenir. Bir sınıf adını yazın, ardından bir::, statik üyeler listesi görüntülenir. Bir sınıf veya yöntemin adını yazmaya başladığınızda, Kod düzenleyicisinde deyimini tamamlamak için öneriler sunar. Daha fazla bilgi için bkz: [kullanarak IntelliSense](/visualstudio/ide/using-intellisense).

### <a name="code-snippets"></a>Kod parçacıkları

IntelliSense kod parçacıkları yaygın olarak kullanılan oluşturmak için kullanabileceğiniz veya bir kısayol tuş vuruşu ile karmaşık kodu oluşturur. Daha fazla bilgi için bkz: [kod parçacıkları](/visualstudio/ide/code-snippets).

## <a name="navigating-code"></a>Kodda gezinme

**Görünüm** menü geçici kod dosyalarınızda gezinmek için erişim sağlar birçok windows ve araçları. Bu windows hakkında ayrıntılı bilgi için bkz: [kodunu yapısı görüntüleme](/visualstudio/ide/viewing-the-structure-of-code).

### <a name="solution-explorer"></a>Çözüm Gezgini

Visual Studio tüm sürümlerinde kullanmak **Çözüm Gezgini** proje dosyalarında arasında gezinmek için bölmesi. Dosya sınıfları görüntülemek için bir .h veya .cpp dosya simgesini genişletin. Üyelerini görmek için bir sınıf genişletin. Üye tanımı veya uygulama dosyasına gitmek için çift tıklayın.

### <a name="class-view-and-code-definition-window"></a>Sınıf Görünümü ve kod tanımı penceresi

Kullanım **sınıf görünümü** bölmesi ad alanları ve sınıfları kısmi sınıflar dahil olmak üzere tüm dosyalardaki, bkz. Her ad alanı veya kaynak dosyayı bu konuma gitmek için üye çift tıklayın ve üyelerini görmek için sınıf genişletebilirsiniz. Açarsanız **kod tanımı penceresi**, içinde seçtiğinizde tanım veya uygulama türü görüntüleyebilir **sınıf görünümü**.

### <a name="object-browser"></a>Nesne Tarayıcısı

Kullanım **Nesne Tarayıcısı** Windows çalışma zamanı bileşenleri (.winmd dosyaları) türü bilgileri keşfetmek için .NET derlemelerini ve COM kitaplıkları yazın. Win32 DLL'leri ile kullanılmaz.

### <a name="go-to-definitiondeclaration"></a>Tanımı/bildirimine gidin

Öğenin tanımına gitmek için herhangi bir API adı veya üye değişkeni üzerinde F12 tuşuna basın. Tanım dosyasında bir .winmd (bir UWP ya da Windows 8.x mağazası uygulaması) ise nesne tarayıcısında type Info seçmeniz gerekir. Ayrıca seçebilirsiniz **Tanıma Git** veya **bildirimi Git** değişken veya türü adına sağ tıklayıp bağlam menüsünden seçeneği seçerek.

### <a name="find-all-references"></a>Tüm Başvuruları Bul

Kaynak kodu dosyasının fare imleci ile bir türü veya yöntemi veya değişken adını sağ tıklatın ve seçin **tüm başvuruları Bul** türü kullanıldığı her konum listesi dosya, proje veya çözüm döndürmek için. **Tüm başvuruları Bul** Akıllı ve diğer değişkenleri farklı kapsamda aynı ada sahip olsa bile yalnızca aynı aynı değişkeni örneklerini döndürür.

## <a name="add-and-edit-resources--msbuild"></a>Ekleme ve düzenleme kaynakları (MSBuild)

Terim *kaynak* Visual Studio bağlamında Masaüstü projesi iletişim kutuları, simgeler, yerelleştirilebilir dizeler, başlangıç ekranında, veritabanı bağlantı dizelerini veya dahil etmek istediğiniz herhangi bir rastgele veri gibi öğeleri içerir. yürütülebilir dosya.

Ekleme ve yerel Masaüstü C++ projelerine kaynakları düzenleme hakkında daha fazla bilgi için bkz: [kaynak dosyalarıyla çalışma](../windows/working-with-resource-files.md).

## <a name="build-compile-and-link"></a>Derleme (derleme ve bağlantı)

Seçin **yapı** > **yapı çözümü** menüsünde çubuğunu ya da derlemek ve proje bağlamak için Ctrl + Shift + B tuş bileşimini girin. Yürütülebilir kod oluşturmak için Visual Studio kullanan [MSBuild](/visualstudio/msbuild/msbuild1) veya CMake veya belirlediğiniz başka bir yapı ortamı ayarladığınız aracılığıyla **Klasör Aç**. Genel Derleme seçenekleri altında ayarladığınız MSBuild projelerinde **Araçları** > **seçenekleri** > **projeler ve çözümler** ve özelliklerini ayarlama altında belirli projeler için **proje** > **özellikleri**. Derleme hataları ve uyarıları hata listesinde raporlanır (Ctrl +\\, E). MSBuild olmayan projeleri Çözüm Gezgini'nde oluşturduğunuz JSON dosyaları ile yapılandırılır. Ne olursa olsun, sistemi yapı **çıkış** penceresi (Alt + 2) oluşturma işlemi hakkında bilgi gösterir. MSBuild yapılandırmaları hakkında daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md) ve [Visual Studio'da C++ projeleri oluşturma](../ide/building-cpp-projects-in-visual-studio.md).

Derleyici (cl.exe) ve diğer birçok yapı ilgili tek başına Araçlar NMAKE ve LIB gibi doğrudan komut satırından da kullanabilirsiniz. Daha fazla bilgi için bkz: [komut satırında C/C++ derleme kodu](../build/building-on-the-command-line.md) ve [C/C++ oluşturma başvurusu](../build/reference/c-cpp-building-reference.md).

## <a name="test"></a>Test

Visual Studio içeren bir birim testi çerçevesi yerel C++ hem C + +/ CLI. Daha fazla bilgi için bkz: [kullanarak birim testlerini doğrulama kodla](/visualstudio/test/unit-test-your-code) ve [yazma birim C++ için Microsoft birim testi çerçevesi ile C/C++ için testleri](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)

## <a name="debug"></a>Hata ayıklama

Tuşlarına basarak programınızı ayıklayabilirsiniz **F5** Debug proje yapılandırmanızı ayarlandığında. Hata ayıklama kesme noktaları tuşlarına basarak ayarlayabilirsiniz sırada **F9**, basarak adım kodlarda **F10**, belirtilen değişkenler veya kasaların değerlerini görüntülemek ve bazı durumlarda kodda değişiklik ve bile devam yeniden derleme olmadan hata ayıklama. Daha fazla bilgi için bkz: [Visual Studio'da hata ayıklamayı](/visualstudio/debugger/debugging-in-visual-studio).

## <a name="deploy-completed-applications"></a>Tamamlanan uygulamaları dağıtma

Bir UWP uygulaması Microsoft Store aracılığıyla müşterilere dağıttığınız **proje** > **deposu** menü seçeneği. CRT dağıtımını otomatik olarak arka planda gerçekleştirilir. Daha fazla bilgi için bkz: [satış uygulamaları](http://go.microsoft.com/fwlink/p/?LinkId=262280).

Bir yerel C++ masaüstü uygulaması başka bir bilgisayara dağıtırken, uygulama ve uygulamanın bağımlı herhangi bir kitaplık dosyasını yüklemeniz gerekir. Evrensel C++ çalışma zamanı (UCRT)'bir uygulama ile dağıtmak için üç yolu vardır: merkezi dağıtım, yerel dağıtım veya statik bağlama. Daha fazla bilgi için bkz: [Masaüstü uygulamaları dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md).

C + dağıtma hakkında daha fazla bilgi için +/ CLI programını bkz [geliştiriciler için Dağıtım Kılavuzu](/dotnet/framework/deployment/deployment-guide-for-developers),

## <a name="related-articles"></a>İlgili Makaleler

|||
|-|-|
|[Visual Studio Sürümlerinde Visual C++ Araçları ve Özellikleri](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)|Hangi özelliklerin Visual Studio çeşitli sürümlerinde kullanılabilir olduğunu gösterir.|
|[MSBuild tabanlı projeler oluşturma ve yönetme](../ide/creating-and-managing-visual-cpp-projects.md)|C++ MSBuild tabanlı projeler Visual Studio ve bağlantılar oluşturmak ve bunları yönetmek nasıl açıklayan diğer makaleler için genel bir bakış sağlar.|
|[Visual C++ projelerinde CMake](cmake-tools-for-visual-cpp.md).|CMake veya diğer MSBuild olmayan projeleri Visual C++'ta nasıl oluşturulacağını açıklar.|
|[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)|C++ projeleri derleme açıklar.|
|[Masaüstü uygulamaları dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)|C++ uygulamaları ve ayrıntılı dağıtım açıklayan diğer makalelere bağlantılar için dağıtım genel bir bakış sağlar.|
|[Visual C++ Taşıma ve Yükseltme Kılavuzu](../porting/visual-cpp-porting-and-upgrading-guide.md)|Visual Studio'nun önceki sürümleri oluşturulan C++ uygulamalarını yükseltme ve ayrıca dışında Visual Studio Araçları ile oluşturulmuş uygulamalar geçirme hakkında ayrıntılı bilgi.|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual Studio ve bağlantıları Visual C++ belge geri kalanı için Visual C++ anahtar özelliklerini açıklar.|

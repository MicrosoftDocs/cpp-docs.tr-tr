---
title: "IDE ve Visual C++ geliştirme araçları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Visual C++, development tools
ms.assetid: 56eabafb-1956-4f0f-bec5-29b887763559
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e503c3ecbf0cd7245aadeb231030a91577e1e865
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ide-and-tools-for-visual-c-development"></a>IDE ve Visual C++ geliştirme araçları
Çok sayıda windows ve diğer dilleri ortak araçları, Visual Studio tümleşik geliştirme ortamı (IDE) parçası olarak, Visual C++ paylaşır. Bu da dahil olmak üzere birçok **Çözüm Gezgini**, kod düzenleyicisini ve hata ayıklayıcı altında belgelenen [Visual Studio IDE](/visualstudio/ide/visual-studio-ide). Genellikle, bir paylaşılan aracı ya da penceresini biraz farklı bir özellikler kümesi için C++ .NET dillerini veya Javascript için vardır. Bazı windows veya araçları yalnızca Visual Studio Pro veya Visual Studio Enterprise'da kullanılabilir.   
  
 Visual Studio IDE içinde paylaşılan Araçlar yanı sıra, Visual C++ özellikle yerel kod geliştirme için çeşitli araçlar vardır. Bu araçları Ayrıca bu makalede listelenmektedir. Hangi Araçlar her Visual Studio sürümünde bir listesi için bkz: [Visual C++ Araçları ve özelliklerinin Visual Studio sürümlerinde](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md).  
## <a name="creating-a-solution-and-projects"></a>Çözüm ve proje oluşturma  

"Proje" temel kaynak kodu dosyaları ve görüntü veya bir yürütülebilir dosyaya yerleşik veri dosyaları gibi kaynakları kümesidir. Visual Studio 2017 herhangi bir yapı sistem veya göz atma ve hata ayıklama IntelliSense için tam destek ile kullanmak istediğiniz özel derleme araçları destekler:
 - MSBuild Visual Studio için "yerel" yapı sistemi ve genellikle UWP uygulamaları veya MFC ya da ATL kullanan eski Windows Masaüstü uygulamaları için en iyi seçimdir. C++ MSBuild tabanlı projeler hakkında daha fazla bilgi için bkz: [oluşturma ve yönetme MSBuild tabanlı projeler](creating-and-managing-visual-cpp-projects.md).
 - CMake bir platformlar arası derleme Masaüstü C++ iş yükü yüklediğinizde Visual Studio IDE içinde tümleşik sisteminin ' dir. Daha fazla bilgi için bkz: [CMake Visual C++ projelerinde](cmake-tools-for-visual-cpp.md).
 - Dosyalar, gevşek topluluğu dahil olmak üzere diğer tüm C++ derleme sistemlere, Klasör Aç özelliği desteklenir. Yapı programınızı çağırma ve hata ayıklama oturumları yapılandırmak için basit JSON dosyaları oluşturun. Daha fazla bilgi için bkz: [C++ kodunuzu Visual Studio'ya Getir](https://blogs.msdn.microsoft.com/vcblog/2017/04/14/bring-your-cpp-code-to-visual-studio/).
 
 
 **Proje şablonları (MSBuild)**  
  
 Visual C++ MSBuild tabanlı projeler için çeşitli şablonlar ile birlikte gelen; Bu şablonlar, başlatıcı kodu ve çeşitli temel program türlerini için gerekli ayarları içerir. Genellikle seçerek Başlat **dosyası &#124; Yeni proje** bir proje şablonu bir proje oluşturmak için daha sonra bu projeye yeni kaynak kodu dosyaları ekleme veya sağlanan dosyalarında kod yazmaya başlayın. C++ projeleri ve proje sihirbazları özel bilgi için bkz: [oluşturma ve yönetme Visual C++ projeleri](../ide/creating-and-managing-visual-cpp-projects.md).  
  
 **Uygulama sihirbazları (MSBuild)**  
  
 Visual C++ öğesini seçtiğinizde bu sihirbazlar için bazı MSBuild proje türleri sağlar **dosyası &#124; Yeni proje**. Sihirbaz adım adım yeni proje oluşturma işleminde size kılavuzluk eder. Bu, çok sayıda seçeneklerini ve ayarlarını proje türleri için kullanışlıdır. Daha fazla bilgi için bkz: [oluşturma Masaüstü projeleri tarafından uygulama sihirbazlarını kullanma](../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
## <a name="creating-user-interfaces-with-designers-msbuild"></a>Kullanıcı arabirimleri (MSBuild) tasarımcılar ile oluşturma 
 Programınızın bir kullanıcı arabirimi varsa, ilk görevi bu düğmeleri, liste kutuları gibi denetimleri ile vb. doldurmak için biridir. Visual Studio, bir görsel tasarım yüzeyi ve C++ uygulaması her özellik için bir araç içerir. Oluşturduğunuz uygulama türünü olsun, temel aynı fikirdir: bir denetim araç kutusu penceresinden sürükleyip istediğiniz konuma tasarım yüzeyine bırakın. Arka planda, Visual Studio kaynaklar ve tüm çalışması için gerekli kod oluşturur. Ardından denetimlerini veri ile doldurma veya bunların görünümünü ve davranışını özelleştirmek için kod yazın.
  
 Bir evrensel Windows Platform uygulaması için kullanıcı arabirimi tasarlama hakkında daha fazla bilgi için bkz: [tasarım ve kullanıcı Arabirimi](https://developer.microsoft.com/en-us/windows/design).  
  
 MFC uygulaması için kullanıcı arabirimi oluşturma hakkında daha fazla bilgi için bkz: [MFC Masaüstü uygulamaları](../mfc/mfc-desktop-applications.md). Win32 Windows programlar hakkında daha fazla bilgi için bkz: [Windows Masaüstü uygulamaları](../windows/windows-desktop-applications-cpp.md).  
  
 C + ile Windows Forms uygulamaları hakkında bilgi için +/ CLI, bkz: [bir Windows Forms uygulaması kullanarak .NET Framework (C++) oluşturma](http://msdn.microsoft.com/en-us/8e007885-6c8b-4fb2-a41d-91febd114a9b).  
  
## <a name="writing-and-editing-code"></a>Yazma ve kod düzenleme  
 **Anlam renklendirme**  
  
 Bir proje oluşturduğunuzda, tüm proje dosyalarını görüntülenen **Çözüm Gezgini** penceresi. Tıkladığınızda bir .h veya .cpp dosyasında **Çözüm Gezgini**, Kod Düzenleyicisi'nde dosya açılır. Özelleştirilmiş bir sözcük işlemci C++ kaynak kodu için kod düzenleyicisidir. Dil anahtar sözcükleri, yöntemi ve değişken adları ve diğer öğelerin kodunu daha okunabilir ve anlaşılması daha kolay hale kodunuzun renkli kodlarla gösterir.  
  
 **IntelliSense**  
  
 Kod Düzenleyicisi birlikte IntelliSense bilinen çeşitli özellikler de destekler. Bir yöntem gelin ve bunu temel bazı belgelerine bakın. Bir sınıf değişken adını yazdıktan sonra ve bir. veya ->, bu sınıfın örnek üyelerin listesi görüntülenir. Bir sınıf adını yazın, ardından bir::, statik üyeler listesi görüntülenir. Bir sınıf veya yöntemin adını yazmaya başladığınızda, Kod düzenleyicisinde deyimini tamamlamak için öneriler sunar. Daha fazla bilgi için bkz: [kullanarak IntelliSense](/visualstudio/ide/using-intellisense).  
  
 **Kod parçacıkları**  
  
 IntelliSense kod parçacıkları yaygın olarak kullanılan oluşturmak için kullanabileceğiniz veya bir kısayol tuş vuruşu ile karmaşık kodu oluşturur. Daha fazla bilgi için bkz: [kod parçacıkları](/visualstudio/ide/code-snippets).  
  
## <a name="navigating-code"></a>Kodda gezinme  
 **Görünüm** menü geçici kod dosyalarınızda gezinmek için erişim sağlar birçok windows ve araçları. Bu windows hakkında ayrıntılı bilgi için bkz: [kodunu yapısı görüntüleme](/visualstudio/ide/viewing-the-structure-of-code).  
  
 **Çözüm Gezgini**  
  
 Visual Studio tüm sürümleri proje dosyalarında arasında gezinmek için Çözüm Gezgini bölmesini kullanın. Dosya sınıfları görüntülemek için bir .h veya .cpp dosya simgesini genişletin. Üyelerini görmek için bir sınıf genişletin. Üye tanımı veya uygulama dosyasına gitmek için çift tıklayın.  
  
 **Sınıf Görünümü ve kod tanımı penceresi**  
  
 Kullanım **sınıf görünümü** bölmesi ad alanları ve sınıfları kısmi sınıflar dahil olmak üzere tüm dosyalardaki, bkz. Her ad alanı veya kaynak dosyayı bu konuma gitmek için üye çift tıklayın ve üyelerini görmek için sınıf genişletebilirsiniz. Kod tanımı penceresi açarsanız, Sınıf Görünümü'nde seçtiğinizde tanım veya uygulama türü görüntüleyebilirsiniz.  
  
 **Nesne Tarayıcısı**  
  
 Kullanım **Nesne Tarayıcısı** Windows çalışma zamanı bileşenleri (.winmd dosyaları) türü bilgileri keşfetmek için .NET derlemelerini ve COM kitaplıkları yazın. Win32 DLL'leri ile kullanılmaz.  
  
 **Tanımı/bildirimine gidin**  
  
 Öğenin tanımına gitmek için herhangi bir API adı veya üye değişkeni üzerinde F12 tuşuna basın. Tanımı bir .winmd dosyasında ise (için bir [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] uygulama) türü bilgileri nesne tarayıcısında gösterilecek sonra. Ayrıca seçebilirsiniz **Tanıma Git** veya **bildirimi Git** değişken veya türü adına sağ tıklayıp bağlam menüsünden seçeneği seçerek.  
  
 **Tüm başvuruları Bul**  
  
 Kaynak kodu dosyasının fare imleci ile bir türü veya yöntemi veya değişken adını sağ tıklatın ve seçin **tüm başvuruları Bul** türü kullanıldığı her konum listesi dosya, proje veya çözüm döndürmek için. **Tüm başvuruları Bul** Akıllı ve diğer değişkenleri farklı kapsamda aynı ada sahip olsa bile yalnızca aynı aynı değişkeni örneklerini döndürür.  
  
 **Mimari Gezgini ve bağımlılık grafikleri (Ultimate)**  
  
 Kullanım **Mimari Gezgini** kodunuzda çeşitli öğeleri arasındaki ilişkileri görüntülemek için. Daha fazla bilgi için bkz: [Bul Mimari Gezgini koduyla](http://msdn.microsoft.com/en-us/b1707926-ef73-47f9-92cd-e00d0fac7e76). Bağımlılık grafikleri bağımlılık ilişkileri görüntülemek için kullanın. Daha fazla bilgi için bkz: [nasıl yapılır: C ve C++ kodu için bağımlılık grafikleri oluşturma](http://msdn.microsoft.com/en-us/3bd5cf9f-62f6-41d0-9f35-d4b2637cba3c).  
  
## <a name="adding-and-editing-resources--msbuild"></a>Ekleme ve düzenleme kaynakları (MSBuild)
 Visual Studio Masaüstü projesi bağlamında "kaynak" terimi iletişim kutuları, simgeler, yerelleştirilebilir dizeler, spash ekranlar, veritabanı bağlantı dizelerini veya yürütülebilir dosya olarak eklemek istediğiniz herhangi bir rastgele veri gibi öğeleri içerir.  
  
 Ekleme ve yerel Masaüstü C++ projelerine kaynakları düzenleme hakkında daha fazla bilgi için bkz: [kaynak dosyalarıyla çalışma](../windows/working-with-resource-files.md).  
  
## <a name="building-compiling-and-linking"></a>(Derleme ve bağlama) oluşturma  
 Tuşuna **Ctrl + Shift + B** derlemek ve proje bağlamak için. Yürütülebilir kod oluşturmak için Visual Studio kullanan [MSBuild](/visualstudio/msbuild/msbuild1) veya CMake veya belirlediğiniz başka bir yapı ortamı ayarladığınız aracılığıyla **Klasör Aç**. Genel Derleme seçenekleri altında ayarladığınız MSBuild projelerinde **Araçları &#124; Seçenekler &#124; Projeler ve çözümler** ve Özellikler altında belirli projeler için ayarlayabileceğiniz **proje &#124; Özellikler**. Derleme hataları ve uyarıları hata listesinde raporlanır (**Ctrl +\\, E**). MSBuild olmayan projeleri Çözüm Gezgini'nde oluşturduğunuz JSON dosyaları ile yapılandırılır. Ne olursa olsun oluşturma sistemi kullanın, çıktı penceresi (**Alt + 2**) oluşturma işlemi hakkında bilgi gösterir. MSBuild yapılandırmaları hakkında daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md) ve [Visual Studio'da C++ projeleri oluşturma](../ide/building-cpp-projects-in-visual-studio.md).  
  
 Visual C++ Derleyici (cl.exe) ve diğer birçok yapı ilgili tek başına Araçlar NMAKE ve LIB gibi doğrudan komut satırından da kullanabilirsiniz. Daha fazla bilgi için bkz: [komut satırında C/C++ derleme kodu](../build/building-on-the-command-line.md) ve [C/C++ oluşturma başvurusu](../build/reference/c-cpp-building-reference.md).  
  
## <a name="testing"></a>Sınama  
 Visual Studio içeren bir birim testi çerçevesi yerel C++ hem C + +/ CLI. Daha fazla bilgi için bkz: [kullanarak birim testlerini doğrulama kodla](/visualstudio/test/unit-test-your-code) ve [yazma birim C++ için Microsoft birim testi çerçevesi ile C/C++ için testleri](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)  
  
## <a name="debugging"></a>Hata Ayıklama  
 Tuşlarına basarak programınızı ayıklayabilirsiniz **F5** Debug proje yapılandırmanızı ayarlandığında. Hata ayıklama kesme noktaları tuşlarına basarak ayarlayabilirsiniz sırada **F9**, basarak adım kodlarda **F10**, belirtilen değişkenler veya kasaların değerlerini görüntülemek ve bazı durumlarda kodda değişiklik ve bile devam yeniden derleme olmadan hata ayıklama. Daha fazla bilgi için bkz: [Visual Studio'da hata ayıklamayı](/visualstudio/debugger/debugging-in-visual-studio).  
  
## <a name="deploying-completed-applications"></a>Tamamlanan uygulamalarını dağıtma  
 Dağıttığınız bir [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] Windows mağazası aracılığıyla aracılığıyla müşterilere **proje &#124; Mağaza** menü seçeneği. CRT dağıtımını otomatik olarak arka planda gerçekleştirilir. Daha fazla bilgi için bkz: [satış uygulamaları](http://go.microsoft.com/fwlink/p/?LinkId=262280).  
  
 Bir yerel C++ masaüstü uygulaması başka bir bilgisayara dağıtırken, uygulama ve uygulamanın bağımlı herhangi bir kitaplık dosyasını yüklemeniz gerekir. Visual C++ çalışma zamanı bir uygulama ile dağıtmak için üç yolu vardır: merkezi dağıtım, yerel dağıtım veya statik bağlama. Daha fazla bilgi için bkz: [Masaüstü uygulamaları dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md).  
  
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
|[Visual C++](../top/visual-cpp-in-visual-studio.md)|Visual Studio ve bağlantıları Visual C++ belge geri kalanı için Visual C++ anahtar özelliklerini açıklar.|

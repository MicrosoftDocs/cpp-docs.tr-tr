---
title: Visual Studio'da C++ projeleri derleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++ projects, building
- projects [C++], building
- builds [C++], about building in Visual Studio
ms.assetid: 9e8bc1a2-bb17-4951-937a-c757ed88d2d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7008e7fe670471301968482fbd4c6c758f0ff5e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33340508"
---
# <a name="building-c-projects-in-visual-studio"></a>Visual Studio'da C++ Projeleri Derleme
Visual Studio tümleşik geliştirme ortamında (IDE), çözümün tamamında ya da tek bir proje oluşturmak için birkaç yolu vardır. Derleme ayarlarını değiştirin ve geliştirme sürecini daha verimli hale getirmek için özel derleme adımları belirtin.  
  
 Visual Studio'da açın ve seçili bir çözümü oluşturmak için **Çözüm Gezgini**, şunları yapabilirsiniz:  
  
-   Menü çubuğunda seçin **yapı**, **yapı çözümü**.  
  
-   Veya, **Çözüm Gezgini**, çözüm için kısayol menüsünü açın ve ardından **yapı çözümü**.  
  
-   Veya F7 tuşuna basın. (C/C++ geliştirme ayarları için varsayılan klavye kısayolu budur.)  
  
-   Veya, [komut penceresi](/visualstudio/ide/reference/command-window) (menü çubuğunda seçin **Görünüm**, **diğer pencereler**, **komut penceresi**), girin `Build.BuildSolution`.  
  
-   Veya, [hızlı başlatma](/visualstudio/ide/reference/quick-launch-environment-options-dialog-box) kutusuna `build build solution`.  
  
 Seçili olan bir projeyi derleme için **Çözüm Gezgini**, şunları yapabilirsiniz:  
  
-   Menü çubuğunda seçin **yapı**, **yapı \<proje adı >**.  
  
-   Veya, **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **yapı**.  
  
-   Veya, komut penceresinde (menü çubuğunda seçin **Görünüm**, **diğer pencereler**, **komut penceresi**), girin `Build.BuildOnlyProject`.  
  
-   Veya, Hızlı Başlat kutusuna `build project only build only <project name>`.  
  
 Visual Studio'da bir Visual C++ uygulamasını derlerken, birçok projenin özellik sayfaları iletişim kutusunda yapı ayarı değiştirebilirsiniz. Proje özellikleri ayarlama hakkında daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).  
  
 IDE oluşturmak, yapı ve C++ projesi hata ayıklamak için nasıl kullanılacağı hakkında bir örnek için bkz: [izlenecek yol: Visual Studio IDE C++ ile keşfedin](/visualstudio/ide/getting-started-with-cpp-in-visual-studio). C + oluşturmak için IDE'yi kullanmaya ilişkin bir örnek +/ CLR proje bkz [izlenecek yol: Visual Studio'da CLR'yi hedefleyen C++ programını derleme](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md). Windows çalışma zamanı uygulama oluşturmak için IDE'yi kullanmaya ilişkin bir örnek için bkz: [C++ kullanarak ilk Windows çalışma zamanı uygulamanızı oluşturma](http://msdn.microsoft.com/library/windows/apps/hh974580.aspx).  
  
 Yapı, yapı ayarlarını değiştirin ve özel belirleme hakkında daha fazla adımları yapı okumak için aşağıdaki makalelere bakın.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](../ide/understanding-custom-build-steps-and-build-events.md)  
 Tümleşik geliştirme ortamını yapı işleminde özelleştirmeyi açıklar.  
  
 [Genel Derleme Komutları ve Özellikler Makroları](../ide/common-macros-for-build-commands-and-properties.md)  
 Dizeleri olduğu kabul edilir kullanabileceğiniz makroları listeler.  
  
 [Harici Projeler Derleme](../ide/building-external-projects.md)  
 Tümleşik geliştirme ortamı dışında özelliklerini kullanabilmeniz proje oluşturma açıklanır.  
  
 [Proje Dosyaları](../ide/project-files.md)  
 .Vcxproj dosyasının XML yapısını gösterir.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [VC ++ dizinleri, projeler, Seçenekler iletişim kutusu](vcpp-directories-property-page.md)  
 (Yalnızca MSBuild Proje) Yürütülebilir dosyalar için arama yolu değiştirmek, bir derleme sırasında dosyaları, kitaplık dosyaları ve kaynak kodu dosyaları dahil etme açıklanmaktadır.  
  
 [Derleme ve Oluşturma](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 Visual Studio içinde oluşturma hakkında bilgi sağlar.  
  
 [C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)  
 Komut satırından veya Visual Studio tümleşik geliştirme ortamı'ndan programınızı oluşturma açıklayan konulara bağlantılar sağlar.  
  
 [C/C++ Derleme Başvurusu](../build/reference/c-cpp-building-reference.md)  
 C++, derleyici ve bağlayıcı programları seçenekleri ve ek derleme araçları oluşturmaya genel bakış için bağlantılar sağlar.  
  
 [Önceki Visual C++ Sürümü Projelerini Yükseltme](../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
 C++ projenizi derleyici araç setini daha yeni sürümlerine yükseltme konusunda sorunlar kapsayan konulara bağlantılar sağlar.  
  
[Visual C++ Taşıma ve Yükseltme Kılavuzu](../porting/visual-cpp-porting-and-upgrading-guide.md)  
  Visual Studio'nun önceki sürümleri oluşturulan C++ uygulamalarını yükseltme ve ayrıca dışında Visual Studio Araçları ile oluşturulmuş uygulamalar geçirme hakkında ayrıntılı bilgi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Evrensel Windows Uygulamaları (C++)](../windows/universal-windows-apps-cpp.md)
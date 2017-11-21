---
title: "Visual C++ proje oluşturma ve yönetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vcprojects
- creatingmanagingVC
dev_langs: C++
helpviewer_keywords:
- ATL projects, creating
- Visual C++ projects, creating
- projects [C++], creating
- Visual C++ projects
- ATL projects
ms.assetid: 11003cd8-9046-4630-a189-a32bf3b88047
caps.latest.revision: "28"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c3e9ab166605d4d67e450a206cf1b47ea6d97f0a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-and-managing-msbuild-based-visual-c-projects"></a>Visual C++ MSBuild tabanlı projeler oluşturma ve yönetme
MSBuild Visual C++ için yerel yapılandırma sistemi ve genellikle en iyi oluşturma MFC ya da ATL kitaplıkları kullanan masaüstü uygulamaları yanı sıra UWP uygulamaları için kullanmak üzere sistemi. MSBuild proje sistemi ve Visual Studio IDE ile tümleşiktir, ancak bunu da komut satırından kullanabilirsiniz. Visual C++ Visual Studio 2017'dan başlayarak, destekler [CMake ve diğer MSBuild olmayan sistemleri Klasör Aç özelliği aracılığıyla](non-msbuild-projects.md).

MSBuild tabanlı projesinde bir proje dosyası örneğin hedef Platformu (x 86, x64 veya ARM) ve olup oluşturmakta olduğunuz diğer yapılandırma ayarlarını yanı sıra program derleme için gereken tüm dosyaları ve kaynakları belirten XML biçiminde (.vcxproj) sahip bir hata ayıklama program sürümünü veya bırakın. Bir proje (ya da çok sayıda proje) bulunan bir *çözüm*; Örneğin, bir çözüm birkaç Win32 DLL projeleri ve bu DLL'leri kullanan tek bir Win32 konsol uygulaması içerebilir. Projeyi derlerken MSBuild altyapısı proje dosyası tüketir ve yürütülebilir dosya ve/veya belirttiğiniz diğer herhangi bir özel çıktı üretir.

Visual C++ projeleri seçerek oluşturabileceğiniz **dosyası &#124; Yeni &#124; Proje**, Visual C++ sol bölmede seçili olduğundan emin olduktan ve Orta bölmede proje şablonları listesinden seçme. Bir şablonu temel tıkladığınızda, çoğu durumda proje oluşturmadan önce çeşitli proje özelliklerini ayarlamanıza olanak sağlayan bir Sihirbazı görünür. Görüntüleyebilir ve proje özellik sayfalarını kullanarak bu özellikleri daha sonra değiştirme (**proje &#124; Özellikler**).  
  
 Ayrıca yeni projeler tarafından oluşturabilirsiniz:  
  
-   seçme **dosyası &#124; Yeni &#124; Var olan koddan proje** ve mevcut kaynak kodu dosyaları eklemek için komut istemlerini izleyerek. Bu seçenek görece küçük ve basit projeleri için en iyi 25 kaynak kodu dosyaları veya az değişiklikle veya hiç karmaşık bağımlılıklar belki de çalışır.  
  
-   derleme görevleri ile başlayan ve Genel sekmesi altında Makefile proje şablonu seçin.  
  
-   boş bir proje oluşturma (altında **genel** sekmesinde) ve kaynak kodu dosyaları, Çözüm Gezgini'nde proje düğümüne sağ tıklayıp seçerek el ile ekleme **Ekle &#124; Varolan öğeyi**.  
  
-   kullanarak [Win32 Uygulama Sihirbazı'nı](../windows/win32-application-wizard.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Visual C++ proje türleri](../ide/visual-cpp-project-types.md)  
 Visual C++'da kullanılabilir MSBuild tabanlı proje türleri açıklanmaktadır.  
  
 [Visual C++ projeleri için oluşturulan dosya türleri](../ide/file-types-created-for-visual-cpp-projects.md)  
 Çeşitli MSBuild proje türleri ile birlikte kullanılan dosya türlerini açıklar.  
  
 [Uygulama sihirbazları kullanarak masaüstü projeleri oluşturma](../ide/creating-desktop-projects-by-using-application-wizards.md)  
 Sihirbazlar ile Visual C++ projeleri oluşturma için nasıl kullanılacağını.  
  
 [Proje özellikleriyle çalışma](../ide/working-with-project-properties.md)  
 Özellik sayfaları ve özellik sayfaları proje ayarlarınızı belirtmek için nasıl kullanılacağını açıklar.  
  
 [Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)  
 Sınıfları, yöntemleri, değişkenlerin ve diğer öğelerin işlevselliği eklemek için projenize ekleme işlemi açıklanmaktadır.  
  
 [Nasıl yapılır: derlemeler için proje çıktı dosyalarını düzenleme](../ide/how-to-organize-project-output-files-for-builds.md)  
 Proje çıktı dosyalarını düzenleme açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [C/C++ programları oluşturma](../build/building-c-cpp-programs.md)  
 Komut satırından veya Visual Studio tümleşik geliştirme ortamı'ndan programınızı oluşturma açıklayan konulara bağlantılar sağlar.  
  
 [Visual C++ başvurusu](http://msdn.microsoft.com/en-us/1ba03b5c-8229-4f63-b08c-6c12141d6ab1)  
 C ve C++ dil başvurusu, Visual C++, Visual C++ genişletilebilirlik nesne modeli ve Microsoft makro derleyici (MASM) ile birlikte sağlanan kitaplıkları açıklayan konulara bağlantılar sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio SDK](http://msdn.microsoft.com/vstudio/extend)

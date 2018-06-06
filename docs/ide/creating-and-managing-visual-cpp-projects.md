---
title: Visual C++ proje oluşturma ve yönetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vcprojects
- creatingmanagingVC
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, creating
- Visual C++ projects, creating
- projects [C++], creating
- Visual C++ projects
- ATL projects
ms.assetid: 11003cd8-9046-4630-a189-a32bf3b88047
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3afbd2019965d859895462cfdad57292bc2e0b3
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33332429"
---
# <a name="creating-and-managing-msbuild-based-visual-c-projects"></a>Visual C++ MSBuild tabanlı projeler oluşturma ve yönetme
MSBuild Visual C++ için yerel yapılandırma sistemi ve genellikle en iyi oluşturma MFC ya da ATL kitaplıkları kullanan masaüstü uygulamaları yanı sıra UWP uygulamaları için kullanmak üzere sistemi. MSBuild proje sistemi ve Visual Studio IDE ile tümleşiktir, ancak bunu da komut satırından kullanabilirsiniz. Visual C++ Visual Studio 2017'dan başlayarak, destekler [CMake ve diğer MSBuild olmayan sistemleri Klasör Aç özelliği aracılığıyla](non-msbuild-projects.md).

MSBuild tabanlı projesinde bir proje dosyası örneğin hedef Platformu (x 86, x64 veya ARM) ve olup oluşturmakta olduğunuz diğer yapılandırma ayarlarını yanı sıra program derleme için gereken tüm dosyaları ve kaynakları belirten XML biçiminde (.vcxproj) sahip bir hata ayıklama program sürümünü veya bırakın. Bir proje (ya da çok sayıda proje) bulunan bir *çözüm*; Örneğin, bir çözüm birkaç Win32 DLL projeleri ve bu DLL'leri kullanan tek bir Win32 konsol uygulaması içerebilir. Projeyi derlerken MSBuild altyapısı proje dosyası tüketir ve yürütülebilir dosya ve/veya belirttiğiniz diğer herhangi bir özel çıktı üretir.

Visual C++ projeleri seçerek oluşturabileceğiniz **dosya &#124; yeni &#124; proje**, Visual C++ sol bölmede seçili olduğundan emin olduktan ve Orta bölmede proje şablonları listesinden seçme. Bir şablonu temel tıkladığınızda, çoğu durumda proje oluşturmadan önce çeşitli proje özelliklerini ayarlamanıza olanak sağlayan bir Sihirbazı görünür. Görüntüleyebilir ve proje özellik sayfalarını kullanarak bu özellikleri daha sonra değiştirme (**proje &#124; özellikleri**).  
  
 Ayrıca yeni projeler tarafından oluşturabilirsiniz:  
  
-   seçme **dosya &#124; yeni &#124; var olan koddan proje** ve mevcut kaynak kodu dosyaları eklemek için komut istemlerini izleyerek. Bu seçenek görece küçük ve basit projeleri için en iyi 25 kaynak kodu dosyaları veya az değişiklikle veya hiç karmaşık bağımlılıklar belki de çalışır.  
  
-   derleme görevleri ile başlayan ve Genel sekmesi altında Makefile proje şablonu seçin.  
  
-   boş bir proje oluşturma (altında **genel** sekmesinde) ve kaynak kodu dosyaları, Çözüm Gezgini'nde proje düğümüne sağ tıklayıp seçerek el ile ekleme **Ekle &#124; varolan öğeyi**.  
  
-   kullanarak [Win32 Uygulama Sihirbazı'nı](../windows/win32-application-wizard.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Visual C++ proje türleri](../ide/visual-cpp-project-types.md)  
 Visual C++'da kullanılabilir MSBuild tabanlı proje türleri açıklanmaktadır.  
  
 [Visual C++ Projeleri için Oluşturulan Dosya Türleri](../ide/file-types-created-for-visual-cpp-projects.md)  
 Çeşitli MSBuild proje türleri ile birlikte kullanılan dosya türlerini açıklar.  
  
 [Uygulama Sihirbazları Kullanarak Masaüstü Projeleri Oluşturma](../ide/creating-desktop-projects-by-using-application-wizards.md)  
 Sihirbazlar ile Visual C++ projeleri oluşturma için nasıl kullanılacağını.  
  
 [Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)  
 Özellik sayfaları ve özellik sayfaları proje ayarlarınızı belirtmek için nasıl kullanılacağını açıklar.  
  
 [Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)  
 Sınıfları, yöntemleri, değişkenlerin ve diğer öğelerin işlevselliği eklemek için projenize ekleme işlemi açıklanmaktadır.  
  
 [Nasıl Yapılır: Derlemeler için Proje Çıktı Dosyalarını Düzenleme](../ide/how-to-organize-project-output-files-for-builds.md)  
 Proje çıktı dosyalarını düzenleme açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)  
 Komut satırından veya Visual Studio tümleşik geliştirme ortamı'ndan programınızı oluşturma açıklayan konulara bağlantılar sağlar.  
  
 [Visual C++ başvurusu](http://msdn.microsoft.com/en-us/1ba03b5c-8229-4f63-b08c-6c12141d6ab1)  
 C ve C++ dil başvurusu, Visual C++, Visual C++ genişletilebilirlik nesne modeli ve Microsoft makro derleyici (MASM) ile birlikte sağlanan kitaplıkları açıklayan konulara bağlantılar sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio SDK](http://msdn.microsoft.com/vstudio/extend)

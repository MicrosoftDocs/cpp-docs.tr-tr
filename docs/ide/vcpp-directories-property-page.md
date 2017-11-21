---
title: "VC ++ dizinleri özellik sayfası | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCDirectories.IncludePath
- VC.Project.VCDirectories.ReferencePath
- VC.Project.VCDirectories.SourcePath
- VC.Project.VCDirectories.LibraryWPath
- VC.Project.VCDirectories.ExecutablePath
- VC.Project.VCDirectories.LibraryPath
- VS.ToolsOptionsPages.Projects.VCDirectories
- VC.Project.VCDirectories.ExcludePath
dev_langs: C++
helpviewer_keywords: VC++ Directories Property Page
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 30a54b1d90585e6433f059acf30991ca53948d60
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vc-directories-property-page"></a>VC++ Dizinleri Özellik Sayfası
Visual Studio'nun proje oluşturmak için kullanmasını istediğiniz dizinleri belirtir. Bu özellik sayfasında erişmek için **Çözüm Gezgini**, proje için kısayol menüsünü açın ve seçin **özellikleri**ve ardından sol bölmesinde **özellik sayfaları** iletişim kutusunda, genişletin **yapılandırma özellikleri** seçip **VC ++ dizinleri**.  
  
 Bir proje oluşturmak için Visual Studio'yu kullandığınızda, belirli dizinleri devralır. Bunların çoğu makro olarak verilir. Sağ bölmesinde bir makrosu geçerli değeri incelemek için **VC ++ dizinleri** sayfasında, bir satır seçin — örneğin, **içerme dizinleri**— sağdaki aşağı ok düğmesini seçin, seçin  **Düzen**ve ardından görüntülenen iletişim kutusunda **makroları** düğmesi. Bu Web günlüğü postaları daha fazla bilgi için bkz: [VC ++ dizinleri](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx), [devralınan özellikler ve özellik sayfaları](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx), ve [Visual Studio 2010 C++ projesi Yükseltme Kılavuzu](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx).  
  
## <a name="directory-types"></a>Dizin Türleri  
 Ayrıca, aşağıdaki gibi diğer dizinleri de belirtebilirsiniz.  
  
 **Yürütülebilir dosya dizinleri**  
 Yürütülebilir dosyaların aranacağı dizinler. Karşılık gelen **yolu** ortam değişkeni.  
  
 **Yönergeleri dahil etme**  
 Kaynak kodda başvurulan ekleme kodu dosyalarının aranacağı dizinler. Karşılık gelen **INCLUDE** ortam değişkeni.  
  
 **Başvuru dizinleri**  
 Derleme ve kaynak kodu tarafından başvurulan modül (meta verileri) dosyaları için aranacak dizinlerde [#using](../preprocessor/hash-using-directive-cpp.md) yönergesi. Karşılık gelen **LIBPATH** ortam değişkeni.  
  
 **Kitaplık dizinleri**  
 Kitaplık (.lib) dosyalarının aranacağı dizinler; çalışma zamanı kitaplıkları da buna dahildir. Karşılık gelen **LIB** ortam değişkeni. Bu ayar .obj dosyaları için geçerli değildir; üzerinde bir .obj dosyasına bağlanmak için [bağlayıcı](../ide/linker-property-pages.md)**genel** özellik sayfasında, **ek kitaplık bağımlılıkları** ve ardından dosyanın göreli yolunu belirtin.  
  
 **Kaynak dizinler**  
 IntelliSense için kullanılacak kaynak dosyaların aranacağı dizinler.  
  
 **Dizinleri dışta tut**  
 Yapı bağımlılıkları denetlenirken aranmayacak dizinler.  
  
#### <a name="to-specify-or-modify-directory-settings"></a>Dizin ayarlarını belirtmek veya değiştirmek için  
  
1.  İçinde **Çözüm Gezgini**, değiştirin ve ardından istediğiniz proje için kısayol menüsünü açın **özellikleri**.  
  
2.  Sol bölmesinde **özellik sayfaları** iletişim kutusunda, genişletin **yapılandırma özellikleri** ve ardından **VC ++ dizinleri**.  
  
3.  Bir dizin listesi değiştirme, seçin, sağ taraftaki aşağı ok düğmesini seçin ve ardından seçin **Düzenle**.  
  
     Görüntülenen iletişim kutusu içindeki kutuda değerleri ekleyebilir veya kaldırabilir ve değerlerin göründüğü sıralamayı yeniden düzenleyebilirsiniz. Proje ayarları seçerek veya temizleyerek devralır olup olmadığını da değiştirebilirsiniz **üst ya da Proje Varsayılanları nesneden devral**.  
  
## <a name="sharing-the-settings"></a>Ayarları Paylaşma  
 Proje özelliklerini diğer kullanıcılarla veya birden çok bilgisayar arasında paylaşabilirsiniz. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).  
  

---
title: "Dosya türleri Visual C++ projeleri için oluşturulan | Microsoft Docs"
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
- header files [C++], Visual C++ projects
- ActiveX controls [C++], Help files
- def files
- project items [C++], files
- Visual C++ projects, files and directories
- resource files, created by wizard
- files [C++], extensions
- Help files, for ActiveX controls
- Web projects [C++], adding items
- .def files
- licensing ActiveX controls
ms.assetid: 2b0ee2e0-ae81-4185-9bb9-11da3c99a283
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 90d7b1523c8a61405224fc21701b5203e2cfb006
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="file-types-created-for-visual-c-projects"></a>Visual C++ Projeleri için Oluşturulan Dosya Türleri
Bu konu, Klasik Masaüstü uygulamalar için Visual C++ projeleri ile ilişkili olan dosyaları tüm türleri açıklanmaktadır. Projenizde eklenen gerçek dosyalarının proje türü ve bir Sihirbazı'nı kullanırken belirttiğiniz seçeneklere bağlıdır.  
  
-   [Proje ve Çözüm Dosyaları](../ide/project-and-solution-files.md)  
  
-   [CLR projeleri](../ide/files-created-for-clr-projects.md)  
  
-   [ATL Programı veya Denetim Kaynağı ve Başlık Dosyaları](../ide/atl-program-or-control-source-and-header-files.md)  
  
-   [MFC Programı veya Denetim Kaynağı ve Başlık Dosyaları](../ide/mfc-program-or-control-source-and-header-files.md)  
  
-   [Önceden Derlenmiş Üst Bilgi Dosyaları](../ide/precompiled-header-files.md)  
  
-   [Kaynak dosyaları](../ide/resource-files-cpp.md)  
  
-   [Yardım Dosyaları (WinHelp)](../ide/help-files-winhelp.md)  
  
-   [İpucu Dosyaları](../ide/hint-files.md)  
  
 Olduğunda, [Visual C++ projesi oluşturma](../ide/creating-desktop-projects-by-using-application-wizards.md), yeni bir çözüm oluşturma veya bir çözüme proje ekleme. Önemsiz olmayan uygulamaları, genellikle bir çözümde birden çok proje ile geliştirilir.  
  
 Projeleri genellikle bir EXE ya da bir DLL üretir. Projeleri birbirlerine bağımlı olabilir; derleme işlemi sırasında Visual C++ ortamına bağımlılıkları hem içinde hem de projeler arasında denetler. Her proje çekirdek kaynak kodu varsa ve proje türüne bağlı olarak çeşitli yönlerini projeyi içeren diğer birçok dosyalar sahip olabilir. Bu dosyaların içeriğini dosya uzantısına göre belirtilir. Visual Studio geliştirme ortamında dosya uzantılarını dosya içeriğini bir derleme sırasında nasıl ele alınacağını belirlemek için kullanır.  
  
 Aşağıdaki tabloda ortak dosyaları bir Visual C++ projesinde gösterir ve bunları kendi dosya uzantısıyla tanımlar.  
  
|Dosya uzantısı|Tür|İçindekiler|  
|--------------------|----------|--------------|  
|.asmx|Kaynak|Dağıtım dosyası.|  
|.asp|Kaynak|Active Server Page dosyası.|  
|.ATP|Proje|Uygulama Şablonu proje dosyası.|  
|.bmp, .dib, .gif, .jpg, .jpe, .png|Kaynak|Genel görüntü dosyaları.|  
|.BSC|Derleme|Tarayıcı kod dosyası.|  
|.cpp; .c|Kaynak|Uygulamanız için ana kaynak kodu dosyaları.|  
|.cur|Kaynak|İmleç bit eşlem grafik dosyası.|  
|.dbp|Proje|Veritabanı Proje dosyası.|  
|.disco|Kaynak|Dinamik bulma belge dosyası. XML Web hizmeti bulma işler.|  
|.exe, .dll|Proje|Yürütülebilir dosya veya dinamik bağlantı kitaplık dosyaları.|  
|.h|Kaynak|Üstbilgi (dahil) dosyası.|  
|.htm, .html, .xsp, .asp, .htc, .hta, .xml|Kaynak|Ortak Web dosyaları.|  
|. HxC|Proje|Proje dosyası yardımcı olur.|  
|.ico|Kaynak|Simge bit eşlem grafik dosyası.|  
|.idb|Derleme|Derleyici tarafından en az yeniden derleme ve artımlı derleme sırasında kullanılan sınıf tanımlarını ve kaynak dosyaları arasındaki bağımlılık bilgi içeren durum dosyası. Kullanım [/Fd](../build/reference/fd-program-database-file-name.md) derleyici seçeneği .idb dosyasının adını belirtin. Bkz: [/GM derlemeyi (etkinleştirmek en az yeniden derleme)](../build/reference/gm-enable-minimal-rebuild.md) daha fazla bilgi için.|  
|.idl|Derleme|Arabirim tanımı dil dosyası. Bkz: [arabirim tanımı (IDL) dosya](http://msdn.microsoft.com/library/windows/desktop/aa378712) daha fazla bilgi için Windows SDK'sındaki.|  
|.ilk|Bağlama|Artımlı bağlantı dosyası. Bkz: [/ARTIMLI](../build/reference/incremental-link-incrementally.md) daha fazla bilgi için.|  
|.map|Bağlama|Bağlayıcı bilgilerini içeren bir metin dosyası. Kullanım [/Fm](../build/reference/fm-name-mapfile.md) derleyici seçeneği harita dosya adı. Bkz: [/MAP](../build/reference/map-generate-mapfile.md) daha fazla bilgi için.|  
|.mfcribbon ms|Kaynak|Şeritte düğmeleri, denetimleri ve özniteliklerini tanımlayan XML kodunu içeren bir kaynak dosyası. Daha fazla bilgi için bkz: [Şerit Tasarımcısı (MFC)](../mfc/ribbon-designer-mfc.md).|  
|.obj, .o||Nesne dosyaları, derlenmiş ancak bağlı değil.|  
|.PCH|Hata ayıklama|Önceden derlenmiş üst bilgi dosyası.|  
|.RC, .rc2|Kaynak|[Kaynak betik dosyaları](../windows/working-with-resource-files.md) kaynakları oluşturmak için.|  
|.SBR|Derleme|Kaynak tarayıcı ara dosyası. Giriş dosyası için [BSCMAKE](../build/reference/bscmake-options.md).|  
|.sln|Çözüm|[Çözüm](http://msdn.microsoft.com/en-us/a45c299d-69f5-4b67-879d-1383417df0a7) dosya.|  
|.suo|Çözüm|Çözüm seçenekleri dosyası.|  
|.txt|Kaynak|Bir metin dosyası, genellikle "Benioku".|  
|.vap|Proje|Visual Studio Analyzer proje dosyası.|  
|.vbg|Çözüm|Uyumlu proje Grup dosyası.|  
|.vbp, .vip, .vbproj|Proje|Visual Basic proje dosyası.|  
|.vcxitems|Proje|Birden çok C++ projeleri arasında kod dosya paylaşımı için öğeleri proje paylaşılan. Bkz: [proje dosyalarını ve derleme görevleri dosyaları](../ide/project-and-solution-files.md) daha fazla bilgi için.|
|.vcxproj|Proje|Visual C++ proje dosyası. Bkz: [proje dosyalarını ve derleme görevleri dosyaları](../ide/project-and-solution-files.md) daha fazla bilgi için.|  
|. vcxproj.filters|Proje|Çözüm Gezgini, bir dosya için bir proje eklemek için kullanıldığında, filtreleri dosyası nerede Çözüm Gezgini ağaç görünümünde dosya eklenir, kendi dosya adı uzantısına göre tanımlar.|  
|.vdproj|Proje|Visual Studio dağıtım proje dosyası.|  
|.vmx|Proje|Makro proje dosyası.|  
|.vup|Proje|Yardımcı programı proje dosyası.|  
  
 Visual Studio ile ilişkili diğer dosyalar hakkında daha fazla bilgi için bkz: [dosya türleri ve Visual Studio .NET içinde dosya uzantılarını](/visualstudio/ide/reference/project-and-solution-file-types).  
  
 Proje dosyaları, Çözüm Gezgini'nde klasörler halinde düzenlenir. Visual C++ kaynak dosyaları, üst bilgi dosyaları ve kaynak dosyaları için bir klasör oluşturur, ancak bu klasörleri yeniden düzenleyin veya yenilerini oluşturun. Bir proje hiyerarşi içindeki dosyaların açıkça mantıksal kümeleri düzenlemek için klasörler kullanabilirsiniz. Örneğin, tüm kullanıcı arabirimi kaynak dosyalarını veya belirtimleri, belgeleri içermesini klasör oluşturma veya test paketleri. Tüm dosya klasör adları benzersiz olmalıdır.  
  
 Bir projeye öğe eklediğinizde, öğe oluþturulabilir olup olmadığına bakılmaksızın bu proje için tüm yapılandırmalar için öğeyi ekleyin. MyProject adlı projesi varsa, örneğin, bir öğe ekleme hata ayıklama ve yayın proje yapılandırmaları için ekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ proje oluşturma ve yönetme](../ide/creating-and-managing-visual-cpp-projects.md)   
 [Visual C++ proje türleri](../ide/visual-cpp-project-types.md)   
 [Diğer Diller için Sihirbaz Desteği](../ide/wizard-support-for-other-languages.md)
---
title: Dosya türleri Visual C++ projeleri için oluşturulan | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dba47b8464c7fcdd170df1819b65aa448d8f8aeb
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808427"
---
# <a name="file-types-created-for-visual-c-projects"></a>Visual C++ Projeleri için Oluşturulan Dosya Türleri

Bu konuda, Klasik Masaüstü uygulamaları için Visual C++ projeleri ile ilişkili olan dosyaların tüm türleri açıklanmaktadır. Projenize dahil gerçek dosyaları proje türü ve bir Sihirbazı kullanarak belirttiğiniz seçeneklere bağlıdır.

- [Proje ve Çözüm Dosyaları](../ide/project-and-solution-files.md)

- [CLR projeleri](../ide/files-created-for-clr-projects.md)

- [ATL Programı veya Denetim Kaynağı ve Başlık Dosyaları](../ide/atl-program-or-control-source-and-header-files.md)

- [MFC Programı veya Denetim Kaynağı ve Başlık Dosyaları](../ide/mfc-program-or-control-source-and-header-files.md)

- [Önceden Derlenmiş Üst Bilgi Dosyaları](../ide/precompiled-header-files.md)

- [Kaynak dosyaları](../ide/resource-files-cpp.md)

- [Yardım Dosyaları (WinHelp)](../ide/help-files-winhelp.md)

- [İpucu Dosyaları](../ide/hint-files.md)

Olduğunda, [Visual C++ projesi oluşturma](../ide/creating-desktop-projects-by-using-application-wizards.md), yeni bir çözüm oluşturmak olabilir veya bir çözüme proje ekleme. Önemsiz olmayan uygulamaları, genellikle bir çözümde birden çok proje ile geliştirilmiştir.

Projeleri, genellikle bir EXE veya DLL oluşturur. Projelerin birbirine bağımlı olabilir. derleme işlemi sırasında Visual C++ ortamına hem içinde hem de projeler arası bağımlılıkları denetler. Her proje çekirdek kaynak kodu ve proje türüne bağlı olarak çeşitli yönlerini projeyi içeren diğer birçok dosyaları sahip. Bu dosyaların içeriğini dosya uzantısı tarafından belirtilir. Visual Studio geliştirme ortamını dosya uzantılarını derleme sırasında dosya içeriğini işlemek nasıl belirlemek için kullanır.

Aşağıdaki tabloda, bir Visual C++ projesinde ortak dosyaları gösterir ve bunları kendi dosya uzantısıyla tanımlar.

|Dosya uzantısı|Tür|İçindekiler|
|--------------------|----------|--------------|
|.asmx|Kaynak|Dağıtım dosyası.|
|.asp|Kaynak|Active Server Page dosyası.|
|.ATP|Proje|Uygulama Şablonu proje dosyası.|
|.bmp, .dib, .gif, .jpg, .jpe, .png|Kaynak|Genel görüntü dosyaları.|
|.BSC|Derleme|Tarayıcı kod dosyası.|
|.cpp; .c|Kaynak|Uygulamanız için ana kaynak kodu dosyaları.|
|.cur|Kaynak|Grafik bit eşlem dosyası imleç.|
|.dbp|Proje|Veritabanı Proje dosyası.|
|.disco|Kaynak|Devingen keşif belgesi dosyası. XML Web hizmeti bulma işler.|
|.exe, .dll|Proje|Yürütülebilir dosya veya dinamik bağlantı kitaplığı dosyaları.|
|.h|Kaynak|Bir üst bilgisi (dahil) dosyası.|
|.htm, .html, .xsp, .asp, .htc, .hta, .xml|Kaynak|Ortak Web dosyaları.|
|. HxC|Proje|Proje dosyası yardımcı olur.|
|.ico|Kaynak|Simge bit eşlem grafik dosyası.|
|.idb|Derleme|En az yeniden derleme ve artımlı derleme sırasında derleyici tarafından kullanılabilecek sınıf tanımları ve kaynak dosyaları arasındaki bağımlılık bilgilerini içeren durum dosyası. Kullanım [/Fd](../build/reference/fd-program-database-file-name.md) derleyici seçeneğini .idb dosyasının adını belirtin. Bkz: [/GM derlemeyi (etkinleştirme en az yeniden derlemeyi)](../build/reference/gm-enable-minimal-rebuild.md) daha fazla bilgi için.|
|.idl|Derleme|Arabirim tanımı dili dosyası. Bkz: [arabirim tanımı (IDL) dosya](/windows/desktop/Rpc/the-interface-definition-language-idl-file) daha fazla bilgi için Windows SDK.|
|.ilk|Bağlama|Artımlı bağlantı dosyası. Bkz: [/INCREMENTAL](../build/reference/incremental-link-incrementally.md) daha fazla bilgi için.|
|.map|Bağlama|Bağlayıcı bilgilerini içeren bir metin dosyası. Kullanım [/Fm](../build/reference/fm-name-mapfile.md) eşleme dosyasını adlandırmak için derleyici seçeneği. Bkz: [/MAP](../build/reference/map-generate-mapfile.md) daha fazla bilgi için.|
|.mfcribbon ms|Kaynak|Şerit düğmeleri, denetimleri ve özniteliklerini tanımlayan XML kodunu içeren bir kaynak dosyası. Daha fazla bilgi için [Şerit Tasarımcısı (MFC)](../mfc/ribbon-designer-mfc.md).|
|.obj, .o||Bağlı değil ancak derlenmiş nesne dosyaları.|
|.PCH|Hata ayıklama|Önceden derlenmiş üst bilgi dosyası.|
|.RC, .rc2|Kaynak|[Kaynak betik dosyalarına](../windows/working-with-resource-files.md) kaynakları oluşturmak için.|
|.SBR|Derleme|Kaynak tarayıcı ara dosyası. Giriş dosyası için [BSCMAKE](../build/reference/bscmake-options.md).|
|.sln|Çözüm|[Çözüm](/visualstudio/ide/solutions-and-projects-in-visual-studio) dosya.|
|.suo|Çözüm|Çözüm seçenekleri dosyası.|
|.txt|Kaynak|Bir metin dosyası, genellikle "Benioku".|
|.vap|Proje|Visual Studio Analyzer proje dosyası.|
|.vbg|Çözüm|Uyumlu proje grubu dosyası.|
|.vbp .vip, .vbproj|Proje|Visual Basic proje dosyası.|
|.vcxitems|Proje|Paylaşılan öğeler projesi'birden çok C++ projeleri arasında kod dosya paylaşımı. Bkz: [proje dosyalarını ve derleme görevleri dosyalarını](../ide/project-and-solution-files.md) daha fazla bilgi için.|
|.vcxproj|Proje|Visual C++ proje dosyası. Bkz: [proje dosyalarını ve derleme görevleri dosyalarını](../ide/project-and-solution-files.md) daha fazla bilgi için.|
|. vcxproj.filters|Proje|Çözüm Gezgini, bir dosyayı bir projeye eklemek için kullanıldığında, filtreler dosyası burada Çözüm Gezgini ağaç görünümünde dosya eklendiğinde, kendi dosya adı uzantısına göre tanımlar.|
|.vdproj|Proje|Visual Studio dağıtım proje dosyası.|
|.vmx|Proje|Makrosu proje dosyası.|
|.vup|Proje|Yardımcı programı proje dosyası.|

Visual Studio ile ilişkili diğer dosyalar hakkında daha fazla bilgi için bkz. [dosya türleri ve dosya uzantıları Visual Studio. NET'te](/visualstudio/ide/reference/project-and-solution-file-types).

Proje dosyaları Çözüm Gezgini'nde klasörler halinde düzenlenir. Visual C++ kaynak dosyaları, üstbilgi dosyaları ve kaynak dosyaları için bir klasör oluşturur, ancak bu klasörleri yeniden düzenlemek veya yenilerini oluşturun. Dosyaları bir proje hiyerarşisi içinde açıkça mantıksal kümelerini düzenlemek için klasörleri'ni kullanabilirsiniz. Örneğin, tüm kullanıcı arabirimi kaynak dosyaları veya belirtimleri, belgeleri içermesini klasör oluşturma veya test paketleri. Tüm dosya klasör adları benzersiz olmalıdır.

Bir projeye bir öğe eklediğinizde, öğe derlenebilir olup olmadığına bakılmaksızın bu proje için tüm yapılandırmalar için öğeyi ekleyin. MyProject adlı bir proje varsa, örneğin, bir öğe ekleme, hata ayıklama ve yayın proje yapılandırmaları için ekler.

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ proje oluşturma ve yönetme](../ide/creating-and-managing-visual-cpp-projects.md)<br>
[Visual C++ Proje Türleri](../ide/visual-cpp-project-types.md)<br>
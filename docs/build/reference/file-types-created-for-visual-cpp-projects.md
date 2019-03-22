---
title: Visual C++ Projeleri için Oluşturulan Dosya Türleri
ms.date: 11/04/2016
helpviewer_keywords:
- header files [C++], Visual Studio projects
- ActiveX controls [C++], Help files
- def files
- project items [C++], files
- Visual Studio C++ projects, files and directories
- resource files, created by wizard
- files [C++], extensions
- Help files, for ActiveX controls
- Web projects [C++], adding items
- .def files
- licensing ActiveX controls
ms.assetid: 2b0ee2e0-ae81-4185-9bb9-11da3c99a283
ms.openlocfilehash: 7ef8127b829b60d84af72874292c33ae1c7c4636
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58327587"
---
# <a name="file-types-created-for-visual-studio-c-projects"></a>Visual Studio C++ projeleri için oluşturulan dosya türleri

Bu konuda, Klasik Masaüstü uygulamaları için Visual Studio projeleri ile ilişkili olan dosyaların tüm türleri açıklanmaktadır. Projenize dahil gerçek dosyaları proje türü ve bir Sihirbazı kullanarak belirttiğiniz seçeneklere bağlıdır.

- [Proje ve Çözüm Dosyaları](project-and-solution-files.md)

- [CLR projeleri](files-created-for-clr-projects.md)

- [ATL Programı veya Denetim Kaynağı ve Başlık Dosyaları](atl-program-or-control-source-and-header-files.md)

- [MFC Programı veya Denetim Kaynağı ve Başlık Dosyaları](mfc-program-or-control-source-and-header-files.md)

- [Önceden Derlenmiş Üst Bilgi Dosyaları](../creating-precompiled-header-files.md)

- [Kaynak Dosyalar](resource-files-cpp.md)

- [Yardım Dosyaları (WinHelp)](help-files-winhelp.md)

- [İpucu Dosyaları](hint-files.md)

Visual Studio projesi oluşturduğunuzda, yeni bir çözüm oluşturmak olabilir ya da bir çözüme proje ekleme. Önemsiz olmayan uygulamaları, genellikle bir çözümde birden çok proje ile geliştirilmiştir.

Projeleri, genellikle bir EXE veya DLL oluşturur. Projelerin birbirine bağımlı olabilir. derleme işlemi sırasında Visual Studio ortamının içinde ve projeler arası bağımlılıkları denetler. Her proje çekirdek kaynak kodu ve proje türüne bağlı olarak çeşitli yönlerini projeyi içeren diğer birçok dosyaları sahip. Bu dosyaların içeriğini dosya uzantısı tarafından belirtilir. Visual Studio geliştirme ortamını dosya uzantılarını derleme sırasında dosya içeriğini işlemek nasıl belirlemek için kullanır.

Aşağıdaki tabloda, Visual Studio projesinde ortak dosyaları gösterir ve bunları kendi dosya uzantısıyla tanımlar.

|Dosya uzantısı|Tür|İçindekiler|
|--------------------|----------|--------------|
|.asmx|Kaynak|Dağıtım dosyası.|
|.asp|Kaynak|Active Server Page dosyası.|
|.ATP|Project|Uygulama Şablonu proje dosyası.|
|.bmp, .dib, .gif, .jpg, .jpe, .png|Kaynak|Genel görüntü dosyaları.|
|.bsc|Derleme|Tarayıcı kod dosyası.|
|.cpp, .c|Kaynak|Uygulamanız için ana kaynak kodu dosyaları.|
|.cur|Kaynak|Grafik bit eşlem dosyası imleç.|
|.dbp|Project|Veritabanı Proje dosyası.|
|.disco|Kaynak|Devingen keşif belgesi dosyası. XML Web hizmeti bulma işler.|
|.exe, .dll|Project|Yürütülebilir dosya veya dinamik bağlantı kitaplığı dosyaları.|
|.h|Kaynak|Bir üst bilgisi (dahil) dosyası.|
|.htm, .html, .xsp, .asp, .htc, .hta, .xml|Kaynak|Ortak Web dosyaları.|
|.HxC|Project|Proje dosyası yardımcı olur.|
|.ico|Kaynak|Simge bit eşlem grafik dosyası.|
|.idb|Derleme|En az yeniden derleme ve artımlı derleme sırasında derleyici tarafından kullanılabilecek sınıf tanımları ve kaynak dosyaları arasındaki bağımlılık bilgilerini içeren durum dosyası. Kullanım [/Fd](fd-program-database-file-name.md) derleyici seçeneğini .idb dosyasının adını belirtin. Bkz: [/GM derlemeyi (etkinleştirme en az yeniden derlemeyi)](gm-enable-minimal-rebuild.md) daha fazla bilgi için.|
|.idl|Derleme|Arabirim tanımı dili dosyası. Bkz: [arabirim tanımı (IDL) dosya](/windows/desktop/Rpc/the-interface-definition-language-idl-file) daha fazla bilgi için Windows SDK.|
|.ilk|Bağlama|Artımlı bağlantı dosyası. Bkz: [/INCREMENTAL](incremental-link-incrementally.md) daha fazla bilgi için.|
|.map|Bağlama|Bağlayıcı bilgilerini içeren bir metin dosyası. Kullanım [/Fm](fm-name-mapfile.md) eşleme dosyasını adlandırmak için derleyici seçeneği. Bkz: [/MAP](map-generate-mapfile.md) daha fazla bilgi için.|
|.mfcribbon-ms|Kaynak|Şerit düğmeleri, denetimleri ve özniteliklerini tanımlayan XML kodunu içeren bir kaynak dosyası. Daha fazla bilgi için [Şerit Tasarımcısı (MFC)](../../mfc/ribbon-designer-mfc.md).|
|.obj, .o||Bağlı değil ancak derlenmiş nesne dosyaları.|
|.pch|Hata ayıklama|Önceden derlenmiş üst bilgi dosyası.|
|.RC, .rc2|Kaynak|[Kaynak betik dosyalarına](../../windows/working-with-resource-files.md) kaynakları oluşturmak için.|
|.sbr|Derleme|Kaynak tarayıcı ara dosyası. Giriş dosyası için [BSCMAKE](bscmake-options.md).|
|.sln|Çözüm|[Çözüm](/visualstudio/ide/solutions-and-projects-in-visual-studio) dosya.|
|.suo|Çözüm|Çözüm seçenekleri dosyası.|
|.txt|Kaynak|Bir metin dosyası, genellikle "Benioku".|
|.vap|Project|Visual Studio Analyzer proje dosyası.|
|.vbg|Çözüm|Uyumlu proje grubu dosyası.|
|.vbp, .vip, .vbproj|Project|Visual Basic proje dosyası.|
|.vcxitems|Project|Paylaşılan öğeler projesi'birden çok C++ projeleri arasında kod dosya paylaşımı. Bkz: [proje ve çözüm dosyaları](project-and-solution-files.md) daha fazla bilgi için.|
|.vcxproj|Project|Visual Studio Proje dosyası. Bkz: [proje ve çözüm dosyaları](project-and-solution-files.md) daha fazla bilgi için.|
|.vcxproj.filters|Project|Çözüm Gezgini, bir dosyayı bir projeye eklemek için kullanıldığında, filtreler dosyası burada Çözüm Gezgini ağaç görünümünde dosya eklendiğinde, kendi dosya adı uzantısına göre tanımlar.|
|.vdproj|Project|Visual Studio dağıtım proje dosyası.|
|.vmx|Project|Makrosu proje dosyası.|
|.vup|Project|Yardımcı programı proje dosyası.|

Visual Studio ile ilişkili diğer dosyalar hakkında daha fazla bilgi için bkz. [dosya türleri ve dosya uzantıları Visual Studio. NET'te](/visualstudio/ide/reference/project-and-solution-file-types).

Proje dosyaları Çözüm Gezgini'nde klasörler halinde düzenlenir. Visual Studio kaynak dosyaları, üstbilgi dosyaları ve kaynak dosyaları için bir klasör oluşturur, ancak bu klasörleri yeniden düzenlemek veya yenilerini oluşturun. Dosyaları bir proje hiyerarşisi içinde açıkça mantıksal kümelerini düzenlemek için klasörleri'ni kullanabilirsiniz. Örneğin, tüm kullanıcı arabirimi kaynak dosyaları veya belirtimleri, belgeleri içermesini klasör oluşturma veya test paketleri. Tüm dosya klasör adları benzersiz olmalıdır.

Bir projeye bir öğe eklediğinizde, öğe derlenebilir olup olmadığına bakılmaksızın bu proje için tüm yapılandırmalar için öğeyi ekleyin. MyProject adlı bir proje varsa, örneğin, bir öğe ekleme, hata ayıklama ve yayın proje yapılandırmaları için ekler.

## <a name="see-also"></a>Ayrıca Bkz.

[Visual Studio C++ proje oluşturma ve yönetme](../creating-and-managing-visual-cpp-projects.md)<br>
[Visual Studio C++ proje türleri](visual-cpp-project-types.md)<br>
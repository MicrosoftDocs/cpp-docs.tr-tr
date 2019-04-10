---
title: Visual C++ Projeleri için Oluşturulan Dosya Türleri
ms.date: 04/08/2019
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
ms.openlocfilehash: eee53acbb8b0b8432a7d5819fb773b616f0e8897
ms.sourcegitcommit: 39debf8c525c3951af6913ee5e514617658f8859
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59424099"
---
# <a name="file-types-created-for-visual-studio-c-projects"></a>Visual Studio C++ projeleri için oluşturulan dosya türleri

Birçok türdeki dosyayı Klasik Masaüstü uygulamaları için Visual Studio projeleri ile ilişkilidir. Projenize dahil gerçek dosyaları proje türü ve bir Sihirbazı kullanarak belirttiğiniz seçeneklere bağlıdır.

- [Proje ve Çözüm Dosyaları](project-and-solution-files.md)

- [CLR Projeleri](files-created-for-clr-projects.md)

- [ATL Programı veya Denetim Kaynağı ve Başlık Dosyaları](atl-program-or-control-source-and-header-files.md)

- [MFC Programı veya Denetim Kaynağı ve Başlık Dosyaları](mfc-program-or-control-source-and-header-files.md)

- [Önceden Derlenmiş Başlık Dosyaları](../creating-precompiled-header-files.md)

- [Kaynak Dosyalar](resource-files-cpp.md)

- [Yardım Dosyaları (WinHelp)](help-files-winhelp.md)

- [İpucu Dosyaları](hint-files.md)

Visual Studio projesi oluşturduğunuzda, yeni çözümde oluşturabilir veya varolan çözüme bir proje ekleyebilir. Önemsiz olmayan uygulamaları, genellikle bir çözümde birden çok proje ile geliştirilmiştir.

Projeleri, genellikle bir EXE veya DLL oluşturur. Projelerin birbirine bağımlı olabilir. derleme işlemi sırasında Visual Studio ortamının içinde ve projeler arası bağımlılıkları denetler. Her proje, çekirdek kaynak kodu genellikle vardır. Projenin türüne bağlı olarak çeşitli yönlerini projeyi içeren diğer birçok dosyaları bulunabilir. Bu dosyaların içeriğini dosya uzantısı tarafından belirtilir. Visual Studio geliştirme ortamını dosya uzantılarını derleme sırasında dosya içeriğini işlemek nasıl belirlemek için kullanır.

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
|.idb|Derleme|Sınıf tanımları ve kaynak dosyaları arasındaki bağımlılık bilgilerini içeren durum dosyası. Artımlı derleme sırasında derleyici tarafından kullanılabilir. Kullanım [/Fd](fd-program-database-file-name.md) derleyici seçeneğini .idb dosyasının adını belirtin.|
|.idl|Derleme|Arabirim tanımı dili dosyası. Daha fazla bilgi için [arabirim tanımı (IDL) dosya](/windows/desktop/Rpc/the-interface-definition-language-idl-file) Windows SDK.|
|.ilk|Bağlama|Artımlı bağlantı dosyası. Daha fazla bilgi için [/INCREMENTAL](incremental-link-incrementally.md).|
|.map|Bağlama|Bağlayıcı bilgilerini içeren bir metin dosyası. Kullanım [/Fm](fm-name-mapfile.md) eşleme dosyasını adlandırmak için derleyici seçeneği. Daha fazla bilgi için [/MAP](map-generate-mapfile.md).|
|.mfcribbon-ms|Kaynak|Şeritte MFC düğmeler, denetimleri ve özniteliklerini tanımlayan XML kodunu içeren bir kaynak dosyası. Daha fazla bilgi için [Şerit Tasarımcısı](../../mfc/ribbon-designer-mfc.md).|
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
|.vcxitems|Project|Paylaşılan öğeler projesi'birden çok C++ projeleri arasında kod dosya paylaşımı. Daha fazla bilgi için [proje ve çözüm dosyaları](project-and-solution-files.md).|
|.vcxproj|Project|Visual Studio Proje dosyası. Daha fazla bilgi için [proje ve çözüm dosyaları](project-and-solution-files.md).|
|.vcxproj.filters|Project|Bir projeye bir dosya eklemek için Çözüm Gezgini'ni kullandığınızda kullanılır. Filtreler dosyası, dosya adı uzantısına göre dosyası eklemek için Çözüm Gezgini ağaç görünümünde nereye tanımlar.|
|.vdproj|Project|Visual Studio dağıtım proje dosyası.|
|.vmx|Project|Makrosu proje dosyası.|
|.vup|Project|Yardımcı programı proje dosyası.|

Visual Studio ile ilişkili diğer dosyalar hakkında daha fazla bilgi için bkz. [dosya türleri ve dosya uzantıları Visual Studio. NET'te](/visualstudio/ide/reference/project-and-solution-file-types).

Proje dosyaları Çözüm Gezgini'nde klasörler halinde düzenlenir. Visual Studio kaynak dosyaları, üstbilgi dosyaları ve kaynak dosyaları için bir klasör oluşturur, ancak bu klasörleri yeniden düzenlemek veya yenilerini oluşturun. Dosyaları bir proje hiyerarşisi içinde açıkça mantıksal kümelerini düzenlemek için klasörleri'ni kullanabilirsiniz. Örneğin, tüm kullanıcı arabirimi kaynak dosyalarını içeren klasörler oluşturabilirsiniz. Veya klasörleri belirtimleri, belgeleri veya test paketleri. Tüm dosya klasör adları benzersiz olmalıdır.

Bir projeye bir öğe eklediğinizde, bu proje için tüm yapılandırmalar için öğeyi ekleyin. Öğe, derlenebilir olup olmadığını eklenir. MyProject adlı bir proje varsa, örneğin, bir öğe ekleme, hata ayıklama ve yayın proje yapılandırmaları için ekler.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio C++ proje oluşturma ve yönetme](../creating-and-managing-visual-cpp-projects.md)<br>
[Visual Studio C++ proje türleri](visual-cpp-project-types.md)<br>
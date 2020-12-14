---
description: 'Hakkında daha fazla bilgi edinin: Visual Studio C++ projeleri için oluşturulan dosya türleri'
title: Visual Studio C++ projeleri için oluşturulan dosya türleri
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
ms.openlocfilehash: bd1dad365ea2635549322c886f00f4e08ff47942
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200591"
---
# <a name="file-types-created-for-visual-studio-c-projects"></a>Visual Studio C++ projeleri için oluşturulan dosya türleri

Birçok dosya türü, klasik masaüstü uygulamaları için Visual Studio projeleriyle ilişkilendirilir. Projenizde bulunan gerçek dosyalar proje türüne ve sihirbaz kullanılırken belirlediğiniz seçeneklere bağlıdır.

- [Proje ve çözüm dosyaları](project-and-solution-files.md)

- [CLR projeleri](files-created-for-clr-projects.md)

- [ATL programı veya denetim kaynağı ve üstbilgi dosyaları](atl-program-or-control-source-and-header-files.md)

- [MFC programı veya denetim kaynağı ve üstbilgi dosyaları](mfc-program-or-control-source-and-header-files.md)

- [Ön derlenmiş üstbilgi dosyaları](../creating-precompiled-header-files.md)

- [Kaynak dosyaları](resource-files-cpp.md)

- [Yardım Dosyaları (WinHelp)](help-files-winhelp.md)

- [İpucu Dosyaları](hint-files.md)

Bir Visual Studio projesi oluşturduğunuzda, bunu yeni bir çözümde oluşturabilir veya var olan bir çözüme bir proje ekleyebilirsiniz. Önemsiz olmayan uygulamalar genellikle bir çözümde birden çok projeyle birlikte geliştirilir.

Projeler genellikle bir EXE ya da DLL üretir. Projeler birbirlerine bağımlı olabilir; yapı işlemi sırasında, Visual Studio ortamı, hem projeler içinde hem de arasında bağımlılıkları denetler. Her projenin genellikle çekirdek kaynak kodu vardır. Projenin türüne bağlı olarak, projenin çeşitli yönlerini içeren çok sayıda başka dosya olabilir. Bu dosyaların içeriği dosya uzantısıyla belirtilir. Visual Studio geliştirme ortamı, derleme sırasında dosya içeriğini nasıl işleyeceğinizi öğrenmek için dosya uzantılarını kullanır.

Aşağıdaki tabloda bir Visual Studio projesindeki ortak dosyalar gösterilmektedir ve bunları dosya uzantısıyla tanımlar.

|Dosya uzantısı|Tür|İçindekiler|
|--------------------|----------|--------------|
|.asmx|Kaynak|Dağıtım dosyası.|
|\|Kaynak|Active Server sayfa dosyası.|
|. ATP|Project|Uygulama şablonu proje dosyası.|
|. bmp,. dib,. gif,. jpg,. jpe,. png|Kaynak|Genel resim dosyaları.|
|. bsc|Derlen|Tarayıcı kodu dosyası.|
|. cpp,. c|Kaynak|Uygulamanız için ana kaynak kodu dosyaları.|
|. cur|Kaynak|İmleç bit eşlem grafik dosyası.|
|. DBP|Project|Veritabanı proje dosyası.|
|. disco|Kaynak|Dinamik bulgu belge dosyası. XML Web hizmeti bulmayı işler.|
|. exe,. dll|Project|Yürütülebilir veya dinamik bağlantı kitaplığı dosyaları.|
|. h|Kaynak|Üst bilgi (dahil) dosyası.|
|. htm,. html,. XSP,. asp,. HTC,. hta,. xml|Kaynak|Ortak Web dosyaları.|
|. HxC|Project|Yardım proje dosyası.|
|. ico|Kaynak|Simge bit eşlem grafik dosyası.|
|. IDB|Derlen|Kaynak dosyalar ve sınıf tanımları arasındaki bağımlılık bilgilerini içeren durum dosyası. Bu, Artımlı derleme sırasında derleyici tarafından kullanılabilir. . IDB dosyasının adını belirtmek için [/FD](fd-program-database-file-name.md) derleyici seçeneğini kullanın.|
|. IDL|Derlen|Arabirim tanım dili dosyası. Daha fazla bilgi için Windows SDK [arabirim tanımı (IDL) dosyasına](/windows/win32/Rpc/the-interface-definition-language-idl-file) bakın.|
|. ilk|Bağlama|Artımlı bağlantı dosyası. Daha fazla bilgi için bkz. [/ıncreıncre.](incremental-link-incrementally.md)|
|. Map|Bağlama|Bağlayıcı bilgilerini içeren bir metin dosyası. Eşleme dosyasını adlandırmak için [/FM](fm-name-mapfile.md) derleyici seçeneğini kullanın. Daha fazla bilgi için bkz. [/Map](map-generate-mapfile.md).|
|. mfcribbon-ms|Kaynak|Şeritteki MFC düğmelerini, denetimleri ve özniteliklerini tanımlayan XML kodunu içeren bir kaynak dosyası. Daha fazla bilgi için bkz. [Şerit Tasarımcısı](../../mfc/ribbon-designer-mfc.md).|
|. obj,. o||Nesne dosyaları derlendi, ancak bağlanmadı.|
|. pch|Hata ayıklama|Ön derlenmiş üstbilgi dosyası.|
|. RC,. RC2|Kaynak|[Kaynak oluşturmak Için kaynak betik dosyaları](../../windows/working-with-resource-files.md) .|
|. sbr|Derlen|Kaynak tarayıcı ara dosyası. [BSCMAKE](bscmake-options.md)için giriş dosyası.|
|. sln|Çözüm|[Çözüm](/visualstudio/ide/solutions-and-projects-in-visual-studio) dosyası.|
|. suo|Çözüm|Çözüm seçenekleri dosyası.|
|.txt|Kaynak|Genellikle "Benioku" dosyası olan bir metin dosyası.|
|. VAP|Project|Visual Studio Analyzer proje dosyası.|
|. vbg|Çözüm|Uyumlu bir proje grubu dosyası.|
|. vbp,. Vip,. vbproj|Project|Visual Basic proje dosyası.|
|. vcxıtems|Project|Birden çok C++ projesi arasında kod dosyaları paylaşmak için paylaşılan öğeler projesi. Daha fazla bilgi için bkz. [Proje ve çözüm dosyaları](project-and-solution-files.md).|
|. vcxproj|Project|Visual Studio proje dosyası. Daha fazla bilgi için bkz. [Proje ve çözüm dosyaları](project-and-solution-files.md).|
|. vcxproj. Filters|Project|Bir projeye dosya eklemek için Çözüm Gezgini kullandığınızda kullanılır. Filtreler dosyası, dosya adı uzantısına bağlı olarak dosyayı eklemek için Çözüm Gezgini ağaç görünümünde nerede olduğunu tanımlar.|
|. VDPROJ|Project|Visual Studio dağıtımı proje dosyası.|
|.vmx|Project|Makro proje dosyası.|
|. VUP|Project|Yardımcı program proje dosyası.|

Visual Studio ile ilişkili diğer dosyalar hakkında daha fazla bilgi için bkz. [Visual Studio .net 'Te dosya türleri ve dosya uzantıları](/visualstudio/ide/reference/project-and-solution-file-types).

Proje dosyaları Çözüm Gezgini klasörler halinde düzenlenir. Visual Studio, kaynak dosyalar, üst bilgi dosyaları ve kaynak dosyaları için bir klasör oluşturur, ancak bu klasörleri yeniden düzenleyebilir veya yenilerini oluşturabilirsiniz. Bir projenin hiyerarşisinde dosyaların açıkça mantıksal kümelerini düzenlemek için klasörleri kullanabilirsiniz. Örneğin, tüm Kullanıcı arabirimi kaynak dosyalarınızı içerecek klasörler oluşturabilirsiniz. Ya da Özellikler, belgeler veya test paketleri için klasörler. Tüm dosya klasörü adları benzersiz olmalıdır.

Bir projeye bir öğe eklediğinizde, öğeyi bu proje için tüm yapılandırmalara eklersiniz. Öğe, oluşturulabilir olup olmadığına bakılmaksızın eklenir. Örneğin, MyProject adlı bir projeniz varsa, bir öğe eklemek onu hata ayıklama ve yayın projesi yapılandırmalarına ekler.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio C++ projelerini oluşturma ve yönetme](../creating-and-managing-visual-cpp-projects.md)<br>
[Visual Studio C++ proje türleri](visual-cpp-project-types.md)<br>

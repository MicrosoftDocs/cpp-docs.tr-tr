---
title: XML Belgesi Oluşturma Aracı Özellik Sayfaları
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
ms.openlocfilehash: c99677d7fc53ae3343e15e54997fe0101322fbcf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316164"
---
# <a name="xml-document-generator-tool-property-pages"></a>XML Belgesi Oluşturma Aracı Özellik Sayfaları

XML belgesi oluşturma aracı özellik sayfası xdcmake.exe'yi işlevini gösterir. xdcmake.exe'yi kaynak kodunuzu belge açıklamaları içerdiğinde bu .xdc dosyalarının bir .xml dosyasına birleştirir ve [/doc (işlem belgeleri açıklamaları) (C/C++)](doc-process-documentation-comments-c-cpp.md) belirtilirse,. Bkz: [belge açıklamaları için önerilen etiketler](recommended-tags-for-documentation-comments-visual-cpp.md) belge açıklamaları için kaynak kodu ekleme hakkında bilgi için.

> [!NOTE]
>  Komut satırında xdcmake.exe'yi kullanıldığında xdcmake.exe'yi seçenekleri geliştirme ortamında (özellik sayfaları) seçeneklerden farklıdır. Komut satırında xdcmake.exe'yi kullanma hakkında daha fazla bilgi için bkz: [XDCMake başvurusu](xdcmake-reference.md).

## <a name="uielement-list"></a>UIElement Listesi

- **Başlangıç başlığını gösterme**

   Telif hakkı iletisini bastır.

- **Ek belge dosyaları**

   Proje sisteminin .xdc dosyaları aramak istediğiniz ek dizinler. xdcmake .xdc dosyalarının proje tarafından oluşturulan her zaman arar. Birden çok dizin belirtilebilir.

- **Çıkış belgesi dosyası**

   .Xml çıkış dosyasının adını ve dizin konumu. Bkz: [derleme komutları ve özellikler için ortak makroları](common-macros-for-build-commands-and-properties.md) dizin konumları belirtmek için makroları kullanma hakkında bilgi için.

- **Belge kitaplığı bağımlılıkları**

   Projenizin çözümde bir .lib proje üzerinde bir bağımlılık varsa, geçerli proje için .xml dosyalarına .xdc dosyalarının .lib projeden işleyebilir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ projesi özellik Sayfa başvurusu](property-pages-visual-cpp.md)
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
ms.openlocfilehash: d17913909532c5bebcac712937af00be3ad98712
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335764"
---
# <a name="xml-document-generator-tool-property-pages"></a>XML Belgesi Oluşturma Aracı Özellik Sayfaları

XML Belge Jeneratör Aracı özelliği sayfası xdcmake.exe işlevselliğini ortaya çıkarır. xdcmake.exe,.xdc dosyalarını bir .xml dosyasında birleştirerek kaynak kodunuz da belge açıklamaları içerir ve [/doc (İşlem Belgeleri Yorumları) (C/C++)](doc-process-documentation-comments-c-cpp.md) belirtilir. Kaynak koduna belge açıklamaları ekleme hakkında bilgi için [Belgeler için Önerilen Etiketlere](recommended-tags-for-documentation-comments-visual-cpp.md) bakın Açıklamalar.

> [!NOTE]
> geliştirme ortamındaki xdcmake.exe seçenekleri (özellik sayfaları) komut satırında xdcmake.exe kullanıldığında seçeneklerden farklıdır. Komut satırında xdcmake.exe kullanma hakkında bilgi [için, XDCMake Başvuru](xdcmake-reference.md)bakın.

## <a name="uielement-list"></a>UIElement Listesi

- **Başlangıç Banner'ı bastır**

   Telif hakkı iletisi bastırın.

- **Ek Belge Dosyaları**

   Proje sisteminin .xdc dosyalarını aramasını istediğiniz ek dizinler. xdcmake her zaman proje tarafından oluşturulan .xdc dosyaları arar. Birden çok dizin belirtilebilir.

- **Çıktı Belge Dosyası**

   .xml çıktı dosyasının adı ve dizin konumu. Dizin konumlarını belirtmek için makroları kullanma hakkında bilgi [almak için yapı komutları ve özellikleri için ortak makrolara](common-macros-for-build-commands-and-properties.md) bakın.

- **Belge Kitaplığı Bağımlılıkları**

   Projenizde çözümde .lib projesine bağımlıysa, .lib projesindeki .xdc dosyalarını geçerli proje için .xml dosyalarına işleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[C++ proje özelliği sayfası başvurusu](property-pages-visual-cpp.md)

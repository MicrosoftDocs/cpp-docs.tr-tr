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
ms.openlocfilehash: 9f10ddf98c238120750e72644779a6ad74af2d1e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171638"
---
# <a name="xml-document-generator-tool-property-pages"></a>XML Belgesi Oluşturma Aracı Özellik Sayfaları

XML belgesi Oluşturucu aracı özellik sayfası xdcmake. exe ' nin işlevlerini gösterir. kaynak kodunuz belge açıklamalarını içerdiğinde ve [/doc (işlem belgeleri açıklamaları) (C/C++)](doc-process-documentation-comments-c-cpp.md) belirtildiğinde xdcmake. exe. xdc dosyalarını bir. xml dosyasına birleştirir. Kaynak koduna belge açıklamaları ekleme hakkında bilgi için bkz. [belge açıklamaları Için önerilen Etiketler](recommended-tags-for-documentation-comments-visual-cpp.md) .

> [!NOTE]
>  geliştirme ortamındaki xdcmake. exe seçenekleri (Özellik sayfaları), xdcmake. exe komut satırında kullanıldığında seçeneklerinizden farklıdır. Komut satırında xdcmake. exe kullanma hakkında bilgi için bkz. [XDCMake başvurusu](xdcmake-reference.md).

## <a name="uielement-list"></a>UIElement Listesi

- **Başlangıç başlığını gösterme**

   Telif hakkı iletisini gizleyin.

- **Ek belge dosyaları**

   Proje sisteminin. xdc dosyalarını arayacağını istediğiniz ek dizinler. XDCMake, proje tarafından oluşturulan. xdc dosyalarını her zaman arayacaktır. Birden çok dizin belirtilebilir.

- **Çıkış belgesi dosyası**

   . Xml çıkış dosyasının adı ve dizin konumu. Dizin konumlarını belirtmek için makroları kullanma hakkında bilgi için bkz. [derleme komutları ve özellikleri Için ortak makrolar](common-macros-for-build-commands-and-properties.md) .

- **Belge kitaplığı bağımlılıkları**

   Projeniz çözümdeki bir. lib projesine bağımlılığı varsa,. xdc dosyalarını. lib projesinden geçerli proje için. xml dosyalarına işleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[C++Proje özellik sayfası başvurusu](property-pages-visual-cpp.md)

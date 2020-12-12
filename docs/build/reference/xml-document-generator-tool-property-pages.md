---
description: 'Daha fazla bilgi edinin: XML belgesi Oluşturucu aracı özellik sayfaları'
title: XML Belgesi Oluşturma Aracı Özellik Sayfaları
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
ms.openlocfilehash: e344d8ef796a5c3455c88851a1fc410801b991bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260975"
---
# <a name="xml-document-generator-tool-property-pages"></a>XML Belgesi Oluşturma Aracı Özellik Sayfaları

XML belgesi Oluşturucu aracı özellik sayfası xdcmake.exe işlevlerini gösterir. xdcmake.exe, kaynak kodunuz belge açıklamalarını içerdiğinde. xdc dosyalarını bir. xml dosyasına birleştirir ve [/doc (Işlem belgeleri açıklamaları) (C/C++)](doc-process-documentation-comments-c-cpp.md) belirtilir. Kaynak koduna belge açıklamaları ekleme hakkında bilgi için bkz. [belge açıklamaları Için önerilen Etiketler](recommended-tags-for-documentation-comments-visual-cpp.md) .

> [!NOTE]
> Geliştirme ortamındaki (Özellik sayfaları) xdcmake.exe seçenekler, komut satırında xdcmake.exe kullanıldığında bulunan seçeneklerden farklıdır. Komut satırında xdcmake.exe kullanma hakkında daha fazla bilgi için bkz. [XDCMake başvurusu](xdcmake-reference.md).

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

[C++ proje özellik sayfası başvurusu](property-pages-visual-cpp.md)

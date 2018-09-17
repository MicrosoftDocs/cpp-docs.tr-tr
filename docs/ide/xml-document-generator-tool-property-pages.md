---
title: XML belgesi oluşturma aracı özellik sayfaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
dev_langs:
- C++
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ee18e32d1aaf2a9035b425cb3c3ef5e2db15145
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718815"
---
# <a name="xml-document-generator-tool-property-pages"></a>XML Belgesi Oluşturma Aracı Özellik Sayfaları
XML belgesi oluşturma aracı özellik sayfası xdcmake.exe'yi işlevini gösterir. xdcmake.exe'yi kaynak kodunuzu belge açıklamaları içerdiğinde bu .xdc dosyalarının bir .xml dosyasına birleştirir ve [/doc (işlem belgeleri açıklamaları) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md) belirtilirse,. Bkz: [belge açıklamaları için önerilen etiketler](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) belge açıklamaları için kaynak kodu ekleme hakkında bilgi için.  
  
> [!NOTE]
>  Komut satırında xdcmake.exe'yi kullanıldığında xdcmake.exe'yi seçenekleri geliştirme ortamında (özellik sayfaları) seçeneklerden farklıdır. Komut satırında xdcmake.exe'yi kullanma hakkında daha fazla bilgi için bkz: [XDCMake başvurusu](../ide/xdcmake-reference.md).  
  
## <a name="uielement-list"></a>UIElement Listesi  
- **Başlangıç başlığını gösterme**

   Telif hakkı iletisini bastır.  
  
- **Ek belge dosyaları**

   Proje sisteminin .xdc dosyaları aramak istediğiniz ek dizinler. xdcmake .xdc dosyalarının proje tarafından oluşturulan her zaman arar. Birden çok dizin belirtilebilir.  
  
- **Çıkış belgesi dosyası**

   .Xml çıkış dosyasının adını ve dizin konumu. Bkz: [genel derleme komutları ve Özellikler makroları](../ide/common-macros-for-build-commands-and-properties.md) dizin konumları belirtmek için makroları kullanma hakkında bilgi için.  
  
- **Belge kitaplığı bağımlılıkları**

   Projenizin çözümde bir .lib proje üzerinde bir bağımlılık varsa, geçerli proje için .xml dosyalarına .xdc dosyalarının .lib projeden işleyebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../ide/property-pages-visual-cpp.md)   
 [Özellik Sayfaları](../ide/property-pages-visual-cpp.md)
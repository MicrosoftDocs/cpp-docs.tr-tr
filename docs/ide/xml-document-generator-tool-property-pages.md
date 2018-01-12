---
title: "XML belgesi oluşturma aracı özellik sayfaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
dev_langs: C++
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc09dafc0f07bc16a11dd255419440b6464456c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="xml-document-generator-tool-property-pages"></a>XML Belgesi Oluşturma Aracı Özellik Sayfaları
XML belgesi oluşturma aracı özellik sayfası xdcmake.exe işlevselliğini kullanıma sunar. xdcmake.exe kaynak kodunuzu belge açıklamaları içerdiğinde bu .xdc dosyaları bir .xml dosyasına birleştirir ve [/doc (işlem belgesi açıklamaları) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md) belirtilirse,. Bkz: [belge açıklamaları için önerilen etiketler](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) kaynak koduna belge açıklamaları ekleme hakkında bilgi için.  
  
> [!NOTE]
>  Komut satırında xdcmake.exe kullanıldığında, geliştirme ortamı (özellik sayfaları) xdcmake.exe seçeneklerinde seçeneklerinden farklılık gösterir. Komut satırında xdcmake.exe kullanma hakkında daha fazla bilgi için bkz: [XDCMake başvurusu](../ide/xdcmake-reference.md).  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Başlangıç başlığını gösterme**  
 Telif hakkı iletisi engelleyin.  
  
 **Ek belge dosyaları**  
 Ek dizinler .xdc dosyaları aramak için proje sistemi istiyor. xdcmake her zaman proje tarafından oluşturulan .xdc dosyaları arar. Birden çok dizin belirtilebilir.  
  
 **Çıktı belge dosyası**  
 .Xml çıkış dosyasının adını ve dizin konumu. Bkz: [derleme komutları ve özellikler için ortak makrolar](../ide/common-macros-for-build-commands-and-properties.md) directory konumlarını belirtmek için makroları kullanma hakkında bilgi için.  
  
 **Belge kitaplığı bağımlılıkları**  
 Projenizin çözümdeki .lib projedeki bir bağımlılık varsa, geçerli projenin .xml dosyalarına .lib projeden .xdc dosyalarını işleyebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../ide/property-pages-visual-cpp.md)   
 [Özellik Sayfaları](../ide/property-pages-visual-cpp.md)
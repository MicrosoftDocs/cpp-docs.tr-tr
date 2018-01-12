---
title: "MFC Uygulama Mimarisi sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.mfc
dev_langs: C++
helpviewer_keywords:
- MFC, classes
- MFC, application development
- classes [MFC], MFC
- application architecture classes [MFC]
ms.assetid: 71b2de54-b44d-407e-9c71-9baf954e18d9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 623775d6c3306ba4afdb01eb78ea70b05f7a3365
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-application-architecture-classes"></a>MFC Uygulama Mimarisi Sınıfları
Bu kategorideki sınıfları framework uygulaması mimarisini katkıda. Bunların çoğu uygulamaları için ortak işlevselliği sağlar. Uygulamaya özel işlevsellik eklemek için Framework'te doldurun. Genellikle, yeni sınıflar mimarisi sınıflarından türetme ve yeni üye ekleme veya var olan üye işlevlerini geçersiz kılma bunu.  
  
 [Uygulama sihirbazları](../mfc/reference/mfc-application-wizard.md) çeşitli uygulamaları, farklı şekillerde tümü kullanan uygulama çerçevesi oluşturur. (Tek belge arabirimi) SDI ve MDI (birden çok belge arabirimi) uygulamaları belge/görünüm mimarisinin adlı framework'ün bir parçası tam kullanılmasını sağlamak. İletişim tabanlı uygulamalar, form tabanlı uygulamalar ve DLL'ler gibi uygulamalarının diğer türleri yalnızca bazı belge/görünüm mimarisi özellikleri kullanın.  
  
 Belge/görünüm uygulamaları bir veya daha fazla kümesi belgeler, görünümler ve çerçeve pencereleri içerir. Belge şablonu nesnesi için her bir belge/görünüm/çerçeve kümesi sınıfları ilişkilendirir.  
  
 Belge/görünüm mimarisinin MFC uygulamanızda kullanmak zorunda değil olmasa da, çok sayıda Bunun yapılması için avantaj vardır. MFC OLE kapsayıcı ve sunucu desteği, yazdırmayı ve baskı önizlemeyi desteği gibi belge/görünüm mimarisi hakkında temel alır.  
  
 En az iki nesnelerinin tüm MFC uygulamaları vardır: uygulama nesnesi türetilmiş [CWinApp](../mfc/reference/cwinapp-class.md)ve bazı sıralama (genellikle dolaylı olarak) türetilmiş ana penceresi nesnesinin [CWnd](../mfc/reference/cwnd-class.md). (Genellikle, ana pencereyi türetildiği [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), veya [CDialog](../mfc/reference/cdialog-class.md), her biri türetilmiş `CWnd`.)  
  
 Belge/görünüm mimarisi kullanan uygulamaları ek nesneleri içerir. Asıl nesneler şunlardır:  
  
-   Uygulama nesnesi sınıfından türetilen [CWinApp](../mfc/reference/cwinapp-class.md), önceden belirtildiği gibi.  
  
-   Bir veya daha fazla belge sınıfı nesneleri sınıfından türetilen [CDocument](../mfc/reference/cdocument-class.md). Belge sınıfı nesneleri görünümünde yönetilen veri iç gösterimini sorumludur. Bunlar, bir veri dosyası ile ilişkili olabilir.  
  
-   Bir veya daha fazla görünüm nesneleri sınıfından türetilen [CView](../mfc/reference/cview-class.md). Her görünüm, bir belgeye eklenmiş ve çerçeve penceresi ile ilişkili bir penceredir. Görünümleri görüntülemek ve bir belge sınıfı nesnesinde bulunan verileri arabirimidir.  
  
 Belge/görünüm uygulamaları da içeren çerçeve pencereleri (türetilmiş [CFrameWnd](../mfc/reference/cframewnd-class.md)) ve belge şablonları (türetilmiş [CDocTemplate](../mfc/reference/cdoctemplate-class.md)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)


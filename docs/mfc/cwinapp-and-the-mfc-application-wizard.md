---
title: CWinApp ve MFC Uygulama Sihirbazı'nı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWinApp
dev_langs:
- C++
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d40f314c7717d2e69b2b4802bf9c2c5468511db5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341267"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp ve MFC Uygulama Sihirbazı
Bir uygulama sınıfı türetilen bir iskelet uygulama oluşturduğunda, MFC Uygulama Sihirbazı'nı bildirir [CWinApp](../mfc/reference/cwinapp-class.md). MFC Uygulama Sihirbazı'nı, ayrıca aşağıdaki öğeleri içeren bir uygulama dosyası oluşturur:  
  
-   Uygulama sınıfı için ileti eşlemesi.  
  
-   Bir boş sınıf oluşturucu.  
  
-   Bir ve yalnızca nesne sınıfının bildirir değişkeni.  
  
-   Standart bir uygulaması, `InitInstance` üye işlevi.  
  
 Uygulama sınıfı proje başlığı ve ana kaynak dosyalarında yerleştirilir. Oluşturulan dosyalar ve sınıf adları, MFC Uygulama Sihirbazı'nda sağladığınız proje adı dayanır. Bu sınıfların kodunu görüntülemek için kolay yolunu [sınıf görünümü](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925).  
  
 Standart uygulamaları ve sağlanan ileti eşlemesi birçok amaç için yeterli olur, ancak bunları gerektiği şekilde değiştirebilirsiniz. Bu uygulamalar en ilginç `InitInstance` üye işlevi. Genellikle, iskelet uygulaması için kod ekleyeceksiniz `InitInstance`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinApp: Uygulama sınıfı](../mfc/cwinapp-the-application-class.md)   
 [Geçersiz kılınabilir CWinApp üye işlevleri](../mfc/overridable-cwinapp-member-functions.md)   
 [Özel CWinApp Hizmetleri](../mfc/special-cwinapp-services.md)


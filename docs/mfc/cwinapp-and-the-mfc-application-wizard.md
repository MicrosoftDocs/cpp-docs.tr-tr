---
title: "CWinApp ve MFC Uygulama Sihirbazı'nı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CWinApp
dev_langs: C++
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 603504025bf4069f7a56b705e50a176975dbf244
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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


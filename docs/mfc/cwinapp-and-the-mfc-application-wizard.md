---
title: CWinApp ve MFC Uygulama Sihirbazı | Microsoft Docs
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
ms.openlocfilehash: 702c20fc9f303670d2add4ebf840785acff7750d
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026491"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp ve MFC Uygulama Sihirbazı
İskelet bir uygulama oluşturduğunda, MFC Uygulama Sihirbazı, bir uygulama sınıfı türetilen bildirir [CWinApp](../mfc/reference/cwinapp-class.md). MFC Uygulama Sihirbazı, aşağıdaki öğeleri içeren bir uygulama dosyasını da oluşturur:  
  
-   Uygulama sınıfı için ileti eşlemesi.  
  
-   Bir boş sınıf oluşturucu.  
  
-   Değişken yalnızca sınıf nesnesi bildirir.  
  
-   Standart bir uygulaması, `InitInstance` üye işlevi.  
  
 Proje başlığı ve ana kaynak dosyalarında uygulama sınıfı yerleştirilir. Oluşturulan dosyalar ve sınıf adları MFC Uygulama Sihirbazı'nda sağladığınız proje adı temel alır. Bu sınıfların kodunu görüntülemek için en kolay yolu aracılığıyladır [sınıf görünümü](http://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925).  
  
 Standart uygulamalar ve sağlanan ileti eşlemesi birçok amaç için uygundur, ancak bunları gerektiği şekilde değiştirebilirsiniz. Bu uygulamalar en ilginç `InitInstance` üye işlevi. Genellikle, iskelet uygulanması için kod ekleyeceksiniz `InitInstance`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinApp: Uygulama sınıfı](../mfc/cwinapp-the-application-class.md)   
 [Geçersiz kılınabilir CWinApp üye işlevleri](../mfc/overridable-cwinapp-member-functions.md)   
 [Özel CWinApp Hizmetleri](../mfc/special-cwinapp-services.md)


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
ms.openlocfilehash: 59fcd3f00fb8998cf90c88d574b9d22051cb4305
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687790"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp ve MFC Uygulama Sihirbazı
İskelet bir uygulama oluşturduğunda, MFC Uygulama Sihirbazı, bir uygulama sınıfı türetilen bildirir [CWinApp](../mfc/reference/cwinapp-class.md). MFC Uygulama Sihirbazı, aşağıdaki öğeleri içeren bir uygulama dosyasını da oluşturur:  
  
-   Uygulama sınıfı için ileti eşlemesi.  
  
-   Bir boş sınıf oluşturucu.  
  
-   Değişken yalnızca sınıf nesnesi bildirir.  
  
-   Standart bir uygulaması, `InitInstance` üye işlevi.  
  
 Proje başlığı ve ana kaynak dosyalarında uygulama sınıfı yerleştirilir. Oluşturulan dosyalar ve sınıf adları MFC Uygulama Sihirbazı'nda sağladığınız proje adı temel alır. Bu sınıfların kodunu görüntülemek için en kolay yolu aracılığıyladır [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Standart uygulamalar ve sağlanan ileti eşlemesi birçok amaç için uygundur, ancak bunları gerektiği şekilde değiştirebilirsiniz. Bu uygulamalar en ilginç `InitInstance` üye işlevi. Genellikle, iskelet uygulanması için kod ekleyeceksiniz `InitInstance`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinApp: Uygulama sınıfı](../mfc/cwinapp-the-application-class.md)   
 [Geçersiz kılınabilir CWinApp üye işlevleri](../mfc/overridable-cwinapp-member-functions.md)   
 [Özel CWinApp Hizmetleri](../mfc/special-cwinapp-services.md)


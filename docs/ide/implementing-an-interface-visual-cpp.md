---
title: Arabirim (Visual C++) uygulama | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: interfaces, implementing
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: caea9442973d131e99b3f52ca36a6cf991f2410a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="implementing-an-interface-visual-c"></a>Arabirimi Uygulama (Visual C++)
Bir arabirim için bir proje ATL COM uygulamanın veya ATL desteği içeren bir MFC uygulaması olarak oluşturmuş olmanız gerekir. Kullanabileceğiniz [ATL Proje Sihirbazı](../atl/reference/atl-project-wizard.md) bir ATL uygulama oluşturmak için veya [ATL nesne MFC uygulamanıza eklemek](../mfc/reference/adding-atl-support-to-your-mfc-project.md) MFC uygulaması için ATL desteği uygulamak için.  
  
 Bir arabirim için projesi oluşturduktan sonra bir ATL nesne eklemeniz gerekir. Bkz: [nesneleri ekleme ve denetimleri için ATL projesinde](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) nesneleri ATL projenize ekleyin sihirbazları listesi.  
  
> [!NOTE]
>  Sihirbaz ATL iletişim kutuları, ATL, performans nesneleri ve performans sayaçlarını kullanarak XML Web Hizmetleri desteklemiyor.  
  
 Varsa, [ATL Denetim Ekleme](../atl/reference/adding-an-atl-control.md), listelenen varsayılan arabirimlerini belirtebilirsiniz [arabirimleri](../atl/reference/interfaces-atl-control-wizard.md) sayfasında, Sihirbazı ve atlcom.h olarak tanımlanmış.  
  
 Nesne veya denetim ekledikten sonra arabirim Uygulama Sihirbazı'nı kullanarak tüm kullanılabilir türü kitaplığında yer alan diğer arabirimleri uygulayabilir.  
  
 Projenin .idl dosyaya yeni bir arabirimi ekliyorsanız, el ile eklemelisiniz. Bkz: [ATL projesinde yeni bir arabirim ekleme](../atl/reference/adding-a-new-interface-in-an-atl-project.md) daha fazla bilgi için.  
  
### <a name="to-implement-an-interface"></a>Arabirim uygulamak için  
  
1.  Sınıf Görünümü'nde ATL nesnesi için sınıf adını sağ tıklatın.  
  
2.  Tıklatın **Ekle** kısayol menüsünden ve ardından **arabirimi uygulama** görüntülemek için [arabirim Uygulama Sihirbazı](../ide/implement-interface-wizard.md).  
  
3.  ' I tıklatın ve uygun tür kitaplıklarından uygulanması için arabirimleri seçin **son**.  
  
4.  Sınıf Görünümü'nde nesnenin tabanları genişletin ve arabirimleri düğüm uyguladık ve kullanılabilir özellikler, yöntemleri ve olayları görmek için arabirimin düğümünü genişletin arabirimi bakın.  
  
    > [!NOTE]
    >  Aynı zamanda [Nesne Tarayıcısı](http://msdn.microsoft.com/en-us/f89acfc5-1152-413d-9f56-3dc16e3f0470) arabirimi üyeleri incelemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM arabirimi oluşturma](../ide/creating-a-com-interface-visual-cpp.md)   
 [COM arabirimini düzenleme](../ide/editing-a-com-interface.md)
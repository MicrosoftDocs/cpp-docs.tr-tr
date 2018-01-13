---
title: "Nesneleri ve denetimleri için ATL projesinde ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.appwiz.ATL.controls
dev_langs: C++
helpviewer_keywords:
- ATL projects, adding objects
- wizards [C++], ATL projects
- ATL projects, adding controls
- controls [ATL], adding to projects
- objects [C++], adding to ATL projects
- ATL Control Wizard
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 319d130b9d8f17875aaa8bac15f546401457b963
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-objects-and-controls-to-an-atl-project"></a>Nesneleri ve denetimleri için ATL projesinde ekleme
ATL veya MFC tabanlı projelerinizi bir nesneyi veya bir denetim eklemek için ATL kodu sihirbazlardan birini kullanabilirsiniz. Her COM nesnesi veya denetim için eklediğiniz, sihirbaz .cpp ve .h dosyaları yanı sıra, kayıt defteri betik tabanlı desteği için bir .rgs dosyası oluşturur. Aşağıdaki ATL kodu sihirbazlar Visual Studio'da kullanılabilir:  
  
||||  
|-|-|-|  
|[ATL Basit Nesne](../../atl/reference/atl-simple-object-wizard.md)|[ATL iletişim](../../atl/reference/atl-dialog-wizard.md)|[ATL denetimi](../../atl/reference/atl-control-wizard.md)|  
|[ATL özellik sayfası](../../atl/reference/atl-property-page-wizard.md)|[ATL Active Server sayfası bileşeni](../../atl/reference/atl-active-server-page-component-wizard.md)|[ATL OLE DB Tüketicisi](../../atl/reference/atl-ole-db-consumer-wizard.md)|  
|[MFC için ATL desteği ekleme](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)|[ATL COM+ 1.0 Bileşeni Sihirbazı](../../atl/reference/atl-com-plus-1-0-component-wizard.md)|[ATL OLE DB sağlayıcısı](../../atl/reference/atl-ole-db-provider-wizard.md)|  
  
> [!NOTE]
>  Projenize ATL nesneyi eklemeden önce Ayrıntılar ve gereksinimler için kendi ilgili Yardım konuları nesnesinde gözden geçirmelidir.  
  
### <a name="to-add-an-object-or-a-control-using-the-atl-control-wizard"></a>Bir nesne veya ATL Denetim Sihirbazı'nı kullanarak denetim eklemek için  
  
1.  Çözüm Gezgini'nde, proje düğümüne sağ tıklatın ve **Ekle** kısayol menüsünden. Tıklatın **sınıfı ekleme**.  
  
     [Sınıfı Ekle](../../ide/add-class-dialog-box.md) iletişim kutusu görüntülenir.  
  
2.  ATL klasörü kategoriler Bölmesi'nde seçili şablonları bölmesinden eklemek için bir nesne seçin. Tıklatın **açık**. Seçili nesne için kod Sihirbazı görünür.  
  
    > [!NOTE]
    >  MFC projesinde ATL nesneyi eklemek istiyorsanız, varolan bir projeye ATL desteği eklemeniz gerekir. Bu yönergeleri izleyerek yapmak [MFC projenize ATL desteği ekleme](../../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
     Alternatif olarak, daha önce ATL desteğini eklemeden MFC projenize ATL nesne eklemeye çalışırsanız, Visual Studio projenize eklenen ATL desteği isteyip istemediğinizi belirtmenizi ister. Tıklatın **Evet** projenize ATL desteği ekleyin ve seçili ATL Sihirbazı'nı açın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL Proje Sihirbazı](../../atl/reference/atl-project-wizard.md)   
 [Visual C++ proje türleri](../../ide/visual-cpp-project-types.md)   
 [Uygulama sihirbazları kullanarak masaüstü projeleri oluşturma](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL COM nesneleri temelleri](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATL ve C çalışma zamanı koduyla programlama](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Varsayılan ATL Projesi Yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)


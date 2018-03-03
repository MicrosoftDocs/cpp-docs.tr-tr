---
title: "MFC ActiveX Denetim Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.ctl.overview
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], MFC
- MFC ActiveX controls [MFC], wizards
- OLE controls [MFC], creating
- MFC ActiveX Control Wizard
- OLE controls [MFC]
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82e562ceb73da2b103360ab9607cecbbe9f1da02
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-control-wizard"></a>MFC ActiveX Denetim Sihirbazı
ActiveX denetimi belirli bir türde değil [Otomasyon sunucusu](../../mfc/automation-servers.md); yeniden kullanılabilir bir bileşendir. ActiveX denetimi barındırma uygulama [otomasyon istemci](../../mfc/automation-clients.md) bu denetimin. Amacınız yeniden kullanılabilir bir bileşen oluşturmak için ise, bu Sihirbazı, bir denetim oluşturmak için kullanın. Bkz: [MFC ActiveX denetimleri](../../mfc/mfc-activex-controls.md) daha fazla bilgi için.  
  
 Alternatif olarak, Otomasyon sunucusu MFC kullanarak bir uygulama oluşturabilirsiniz [MFC Uygulama Sihirbazı'nı](../../mfc/reference/mfc-application-wizard.md).  
  
 Bu sihirbaz kullanılarak oluşturulan bir ActiveX denetimini bir kullanıcı arabirimine sahip veya görünmez olabilir. Bu seçenek belirtebilir [denetim ayarlarını](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) sihirbaz sayfasında. Bir zamanlayıcı denetimi görünmez olmasını istediğiniz bir ActiveX denetimi örneğidir.  
  
 ActiveX denetimlerini karmaşık kullanıcı arabirimi olabilir. Bazı denetimler kapsüllenmiş formlar gibi olabilir: çoğu içeren tek bir denetim alanları, her bir Windows denetimi, kendi içinde. Örneğin, bir MFC ActiveX denetimi olarak uygulanan bir otomatik bölümleri nesne bir form benzeri kullanıcı arabirimi üzerinden kullanıcılar tarafından okunabilir ve parça numarası, parça ad ve diğer bilgileri Düzenle sunabilir. Bkz: [MFC ActiveX denetimleri](../../mfc/mfc-activex-controls.md) daha fazla bilgi için.  
  
 ActiveX nesneleri için bir kapsayıcı oluşturmanız gerekiyorsa, bkz: [bir ActiveX denetimi kapsayıcısı oluşturma](../../mfc/reference/creating-an-mfc-activex-control-container.md).  
  
 MFC starter program C++ kaynak (.cpp) dosyaları, kaynak (.rc) dosyaları ve bir proje (.vcxproj) dosyası içerir. Bu Başlatıcı dosyalarda oluşturulan kodu MFC temel alır.  
  
 Aşağıdaki örnek listesi görevleri ve ActiveX denetimi için geliştirmeler türleri gösterilmektedir:  
  
-   [ActiveX denetimi en iyi duruma getirme](../../mfc/mfc-activex-controls-optimization.md)  
  
-   [Bir ActiveX denetimine stok olaylar ekleme](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [Özel olaylar ekleme](../../mfc/mfc-activex-controls-adding-custom-events.md)  
  
-   [Stok yöntemler ekleme](../../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [Özel yöntemler ekleme](../../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [Stok Özellikler ekleme](../../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [Özel Özellikler ekleme](../../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [Bir ActiveX denetim kapsayıcısındaki ActiveX denetimlerini programlama](../../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
## <a name="overview"></a>Genel Bakış  
 Bu sihirbaz sayfası oluşturmakta olduğunuz MFC ActiveX denetim projesi için geçerli uygulama ayarlarını açıklar. Varsayılan olarak, sihirbaz aşağıdaki gibi bir proje oluşturur:  
  
-   Varsayılan proje çalışma zamanı lisans ya da Yardım dosyaları oluşturur. Bu varsayılan ayarları değiştirebilirsiniz [uygulama ayarları](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) sayfası. ActiveX Denetim Sihirbazı'nı bu sayfada yaptığınız seçimleri yansıtılır **genel bakış** sayfası.  
  
-   Proje bir denetim ve proje adını temel alarak bir özellik sayfası sınıfı içerir. Proje ve dosya adları adlarını düzenleyebileceğiniz [denetim adlarının](../../mfc/reference/control-names-mfc-activex-control-wizard.md) sayfası.  
  
-   Denetim hiçbir var olan Windows denetimine bağlı, görünür hale gelir, bir kullanıcı arabirimine sahiptir ve içerir etkinleştirir bir **hakkında** iletişim kutusu. Bu varsayılan ayarları değiştirebilirsiniz [denetim ayarlarını](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfası.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ proje oluşturma ve yönetme](../../ide/creating-and-managing-visual-cpp-projects.md)   
 [Visual C++ proje türleri](../../ide/visual-cpp-project-types.md)   
 [Kavramları](../../atl/active-template-library-atl-concepts.md)


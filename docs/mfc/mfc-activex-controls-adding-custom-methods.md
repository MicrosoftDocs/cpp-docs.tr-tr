---
title: "MFC ActiveX denetimleri: Özel yöntemler ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
- PtInCircle custom method [MFC]
ms.assetid: 8f8dc344-44a0-4021-8db5-4cdd3d700e18
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2f79d4c5f7407e3de12ccf180a68b2b22e35bf10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-adding-custom-methods"></a>MFC ActiveX Denetimleri: Özel Yöntemler Ekleme
Bunlar zaten tarafından uygulanmaz, özel yöntemler farklı stok yöntemleri `COleControl`. Denetiminize eklediğiniz her özel yöntem uygulamasını sağlamanız gerekir.  
  
 ActiveX denetimi kullanıcısı özel bir yöntem özel denetim eylemleri gerçekleştirmek için herhangi bir zamanda çağırabilirsiniz. Özel yöntemler için gönderme eşleme girişi biçimidir `DISP_FUNCTION`.  
  
##  <a name="_core_adding_a_custom_method_with_classwizard"></a>Özel bir yöntemle ekleme yöntem Ekleme Sihirbazı  
 Aşağıdaki yordamda bir ActiveX denetiminin iskelet kodu Ptıncircle özel yöntemi ekleme gösterilmektedir. Ptıncircle denetime geçirilen koordinatları içinde veya dışında daireye olup olmadığını belirler. Bu yordamı, diğer özel yöntemler eklemek için de kullanılabilir. Özel yöntem adınızı ve parametreleri Ptıncircle yöntemi adını ve parametreleri için yerleştirin.  
  
> [!NOTE]
>  Bu örnekte `InCircle` olayları makaleden işlevi. Bu işlev hakkında daha fazla bilgi için bkz: [MFC ActiveX denetimleri: ActiveX denetimini özel olaylar ekleme](../mfc/mfc-activex-controls-adding-custom-events.md).  
  
#### <a name="to-add-the-ptincircle-custom-method-using-the-add-method-wizard"></a>Yöntem Ekleme Sihirbazı'nı kullanarak Ptıncircle özel yöntemi eklemek için  
  
1.  Denetimin proje yükleyin.  
  
2.  Sınıf Görünümü'nde denetiminizin kitaplığı düğümünü genişletin.  
  
3.  Arabirim (kitaplık düğümünün İkinci düğüm) denetlemek için kısayol menüsünü açmak için düğümü.  
  
4.  Kısayol menüsünden tıklatın **Ekle** ve ardından **ekleme yöntemi**.  
  
     Bu yöntem Ekleme Sihirbazı'nı açar.  
  
5.  İçinde **yöntem adı** kutusuna `PtInCircle`.  
  
6.  İçinde **iç adı** kutusunda, yöntemin iç işlevin adını yazın veya varsayılan değeri kullanın (Bu durumda, `PtInCircle`).  
  
7.  İçinde **dönüş türü** kutusunda, **VARIANT_BOOL** yöntemin dönüş türü.  
  
8.  Kullanarak **parametre türü** ve **parametre adı** denetimleri, adında bir parametre eklemek `xCoord` (tür **OLE_XPOS_PIXELS**).  
  
9. Kullanarak **parametre türü** ve **parametre adı** denetimleri, adında bir parametre eklemek `yCoord` (tür **OLE_YPOS_PIXELS**).  
  
10. **Son**'a tıklayın.  
  
##  <a name="_core_classwizard_changes_for_custom_methods"></a>Yöntem Sihirbazı değişiklikleri için özel yöntemler ekleme  
 Özel bir yöntem eklediğinizde, yöntem Ekleme Sihirbazı'nı bazı değişiklikler denetim sınıfı başlığına hale getirir. (. Y) ve uygulama (. CPP) dosyaları. Aşağıdaki satırı control sınıfı üstbilgisini gönderme harita bildiriminde eklenir (. H) dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#18](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_1.h)]  
  
 Bu kod adlı bir dağıtım yöntemi işleyicisi bildirir `PtInCircle`. Bu işlev dış adı Ptıncircle kullanarak denetim kullanıcı tarafından çağrılabilir.  
  
 Aşağıdaki satırı denetimin eklenir. IDL dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#19](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_2.idl)]  
  
 Bu satırı Ptıncircle yöntemi belirli bir kimlik numarası, yöntem Ekleme Sihirbazı'nı yöntemler ve özellikler listesinde yöntemin konuma atar. Yöntem Ekleme Sihirbazı'nı özel yöntem eklemek için kullanıldığından, bu girişini otomatik olarak projenin eklendi. IDL dosyası.  
  
 Ayrıca, aşağıdaki satırı bulunan uygulamasında (. Denetim sınıfı CPP) dosyasının denetimin gönderme haritaya eklenir:  
  
 [!code-cpp[NVC_MFC_AxUI#20](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_3.cpp)]  
  
 `DISP_FUNCTION` Makrosu eşlemeleri Ptıncircle yöntemi denetimin işleyici işleve `PtInCircle`, dönüş türü olarak bildirir **VARIANT_BOOL**ve türünde iki parametre bildirir **vts_xpos_pıxels** ve **VTS_YPOSPIXELS** geçirilecek `PtInCircle`.  
  
 Son olarak, yöntem Ekleme Sihirbazı'nı saplama işlevi ekler `CSampleCtrl::PtInCircle` denetimin uygulama altına (. CPP) dosyası. İçin `PtInCircle` daha önce belirtildiği gibi çalışması için bunu şu şekilde değiştirilmelidir:  
  
 [!code-cpp[NVC_MFC_AxUI#21](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_4.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [Sınıf Görünümü ve Nesne Tarayıcısı Simgeleri](/visualstudio/ide/class-view-and-object-browser-icons)


---
title: "MFC ActiveX denetimleri: Stok yöntemler ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], stock methods
- MFC ActiveX controls [MFC], methods
- DoClick method [MFC]
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2531f84974626fcdb364df67b12f27d61e75a62a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-adding-stock-methods"></a>MFC ActiveX Denetimleri: Stok Yöntemler Ekleme
Stok yöntemi bir özel yönteminden farklıdır sınıfı tarafından zaten uygulanmış [COleControl](../mfc/reference/colecontrol-class.md). Örneğin, `COleControl` denetiminiz için yenileme yöntemi destekleyen önceden tanımlanmış üye işlevi içeriyor. Stok bu yöntem için gönderme harita giriş **DISP_STOCKFUNC_REFRESH**.  
  
 `COleControl`Stok iki yöntemi destekler: DoClick ve yenileyin. Yenileme denetimin görünümünü hemen güncelleştirmek için denetimin kullanıcı tarafından çağrılır; Denetimin tıklatın tetiklenecek DoClick çağrılan olay.  
  
|Yöntem|Gönderme eşleme girişi|Yorum|  
|------------|------------------------|-------------|  
|`DoClick`|**DISP_STOCKPROP_DOCLICK)**|Click olayını tetikler.|  
|**Yenileme**|**DISP_STOCKPROP_REFRESH)**|Denetimin görünümünü hemen güncelleştirir.|  
  
##  <a name="_core_adding_a_stock_method_using_classwizard"></a>Stok yöntemi kullanarak ekleme yöntem Ekleme Sihirbazı  
 Stok yöntem ekleme basittir kullanarak [yöntem Ekleme Sihirbazı'nı](../ide/add-method-wizard.md). Aşağıdaki yordamda, MFC ActiveX Denetim Sihirbazı kullanılarak oluşturulan bir denetime Refresh yöntemi ekleme gösterilmektedir.  
  
#### <a name="to-add-the-stock-refresh-method-using-the-add-method-wizard"></a>Yöntem Ekleme Sihirbazı'nı kullanarak stok yenileme yöntemini eklemek için  
  
1.  Denetiminizin proje yükleyin.  
  
2.  Sınıf Görünümü'nde denetiminizin kitaplığı düğümünü genişletin.  
  
3.  Arabirim (kitaplık düğümünün İkinci düğüm) denetlemek için kısayol menüsünü açmak için düğümü.  
  
4.  Kısayol menüsünden tıklatın **Ekle** ve ardından **ekleme yöntemi**.  
  
     Bu yöntem Ekleme Sihirbazı'nı açar.  
  
5.  İçinde **yöntem adı** kutusunda, **yenileme**.  
  
6.  **Son**'a tıklayın.  
  
##  <a name="_core_classwizard_changes_for_stock_methods"></a>Yöntemi Sihirbazı değişiklikleri için stok yöntemler ekleme  
 Stok yenileme yöntemi denetimin temel sınıfı tarafından desteklenmediği için **yöntem Ekleme Sihirbazı'nı** denetimin sınıf bildirimi herhangi bir şekilde değiştirmez. Denetimin gönderme harita ve çok yöntemi için bir giriş ekler. IDL dosyası. Denetimin gönderme eşlemesi, kendi uygulamasında bulunan aşağıdaki satırı eklenir (. CPP) dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#16](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_1.cpp)]  
  
 Bu yenileme yöntemi denetimin kullanıcılara kullanılabilmesini sağlar.  
  
 Aşağıdaki satırı denetimin eklenir. IDL dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#17](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_2.idl)]  
  
 Bu satırı Refresh yöntemi belirli bir kimlik numarası atar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)


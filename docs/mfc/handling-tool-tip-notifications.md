---
title: "Araç İpucu bildirimlerini işleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- CToolBarCtrl class [MFC], handling notifications
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: ddb93b5f-2e4f-4537-8053-3453c86e2bbb
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6d6ec102d38e91389fddb3faf4eb83ace9ba7129
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="handling-tool-tip-notifications"></a>Araç İpucu Bildirimlerini İşleme
Belirttiğinizde `TBSTYLE_TOOLTIPS` stili, araç oluşturur ve bir araç ipucunu denetimini yönetir. Araç İpucu araç çubuğu düğmesi açıklayan metin satırının içeren küçük bir açılır penceredir. Yalnızca kullanıcı imleci bir araç çubuğu düğmesini koyar ve onu var. yaklaşık yarısı için ikinci bırakır görünen araç ipucu gizlenir. Araç İpucu imlecin yanında görüntülenir.  
  
 Araç İpucu görüntülenmeden önce **TTN_NEEDTEXT** düğmesi için açıklayıcı metni almak için araç çubuğunun sahibi penceresine bildirim iletisi gönderilir. Araç çubuğunun sahibi pencere ise bir `CFrameWnd` penceresinde, araç ipuçları, tüm ek çaba görüntülenir, çünkü `CFrameWnd` için bir varsayılan işleyici sahip **TTN_NEEDTEXT** bildirim. Araç çubuğunun sahibi penceresi türetilmedi varsa `CFrameWnd`, bir iletişim kutusu veya form görünüm gibi sahibi pencerenin ileti eşlemesi için bir giriş ekleyin ve gerekir ileti eşlemesi bildirim işleyicisinde sağlayın. Girişine sahip pencerenin ileti eşlemesi aşağıdaki gibidir:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-tool-tip-notifications_1.cpp)]  
  
## <a name="remarks"></a>Açıklamalar  
 `memberFxn`  
 Metin için bu düğmeyi gerektiğinde çağrılacak üye işlevi.  
  
 Araç İpucu kimliği her zaman olduğuna dikkat edin 0.  
  
 Ek olarak **TTN_NEEDTEXT** bildirimi, bir araç ipucunu denetimini gönderebilir aşağıdaki bildirimler için bir araç çubuğu denetimi:  
  
|Bildirim|Açıklama|  
|------------------|-------------|  
|**TTN_NEEDTEXTA**|Araç ipucunu denetimini ASCII metni (yalnızca Windows 95) gerektirir|  
|**TTN_NEEDTEXTW**|Araç ipucunu denetimini UNICODE metni (yalnızca Windows NT) gerektirir|  
|**TBN_HOTITEMCHANGE**|Etkin (vurgulanan) öğenin değiştiğini gösterir.|  
|**NM_RCLICK**|Kullanıcı bir düğme sağ tıklattığınız gösterir.|  
|**TBN_DRAGOUT**|Kullanıcı düğmesine tıklanana ve işaretçiyi düğmeden sürüklenen gösterir. Araç çubuğu düğmesinden bırakma ve sürükleme uygulanması bir uygulama sağlar. Bu bildirim alındığında uygulama Sürükle başlamak ve bırak işlemini.|  
|**TBN_DROPDOWN**|Kullanıcının kullandığı bir düğme tıkladığını gösterir **TBSTYLE_DROPDOWN** stili.|  
|**TBN_GETOBJECT**|Kullanıcı taşınabilir işaretçinin kullanan bir düğme gösterir **TBSTYLE_DROPPABLE** stili.|  
  
 Bir örnek işleyici işlevi ve araç ipuçlarını etkinleştirme hakkında daha fazla bilgi için bkz: [araç ipuçları](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolBarCtrl kullanma](../mfc/using-ctoolbarctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)


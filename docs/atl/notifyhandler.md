---
title: NotifyHandler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: NotifyHandler
dev_langs: C++
helpviewer_keywords: NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 11f078e6e47aa6c392de79d9811df8738ce09ed9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="notifyhandler"></a>NotifyHandler
Öğesinin üçüncü parametresi tarafından belirtilen işlevin adını `NOTIFY_HANDLER` makro ileti eşlemesi içinde.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
 
    LRESULT 
    NotifyHandler 
 (
    int idCtrl,  
    LPNMHDR pnmh,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>Parametreler  
 `idCtrl`  
 İleti gönderilirken denetim tanımlayıcısı.  
  
 *pnmh*  
 Adres bir [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) bildirim kodu ve ek bilgiler içeren yapısı. Bazı bildirim iletileri için bu parametre olan daha büyük bir yapının işaret **NMHDR** yapısı ilk üye olarak.  
  
 `bHandled`  
 İleti eşleme kümeleri `bHandled` için **TRUE** önce *NotifyHandler* olarak adlandırılır. Varsa *NotifyHandler* tam ileti işlemiyor ayarlamanız gerekir `bHandled` için **FALSE** ileti gereken başka bir işleme belirtmek için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İleti işleme sonucu. başarılı olursa 0.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu ileti işleyicisi bir ileti eşlemesi kullanarak bir örnek için bkz: [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir pencere uygulama](../atl/implementing-a-window.md)   
 [İleti eşlemeleri](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)


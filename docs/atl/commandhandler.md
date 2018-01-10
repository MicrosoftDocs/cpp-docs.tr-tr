---
title: CommandHandler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CommandHandler
dev_langs: C++
helpviewer_keywords: CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c17d9e731eaee9c6e1a1c584e61db6c9826cf8d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="commandhandler"></a>CommandHandler
`CommandHandler`öğesinin üçüncü parametresi tarafından tanımlanan işlevi `COMMAND_HANDLER` makro ileti eşlemesi içinde.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
 
    LRESULT 
    CommandHandler 
 (
    WORD wNotifyCode,  
    WORD wID,  
    HWND hWndCtl,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>Parametreler  
 `wNotifyCode`  
 Bildirim kodu.  
  
 *WID*  
 Menü öğesi, denetim veya Hızlandırıcı tanımlayıcısı.  
  
 *hWndCtl*  
 Pencere denetim için bir tanıtıcı.  
  
 `bHandled`  
 İleti eşleme kümeleri `bHandled` için **TRUE** önce `CommandHandler` olarak adlandırılır. Varsa `CommandHandler` tam ileti işlemiyor ayarlamanız gerekir `bHandled` için **FALSE** ileti gereken başka bir işleme belirtmek için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İleti işleme sonucu. başarılı olursa 0.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu ileti işleyicisi bir ileti eşlemesi kullanarak bir örnek için bkz: [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir pencere uygulama](../atl/implementing-a-window.md)   
 [İleti eşlemeleri](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)


---
title: MessageHandler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- MessageHandler
dev_langs:
- C++
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7247868f85a30cbecef416c690f181f068f7eaf2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="messagehandler"></a>MessageHandler
**MessageHandler** öğesinin ikinci parametresi, tarafından tanımlanan işlevi adı `MESSAGE_HANDLER` makro ileti eşlemesi içinde.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
 
    LRESULT 
    MessageHandler 
 (
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>Parametreler  
 `uMsg`  
 İletiyi belirtir.  
  
 `wParam`  
 Ek ileti özgü bilgiler.  
  
 `lParam`  
 Ek ileti özgü bilgiler.  
  
 `bHandled`  
 İleti eşleme kümeleri `bHandled` için **TRUE** önce `MessageHandler` olarak adlandırılır. Varsa `MessageHandler` tam ileti işlemiyor ayarlamanız gerekir `bHandled` için **FALSE** ileti gereken başka bir işleme belirtmek için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İleti işleme sonucu. başarılı olursa 0.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu ileti işleyicisi bir ileti eşlemesi kullanarak bir örnek için bkz: [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir pencere uygulama](../atl/implementing-a-window.md)   
 [İleti eşlemeleri](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)


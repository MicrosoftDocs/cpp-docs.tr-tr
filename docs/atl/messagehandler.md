---
title: MessageHandler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- MessageHandler
dev_langs:
- C++
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dcd02396fa76e9e68fce628783fb17bc6adab36e
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848408"
---
# <a name="messagehandler"></a>MessageHandler
`MessageHandler` ikinci parametresi, ileti eşlemesi MESSAGE_HANDLER makro ile tanımlanan işlev adıdır.  
  
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
 *uMsg*  
 İletiyi belirtir.  
  
 *wParam*  
 İletiye özgü ek bilgiler.  
  
 *lParam*  
 İletiye özgü ek bilgiler.  
  
 *bHandled*  
 İleti eşleme kümeleri *bHandled* önce true `MessageHandler` çağrılır. Varsa `MessageHandler` tam iletiyi işlemez ayarlamanız gerekir *bHandled* ihtiyaç daha fazla işleme belirtmek için false.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İleti işleme sonucu. başarılıysa 0.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu ileti işleyicisi bir ileti eşlemede kullanma örneği için bkz: [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere uygulama](../atl/implementing-a-window.md)   
 [İleti eşlemeleri](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)


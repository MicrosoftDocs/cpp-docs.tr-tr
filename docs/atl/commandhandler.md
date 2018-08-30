---
title: CommandHandler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CommandHandler
dev_langs:
- C++
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ad124f0819dbfd9cfd0117cb91fbcffba05a400
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201282"
---
# <a name="commandhandler"></a>CommandHandler
`CommandHandler` işlevi, ileti eşlemesi COMMAND_HANDLER makroda'öğesinin üçüncü parametresi tarafından tanımlanır.  
  
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
 *wNotifyCode*  
 Uyarı kodu.  
  
 *wID*  
 Menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısı.  
  
 *hWndCtl*  
 Bir pencere denetimi için bir tanıtıcı.  
  
 *bHandled*  
 İleti eşleme kümeleri *bHandled* önce true `CommandHandler` çağrılır. Varsa `CommandHandler` tam iletiyi işlemez ayarlamanız gerekir *bHandled* ihtiyaç daha fazla işleme belirtmek için false.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İleti işleme sonucu. başarılıysa 0.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu ileti işleyicisi bir ileti eşlemede kullanma örneği için bkz: [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere uygulama](../atl/implementing-a-window.md)   
 [İleti eşlemeleri](../atl/message-maps-atl.md)   
 [WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583)


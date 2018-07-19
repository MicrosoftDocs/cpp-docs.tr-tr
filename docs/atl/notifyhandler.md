---
title: NotifyHandler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- NotifyHandler
dev_langs:
- C++
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 72c6c992f2ec92bc11d6dd009649d503d3c0bd02
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848343"
---
# <a name="notifyhandler"></a>NotifyHandler
İleti haritanızı NOTIFY_HANDLER makroda'öğesinin üçüncü parametresi tarafından belirtilen işlevin adı.  
  
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
 *idCtrl*  
 İletiyi gönderen denetim tanımlayıcısı.  
  
 *pnmh*  
 Adresi bir [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) bildirimi kodunu ve ek bilgiler içeren yapısı. Bazı bildirim iletileri için bu parametreyi olan daha büyük bir yapısına işaret `NMHDR` yapısı olarak kendi ilk üyesi.  
  
 *bHandled*  
 İleti eşleme kümeleri *bHandled* önce true *NotifyHandler* çağrılır. Varsa *NotifyHandler* tam iletiyi işlemez ayarlamanız gerekir *bHandled* için **FALSE** ihtiyaç daha fazla işleme belirtmek için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İleti işleme sonucu. başarılıysa 0.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu ileti işleyicisi bir ileti eşlemede kullanma örneği için bkz: [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere uygulama](../atl/implementing-a-window.md)   
 [İleti eşlemeleri](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

